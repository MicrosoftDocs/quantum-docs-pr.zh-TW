---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216246"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="61785-102">EstimateFrequency 操作</span><span class="sxs-lookup"><span data-stu-id="61785-102">EstimateFrequency operation</span></span>

<span data-ttu-id="61785-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="61785-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="61785-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61785-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61785-105">在準備和測量之後，請透過 `Zero` 執行指定的試用次數，估計 (傳回) 的測量頻率。</span><span class="sxs-lookup"><span data-stu-id="61785-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="61785-106">輸入</span><span class="sxs-lookup"><span data-stu-id="61785-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="61785-107">準備： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61785-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="61785-108">作業 $P $，在其輸入暫存器上準備指定的狀態 $ \rho $。</span><span class="sxs-lookup"><span data-stu-id="61785-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="61785-109">測量：[量子位](xref:microsoft.quantum.lang-ref.qubit)[] =>__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="61785-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="61785-110">作業 $M $ 代表感興趣的度量。</span><span class="sxs-lookup"><span data-stu-id="61785-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="61785-111">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61785-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61785-112">每個動作的準備和測量量子位數目。</span><span class="sxs-lookup"><span data-stu-id="61785-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="61785-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61785-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61785-114">應執行測量的次數，以估計感興趣的頻率。</span><span class="sxs-lookup"><span data-stu-id="61785-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="61785-115">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="61785-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="61785-116">$M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 傳回的估計 $ \hat{p} $ `Zero` ，其使用非偏誤二項式估算器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $ 來取得，其中 $n \_ {\uparrow} $ 是 `Zero` 觀察到的結果數目。</span><span class="sxs-lookup"><span data-stu-id="61785-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="61785-117">這對具有實體限制的目的電腦特別重要，因為無法測量機率。</span><span class="sxs-lookup"><span data-stu-id="61785-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>