---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: 68d9e02fd19df008f2d42b4f04b585a441b2408a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699630"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="12ea3-102">ApplyIfElseIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="12ea3-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="12ea3-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="12ea3-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="12ea3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12ea3-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="12ea3-105">輸入</span><span class="sxs-lookup"><span data-stu-id="12ea3-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="12ea3-106">measurementResult： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="12ea3-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-adj"></a><span data-ttu-id="12ea3-107">onResultZeroOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="12ea3-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onresultoneop--unit--unit-adj"></a><span data-ttu-id="12ea3-108">onResultOneOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="12ea3-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="12ea3-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12ea3-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

