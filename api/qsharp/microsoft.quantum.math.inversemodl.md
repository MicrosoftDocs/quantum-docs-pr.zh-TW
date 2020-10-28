---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700611"
---
# <a name="inversemodl-function"></a>InverseModL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


傳回 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>輸入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要反轉的數位


### <a name="modulus--bigint"></a>模數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

根據數位反轉的模數



## <a name="output--bigint"></a>輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

整數 $b $，例如 $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。