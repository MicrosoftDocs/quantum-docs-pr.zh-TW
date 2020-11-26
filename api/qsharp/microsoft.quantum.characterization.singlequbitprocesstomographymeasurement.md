---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 3756040df8e34ecee1e968428b08387e0096ab7b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204193"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="f3e8a-102">SingleQubitProcessTomographyMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="f3e8a-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="f3e8a-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f3e8a-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f3e8a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3e8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3e8a-105">指定特定的通道，以 Pauli 為基礎執行單一量子位流程 tomography 測量。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="f3e8a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f3e8a-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="f3e8a-107">準備： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f3e8a-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f3e8a-108">要準備量子位的 Pauli 基礎元素 $P $。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="f3e8a-109">測量： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="f3e8a-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="f3e8a-110">要測量量子位的 Pauli 基礎元素 $Q $。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="f3e8a-111">通道： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3e8a-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f3e8a-112">單一量子位通道 $ \Lambda $，其行為正以進程 tomography 進行評估。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f3e8a-113">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f3e8a-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="f3e8a-114">`Zero`Probability $ $ \Begin{align} \Pr ( \texttt{zero} | \Lambda; 的結果P，Q) = \operatorname{Tr}\left ( \frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right) 。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="f3e8a-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f3e8a-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="f3e8a-116">備註</span><span class="sxs-lookup"><span data-stu-id="f3e8a-116">Remarks</span></span>

<span data-ttu-id="f3e8a-117">這項作業所傳回之結果的散發是雙量子位狀態 tomography 的特殊案例。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="f3e8a-118">Let $ \rho = J ( \Lambda) /$2 是 $ \Lambda $ 的 Choi 對於– Jamiłkowski 狀態。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="f3e8a-119">然後，上述散發與 $ $ \begin{align} \Pr ( \texttt{Zero} 相同。rhoM) = \operatorname{Tr} (M \rho) ，\end{align} $ $ where $M = 2 ( \boldone + P) ^ \mathrm{T}/2 \cdot ( \boldone + Q) /$2 是對應至 $P $ 和 $Q $ 的有效測量。</span><span class="sxs-lookup"><span data-stu-id="f3e8a-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>