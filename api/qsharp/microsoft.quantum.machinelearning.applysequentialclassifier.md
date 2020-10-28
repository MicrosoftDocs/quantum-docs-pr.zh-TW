---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: ApplySequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699701"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="46bb1-102">ApplySequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="46bb1-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="46bb1-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="46bb1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="46bb1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46bb1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46bb1-105">提供順序分類器的結構和參數化，將分類器套用至量子位的註冊。</span><span class="sxs-lookup"><span data-stu-id="46bb1-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="46bb1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="46bb1-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="46bb1-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="46bb1-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="46bb1-108">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="46bb1-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="46bb1-109">應套用分類器的目標暫存器。</span><span class="sxs-lookup"><span data-stu-id="46bb1-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46bb1-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46bb1-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

