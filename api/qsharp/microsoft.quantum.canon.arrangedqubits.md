---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699102"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


根據索引排列控制項、目標和 helper 量子位

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>描述

傳回量子位陣列，其目標位於索引0，並在索引 2 ^ i 處控制 i。  Helper 量子位會插入陣列中的所有其他位置。

## <a name="input"></a>輸入

### <a name="controls--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>helper： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

