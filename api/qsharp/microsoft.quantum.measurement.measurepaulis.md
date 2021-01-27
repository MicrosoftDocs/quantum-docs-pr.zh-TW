---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853777"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="47d95-102">MeasurePaulis 操作</span><span class="sxs-lookup"><span data-stu-id="47d95-102">MeasurePaulis operation</span></span>

<span data-ttu-id="47d95-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="47d95-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="47d95-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47d95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47d95-105">指定多量子位 Pauli 運算子的陣列時，會使用指定的測量小工具來測量每個運算子，然後傳回結果的陣列。</span><span class="sxs-lookup"><span data-stu-id="47d95-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="47d95-106">輸入</span><span class="sxs-lookup"><span data-stu-id="47d95-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="47d95-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="47d95-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="47d95-108">要測量的多量子位 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="47d95-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="47d95-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47d95-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="47d95-110">註冊要測量指定運算子的。</span><span class="sxs-lookup"><span data-stu-id="47d95-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="47d95-111">小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="47d95-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="47d95-112">執行指定多量子位運算子測量的作業。</span><span class="sxs-lookup"><span data-stu-id="47d95-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="47d95-113">輸出：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="47d95-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="47d95-114">從測量的每個專案所取得的結果 `paulis` 陣列 `target` 。</span><span class="sxs-lookup"><span data-stu-id="47d95-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>