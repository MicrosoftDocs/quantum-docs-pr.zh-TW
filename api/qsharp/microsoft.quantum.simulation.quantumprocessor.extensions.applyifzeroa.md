---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 812b7a830d963b4bb73c32ba1c136e506789e997
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854190"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="bc345-102">ApplyIfZeroA 操作</span><span class="sxs-lookup"><span data-stu-id="bc345-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="bc345-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bc345-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bc345-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bc345-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bc345-105">輸入</span><span class="sxs-lookup"><span data-stu-id="bc345-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bc345-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="bc345-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="bc345-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="bc345-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="bc345-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="bc345-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bc345-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc345-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc345-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="bc345-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc345-111">不要</span><span class="sxs-lookup"><span data-stu-id="bc345-111">'T</span></span>

