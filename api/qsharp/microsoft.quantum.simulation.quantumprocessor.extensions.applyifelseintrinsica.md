---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: 12144630d1ffe0210c5979db0a94dc5267f17d30
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230152"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="3e2a4-102">ApplyIfElseIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="3e2a4-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="3e2a4-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="3e2a4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3e2a4-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3e2a4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3e2a4-105">輸入</span><span class="sxs-lookup"><span data-stu-id="3e2a4-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="3e2a4-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3e2a4-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-adj"></a><span data-ttu-id="3e2a4-107">onResultZeroOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="3e2a4-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onresultoneop--unit--unit--is-adj"></a><span data-ttu-id="3e2a4-108">onResultOneOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="3e2a4-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="3e2a4-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e2a4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

