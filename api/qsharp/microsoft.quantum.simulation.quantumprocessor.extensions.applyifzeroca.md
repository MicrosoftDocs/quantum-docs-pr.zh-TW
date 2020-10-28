---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701195"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="5e6ce-102">ApplyIfZeroCA 操作</span><span class="sxs-lookup"><span data-stu-id="5e6ce-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="5e6ce-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="5e6ce-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5e6ce-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e6ce-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="5e6ce-105">輸入</span><span class="sxs-lookup"><span data-stu-id="5e6ce-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="5e6ce-106">measurementResult： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="5e6ce-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl--adj"></a><span data-ttu-id="5e6ce-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="5e6ce-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="5e6ce-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="5e6ce-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="5e6ce-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e6ce-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e6ce-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="5e6ce-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e6ce-111">不要</span><span class="sxs-lookup"><span data-stu-id="5e6ce-111">'T</span></span>

