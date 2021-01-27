---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.DelayCA
title: DelayCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: DelayCA
qsharp.summary: ''
ms.openlocfilehash: 3b98cb25adc4e7b39a6139ce1631b1a4505a69bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857856"
---
# <a name="delayca-operation"></a><span data-ttu-id="d3554-102">DelayCA 操作</span><span class="sxs-lookup"><span data-stu-id="d3554-102">DelayCA operation</span></span>

<span data-ttu-id="d3554-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d3554-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d3554-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d3554-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d3554-105">輸入</span><span class="sxs-lookup"><span data-stu-id="d3554-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="d3554-106">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d3554-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="arg--t"></a><span data-ttu-id="d3554-107">arg： t</span><span class="sxs-lookup"><span data-stu-id="d3554-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="d3554-108">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3554-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d3554-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3554-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d3554-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="d3554-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3554-111">不要</span><span class="sxs-lookup"><span data-stu-id="d3554-111">'T</span></span>

