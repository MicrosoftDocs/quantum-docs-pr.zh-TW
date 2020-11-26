---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204346"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="db087-102">EstimateFrequencyA 操作</span><span class="sxs-lookup"><span data-stu-id="db087-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="db087-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="db087-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="db087-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db087-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db087-105">針對 adjointable 和測量的準備工作，會透過 `Zero` 執行指定的試用次數，估計 (傳回) 的測量頻率。</span><span class="sxs-lookup"><span data-stu-id="db087-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="db087-106">輸入</span><span class="sxs-lookup"><span data-stu-id="db087-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="db087-107">準備： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="db087-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="db087-108">Adjointable 作業 $P $，在其輸入暫存器上準備指定的狀態 $ \rho $。</span><span class="sxs-lookup"><span data-stu-id="db087-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="db087-109">測量：[量子位](xref:microsoft.quantum.lang-ref.qubit)[] =>__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="db087-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="db087-110">作業 $M $ 代表感興趣的度量。</span><span class="sxs-lookup"><span data-stu-id="db087-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="db087-111">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db087-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db087-112">每個動作的準備和測量量子位數目。</span><span class="sxs-lookup"><span data-stu-id="db087-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="db087-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db087-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db087-114">應執行測量的次數，以估計感興趣的頻率。</span><span class="sxs-lookup"><span data-stu-id="db087-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="db087-115">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db087-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db087-116">$M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 傳回的估計 $ \hat{p} $ `Zero` ，其使用非偏誤二項式估算器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $ 來取得，其中 $n \_ {\uparrow} $ 是 `Zero` 觀察到的結果數目。</span><span class="sxs-lookup"><span data-stu-id="db087-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="db087-117">備註</span><span class="sxs-lookup"><span data-stu-id="db087-117">Remarks</span></span>

<span data-ttu-id="db087-118">針對 adjointable 作業，可以進行某些假設，例如呼叫作業會將量子位準備成完全相同的狀態，如此可讓目的電腦進行一些效能優化。</span><span class="sxs-lookup"><span data-stu-id="db087-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>