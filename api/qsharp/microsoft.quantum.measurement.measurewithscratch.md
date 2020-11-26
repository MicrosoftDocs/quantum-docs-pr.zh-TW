---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227058"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="b2506-102">MeasureWithScratch 操作</span><span class="sxs-lookup"><span data-stu-id="b2506-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="b2506-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="b2506-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="b2506-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2506-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2506-105">使用明確的臨時量子位來測量指定的 Pauli 運算子，以執行度量。</span><span class="sxs-lookup"><span data-stu-id="b2506-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="b2506-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b2506-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="b2506-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b2506-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="b2506-108">指定為單一量子位 Pauli 運算子陣列的多量子位 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="b2506-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b2506-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2506-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2506-110">要測量的量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="b2506-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b2506-111">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b2506-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="b2506-112">在註冊上測量指定 Pauli 運算子的結果 `target` 。</span><span class="sxs-lookup"><span data-stu-id="b2506-112">The result of measuring the given Pauli operator on the `target` register.</span></span>