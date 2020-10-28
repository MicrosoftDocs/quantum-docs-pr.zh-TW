---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.Delay
title: 延遲操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: Delay
qsharp.summary: ''
ms.openlocfilehash: e6d917946f37c97bbab412c13f977aadf1c118e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701194"
---
# <a name="delay-operation"></a><span data-ttu-id="62643-102">延遲操作</span><span class="sxs-lookup"><span data-stu-id="62643-102">Delay operation</span></span>

<span data-ttu-id="62643-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="62643-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="62643-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62643-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation Delay<'T> (op : ('T => Unit), arg : 'T, aux : Unit) : Unit
```


## <a name="input"></a><span data-ttu-id="62643-105">輸入</span><span class="sxs-lookup"><span data-stu-id="62643-105">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="62643-106">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62643-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="arg--t"></a><span data-ttu-id="62643-107">arg： t</span><span class="sxs-lookup"><span data-stu-id="62643-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="62643-108">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62643-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="62643-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62643-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="62643-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="62643-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="62643-111">不要</span><span class="sxs-lookup"><span data-stu-id="62643-111">'T</span></span>

