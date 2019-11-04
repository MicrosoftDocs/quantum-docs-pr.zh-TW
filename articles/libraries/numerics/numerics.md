---
title: 使用數值程式庫 |Microsoft Docs
description: 使用數值程式庫
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184605"
---
# <a name="using-the-numerics-library"></a>使用數值程式庫

## <a name="overview"></a>概觀

數值程式庫是由三個元件所組成

1. 整數 adders 和比較子的**基本整數算術**
1. **高階整數功能**是建置於基本功能之上;其中包括乘法、除法、反轉等等。 適用于帶正負號和不帶正負號的整數。
1. 具有固定點初始化、加法、乘法、倒數、多項式評估和測量的**定點算術功能**。

所有這些元件都可以使用單一 `open` 語句來存取：
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>類型

數值程式庫支援下列類型

1. **`LittleEndian`** ：代表整數的 qubit 陣列 `qArr : Qubit[]`，其中 `qArr[0]` 表示最不重要的位。
1. **`SignedLittleEndian`** ：與 `LittleEndian` 相同，不同之處在于它代表儲存在兩個補數中的帶正負號的整數。
1. **`FixedPoint`** ：代表由 qubit 陣列 `qArr2 : Qubit[]` 和二進位點位置 `pos`所組成的實數，其會計算二進位點左邊的二進位位數數目。 `qArr2` 的儲存方式與 `SignedLittleEndian`相同。

## <a name="operations"></a>Dynamics 365

針對上述三種類型的每一種，可以使用各種不同的作業：

1. **`LittleEndian`**
    - 加法
    - 比較
    - 乘法
    - 求
    - 除法（含餘數）

1. **`SignedLittleEndian`**
    - 加法
    - 比較
    - 反轉模數2補數
    - 乘法
    - 求

1. **`FixedPoint`**
    - 準備/初始化為傳統值
    - 加法（傳統常數或其他配量固定點）
    - 比較
    - 乘法
    - 求
    - 對偶數和奇數函式的特製化進行多項式評估
    - 倒數（1/x）
    - 測量（傳統雙精度浮點數）

如需每一項作業的詳細資訊和詳細檔，請參閱 Q # 程式庫參考檔，網址為[docs.microsoft.com](https://docs.microsoft.com/en-us/quantum)

## <a name="sample-integer-addition"></a>範例：整數加法

作為基本範例，請考慮 operation $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是採用 n-qubit 整數的作業，$x $ 和 n 或（n + 1）-qubit 暫存器 $y $ 做為輸入，後者會對應到 sum $ （x + y） $。 請注意，如果 $y $ 儲存在 $n $ bit 暫存器中，則總和為計算的模數 $ 2 ^ n $。

使用配量開發工具組時，可以套用此作業，如下所示：
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>範例：評估平滑功能

若要在量子電腦上評估如 $ \sin （x） $ 之類的平滑功能，其中 $x $ 是量子 `FixedPoint` 號碼，則配量開發工具組數值程式庫會提供作業 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP`。

第一個 `EvaluatePolynomialFxP`，可讓評估格式為 $ $ P （x） = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 的多項式，其中 $d $ 代表該*程度*。 若要這麼做，只需要多項式係數 `[a_0,..., a_d]` （類型 `Double[]`）、輸入 `x : FixedPoint` 和輸出 `y : FixedPoint` （一開始為零）：
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
$P （x） = 1 + 2x $ 的結果將會儲存在 `yFxP`中。

第二個、`EvaluateEvenPolynomialFxP`和第三個 `EvaluateOddPolynomialFxP`，分別適用于偶數和奇數函式的案例。 也就是說，若是偶數/奇數函數 $f （x） $ 和 $ $ P_ {偶數} （x） = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d}，$ $ $f （x） $ $P _ {偶數} （x） $ 或 $P _ {奇數} （x）： = x\cdot P_ {偶數} （x） $各自.
在 Q # 中，這兩個案例可以依照下列方式處理：
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
這會評估 $P _ {偶數} （x） = 1 + 2x ^ 2 $，以及
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
這會評估 $P _ {奇數} （x） = x + 2x ^ 3 $。

## <a name="more-samples"></a>更多範例

您可以在[主要範例存放庫](https://github.com/Microsoft/Quantum)中找到更多範例。

若要開始使用，請複製存放庫，並開啟 [`Numerics`] 子資料夾：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

然後，`cd` 到其中一個範例資料夾，並透過執行範例

```bash
dotnet run
```
