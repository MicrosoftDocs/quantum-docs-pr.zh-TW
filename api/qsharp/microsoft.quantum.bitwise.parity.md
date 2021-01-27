---
uid: Microsoft.Quantum.Bitwise.Parity
title: 同位函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Parity
qsharp.summary: Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).
ms.openlocfilehash: b34ef36b0336ec1dea7fdbd878c6d695b38d623e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842134"
---
# <a name="parity-function"></a>同位函式

命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回整數 (1 的位同位，如果其二進位標記法包含奇數，則為 0; 否則為) 。

```qsharp
function Parity (a : Int) : Int
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>範例

```qsharp
let a = 248;
let x = Parity(a); // x : Int = 1.
```