---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: d57f07beddc94d11a2143ba5d1fd975760260731
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230866"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="b25a0-102">ApplyIfZeroA 操作</span><span class="sxs-lookup"><span data-stu-id="b25a0-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="b25a0-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b25a0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b25a0-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b25a0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b25a0-105">輸入</span><span class="sxs-lookup"><span data-stu-id="b25a0-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b25a0-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b25a0-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="b25a0-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="b25a0-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="b25a0-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="b25a0-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b25a0-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b25a0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b25a0-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="b25a0-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b25a0-111">不要</span><span class="sxs-lookup"><span data-stu-id="b25a0-111">'T</span></span>

