---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194214"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="5aa43-102">MeasurePaulis 操作</span><span class="sxs-lookup"><span data-stu-id="5aa43-102">MeasurePaulis operation</span></span>

<span data-ttu-id="5aa43-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="5aa43-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="5aa43-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5aa43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5aa43-105">指定多量子位 Pauli 運算子的陣列時，會使用指定的測量小工具來測量每個運算子，然後傳回結果的陣列。</span><span class="sxs-lookup"><span data-stu-id="5aa43-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="5aa43-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5aa43-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="5aa43-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="5aa43-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="5aa43-108">要測量的多量子位 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="5aa43-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5aa43-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5aa43-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5aa43-110">註冊要測量指定運算子的。</span><span class="sxs-lookup"><span data-stu-id="5aa43-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="5aa43-111">小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="5aa43-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="5aa43-112">執行指定多量子位運算子測量的作業。</span><span class="sxs-lookup"><span data-stu-id="5aa43-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5aa43-113">輸出：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="5aa43-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="5aa43-114">從測量的每個專案所取得的結果 `paulis` 陣列 `target` 。</span><span class="sxs-lookup"><span data-stu-id="5aa43-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>