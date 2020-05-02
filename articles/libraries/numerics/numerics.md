---
title: '使用 Microsoft Q # 數值程式庫'
description: 瞭解 Microsoft 量子數值程式庫中可用的類型和作業。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82677099"
---
# <a name="using-the-numerics-library"></a>使用數值程式庫

## <a name="overview"></a>概觀

數值程式庫是由三個元件所組成

1. 整數 adders 和比較子的**基本整數算術**
1. **高階整數功能**是建置於基本功能之上;其中包括乘法、除法、反轉等等。 適用于帶正負號和不帶正負號的整數。
1. 具有固定點初始化、加法、乘法、倒數、多項式評估和測量的**定點算術功能**。

所有這些元件都可以使用單一`open`語句來存取：
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>類型

數值程式庫支援下列類型

1. **`LittleEndian`**：代表整數的`qArr : Qubit[]` qubit 陣列，其中`qArr[0]`表示最不重要的位。
1. **`SignedLittleEndian`**：與相同`LittleEndian` ，不同之處在于它代表儲存在兩個補數中的帶正負號的整數。
1. **`FixedPoint`**：代表由 qubit 陣列`qArr2 : Qubit[]`和二進位點位置`pos`組成的實數，其會計算二進位點左邊的二進位數。 `qArr2`的儲存方式與相同`SignedLittleEndian`。

## <a name="operations"></a>作業

針對上述三種類型的每一種，可以使用各種不同的作業：

1. **`LittleEndian`**
    - 加
    - 比較
    - 乘
    - 求
    - 除法（含餘數）

1. **`SignedLittleEndian`**
    - 加
    - 比較
    - 反轉模數2補數
    - 乘
    - 求

1. **`FixedPoint`**
    - 準備/初始化為傳統值
    - 加法（傳統常數或其他配量固定點）
    - 比較
    - 乘
    - 求
    - 對偶數和奇數函式的特製化進行多項式評估
    - 倒數（1/x）
    - 測量（傳統雙精度浮點數）

如需每一項作業的詳細資訊和詳細檔，請參閱 Q # 程式庫參考檔，網址為[docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>範例：整數加法

作為基本範例，請考慮 operation $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是採用 n-qubit 整數的作業，$x $ 和 n 或（n + 1）-qubit 暫存器 $y $ 做為輸入，後者會對應到 sum $ （x + y） $。 請注意，如果 $y $ 儲存在 $n $ bit 暫存器中，則總和為計算的模數 $ 2 ^ n $。

使用配量開發工具組時，可以套用此作業，如下所示：
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

## <a name="sample-evaluating-smooth-functions"></a>範例：評估平滑功能

若要在量子電腦上評估如 $ \sin （x） $ 之類的平滑功能，其中 $x $ 是`FixedPoint`配量編號，則「量子開發工具組數值連結`EvaluatePolynomialFxP`庫`Evaluate[Even/Odd]PolynomialFxP`」會提供作業和。

第一個`EvaluatePolynomialFxP`是，可讓評估格式為 $ $ P （x） = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 的多項式，其中 $d $ 代表該*程度*。 若要`[a_0,..., a_d]`這麼做，只需要多項式係數（類型`Double[]`為）、輸入`x : FixedPoint`和輸出`y : FixedPoint` （一開始為零）：
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
$P （x） = 1 + 2x $ 的結果將會儲存在中`yFxP`。

第二個`EvaluateEvenPolynomialFxP`、和第三`EvaluateOddPolynomialFxP`個分別是偶數和奇數函式的特製化。 也就是說，若是偶數/奇數函數 $f （x） $ 和 $ $ P_ {偶數} （x） = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d}，$ $ $f （x） $ 可 $P _ {偶數} （x） $ 或 $P _ {奇數} （x）： = x\cdot P_ {偶數} （x） $ 分別為近似值。
在 Q # 中，這兩個案例可以依照下列方式處理：
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
這會評估 $P _ {偶數} （x） = 1 + 2x ^ 2 $，以及
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
這會評估 $P _ {奇數} （x） = x + 2x ^ 3 $。

## <a name="more-samples"></a>其他範例

您可以在[主要範例存放庫](https://github.com/Microsoft/Quantum)中找到更多範例。

若要開始使用`Numerics` ，請複製存放庫並開啟子資料夾：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

然後， `cd`放入其中一個範例資料夾，並透過執行範例

```bash
dotnet run
```
