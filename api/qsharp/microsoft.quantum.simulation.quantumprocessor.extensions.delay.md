---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.Delay
title: 延遲操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: Delay
qsharp.summary: ''
ms.openlocfilehash: cfc53bda7e97e22f5ca234d8e4cf92f190a46104
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230764"
---
# <a name="delay-operation"></a><span data-ttu-id="2c85a-102">延遲操作</span><span class="sxs-lookup"><span data-stu-id="2c85a-102">Delay operation</span></span>

<span data-ttu-id="2c85a-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="2c85a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="2c85a-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2c85a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation Delay<'T> (op : ('T => Unit), arg : 'T, aux : Unit) : Unit
```


## <a name="input"></a><span data-ttu-id="2c85a-105">輸入</span><span class="sxs-lookup"><span data-stu-id="2c85a-105">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="2c85a-106">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c85a-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="arg--t"></a><span data-ttu-id="2c85a-107">arg： t</span><span class="sxs-lookup"><span data-stu-id="2c85a-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="2c85a-108">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c85a-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2c85a-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c85a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c85a-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="2c85a-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c85a-111">不要</span><span class="sxs-lookup"><span data-stu-id="2c85a-111">'T</span></span>

