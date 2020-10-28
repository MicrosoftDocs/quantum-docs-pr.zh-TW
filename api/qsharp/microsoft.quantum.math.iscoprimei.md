---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700534"
---
# <a name="iscoprimei-function"></a>IsCoprimeI 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


如果 $a $ 和 $b $ 是共同質數，則傳回 true，否則傳回 false。

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

正在測試之共同 primality 的第一個數目


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

正在測試之共同 primality 的第二個數字



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果 $a $ 和 $b $ 是共同質數 (例如其最大公除數為 1 ) ，則為 True，否則為 false。