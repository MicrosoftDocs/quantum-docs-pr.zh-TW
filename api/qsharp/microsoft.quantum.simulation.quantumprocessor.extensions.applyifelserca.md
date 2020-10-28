---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: fb2f7ded44708a93d97d7041bf15be2c8c48990a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699592"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="74b9b-102">ApplyIfElseRCA 操作</span><span class="sxs-lookup"><span data-stu-id="74b9b-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="74b9b-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="74b9b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="74b9b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74b9b-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="74b9b-105">輸入</span><span class="sxs-lookup"><span data-stu-id="74b9b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="74b9b-106">measurementResult： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="74b9b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj--ctl"></a><span data-ttu-id="74b9b-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="74b9b-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="74b9b-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="74b9b-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-adj--ctl"></a><span data-ttu-id="74b9b-109">onResultOneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="74b9b-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="74b9b-110">oneArg： ' U</span><span class="sxs-lookup"><span data-stu-id="74b9b-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="74b9b-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74b9b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="74b9b-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="74b9b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74b9b-113">不要</span><span class="sxs-lookup"><span data-stu-id="74b9b-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="74b9b-114">' U</span><span class="sxs-lookup"><span data-stu-id="74b9b-114">'U</span></span>

