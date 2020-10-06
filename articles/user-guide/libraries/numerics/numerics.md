---
title: 使用 Microsoft Q# 數值程式庫
description: 深入瞭解 Microsoft 量子數值程式庫中可用的類型和操作。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: dfcb8e9e5a15d0881750d67cf58d7ad47cbecd3a
ms.sourcegitcommit: 897ace8b506adb2331e911ee5633dceced566174
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "91764136"
---
# <a name="using-the-numerics-library"></a>使用數值程式庫

## <a name="overview"></a>概觀

數值程式庫包含三個元件

1. 整數 adder 和比較子的**基本整數算術**
1. 建置於基本功能之上的**高階整數功能**;它包含乘法、除法、反轉等等。 用於帶正負號和不帶正負號的整數。
1. 具有固定點初始化、加法、乘法、倒數、多項式評估和測量的**定點算術功能**。

所有這些元件都可以使用單一語句來存取 `open` ：
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>類型

數值程式庫支援下列類型

1. **`LittleEndian`**：表示整數的量子位陣列 `qArr : Qubit[]` ，其中表示 `qArr[0]` 最小的位。
1. **`SignedLittleEndian`**：與 `LittleEndian` 不同之處在于，它代表以二補數儲存的帶正負號整數。
1. **`FixedPoint`**：代表量子位陣列 `qArr2 : Qubit[]` 和二進位點位置所組成的實數 `pos` ，其會計算二進位點左邊的二進位位數數目。 `qArr2` 的儲存方式與相同 `SignedLittleEndian` 。

## <a name="operations"></a>作業

上述三種類型的每一個都有提供各種不同的作業：

1. **`LittleEndian`**
    - 加法
    - 比較
    - 乘法
    - 平方
    - 具有餘數的除法 () 

1. **`SignedLittleEndian`**
    - 加法
    - 比較
    - 反轉模數2補數
    - 乘法
    - 平方

1. **`FixedPoint`**
    - 針對傳統值進行準備/初始化
    - 加法 (傳統常數或其他量子固定點) 
    - 比較
    - 乘法
    - 平方
    - 針對偶數和奇數函數特製化的多項式評估
    - 反向 (1/x) 
    -  (傳統雙精度) 的度量

如需這些作業的詳細資訊和詳細檔，請參閱連結 Q# 庫參考檔，網址 [docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>範例：整數加法

作為基本範例，請考慮作業 $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是採用 n-量子位整數 $x $ 和 n 或 (n + 1) -量子位登錄 $y $ 做為輸入，後者對應至 sum $ (x + y) $。 請注意，如果 $y $ 儲存在 $n $ 位登錄中，則總和會計算模數 $ 2 ^ n $。

您可以使用量子開發工具組來套用此作業，如下所示：
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>範例：評估平滑函數

若要在量子電腦上評估平滑的函式（例如 $ \sin (x) $，其中 $x $ 是量子 `FixedPoint` 數位），則量子開發工具組數值程式庫會提供作業 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP` 。

第一個是， `EvaluatePolynomialFxP` 可讓您評估 "$ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 的多項式，其中 $d $ 表示 *度數*。 若要這樣做，您只需要) 類型的多項式係數 `[a_0,..., a_d]` (`Double[]` 、輸入 `x : FixedPoint` 和輸出 `y : FixedPoint` (一開始零) ：
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
結果（$P (x) = 1 + 2x $）將儲存在中 `yFxP` 。

第二個、 `EvaluateEvenPolynomialFxP` 和第三個 `EvaluateOddPolynomialFxP` 分別是偶數和奇數函數的特殊化。 也就是說，針對偶數/奇數函數 $f (x) $ 和 $ $ P_ {偶數} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d} $ $ $f (x) $ 相當適合 $P _ {偶數} (x) $ 或 $P _ {奇數} (x) ： = x\cdot P_ {偶數} (x) $。
在中 Q# ，這兩個案例可以依照下列方式處理：
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
它會評估 $P _ {偶數} (x) = 1 + 2x ^ 2 $，以及
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
它會評估 $P _ {奇數} (x) = x + 2x ^ 3 $。

## <a name="more-samples"></a>其他範例

您可以在 [主要範例儲存](https://github.com/Microsoft/Quantum)機制中找到更多範例。

若要開始使用，請複製存放庫，並開啟 `Numerics` 子資料夾：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

然後，在 `cd` 其中一個範例資料夾中，並透過下列方式執行範例：

```bash
dotnet run
```
