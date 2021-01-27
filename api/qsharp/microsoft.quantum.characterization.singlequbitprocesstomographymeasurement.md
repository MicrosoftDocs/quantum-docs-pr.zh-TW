---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839646"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="79039-102">SingleQubitProcessTomographyMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="79039-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="79039-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="79039-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="79039-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79039-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79039-105">指定特定的通道，以 Pauli 為基礎執行單一量子位流程 tomography 測量。</span><span class="sxs-lookup"><span data-stu-id="79039-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="79039-106">輸入</span><span class="sxs-lookup"><span data-stu-id="79039-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="79039-107">準備： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="79039-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="79039-108">要準備量子位的 Pauli 基礎元素 $P $。</span><span class="sxs-lookup"><span data-stu-id="79039-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="79039-109">測量： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="79039-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="79039-110">要測量量子位的 Pauli 基礎元素 $Q $。</span><span class="sxs-lookup"><span data-stu-id="79039-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="79039-111">通道： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79039-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="79039-112">單一量子位通道 $ \Lambda $，其行為正以進程 tomography 進行評估。</span><span class="sxs-lookup"><span data-stu-id="79039-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="79039-113">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="79039-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="79039-114">`Zero`Probability $ $ \Begin{align} \Pr ( \texttt{zero} | \Lambda; 的結果P，Q) = \operatorname{Tr}\left ( \frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right) 。</span><span class="sxs-lookup"><span data-stu-id="79039-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="79039-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="79039-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="79039-116">備註</span><span class="sxs-lookup"><span data-stu-id="79039-116">Remarks</span></span>

<span data-ttu-id="79039-117">這項作業所傳回之結果的散發是雙量子位狀態 tomography 的特殊案例。</span><span class="sxs-lookup"><span data-stu-id="79039-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="79039-118">Let $ \rho = J ( \Lambda) /$2 是 $ \Lambda $ 的 Choi 對於– Jamiłkowski 狀態。</span><span class="sxs-lookup"><span data-stu-id="79039-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="79039-119">然後，上述散發與 $ $ \begin{align} \Pr ( \texttt{Zero} 相同。rhoM) = \operatorname{Tr} (M \rho) ，\end{align} $ $ where $M = 2 ( \boldone + P) ^ \mathrm{T}/2 \cdot ( \boldone + Q) /$2 是對應至 $P $ 和 $Q $ 的有效測量。</span><span class="sxs-lookup"><span data-stu-id="79039-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>