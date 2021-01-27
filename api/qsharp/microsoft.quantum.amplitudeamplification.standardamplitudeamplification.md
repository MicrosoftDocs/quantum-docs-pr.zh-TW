---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843936"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="2a72d-102">StandardAmplitudeAmplification 函式</span><span class="sxs-lookup"><span data-stu-id="2a72d-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="2a72d-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2a72d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2a72d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a72d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a72d-105">標準振幅放大演算法</span><span class="sxs-lookup"><span data-stu-id="2a72d-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2a72d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2a72d-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="2a72d-107">nIterations： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a72d-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a72d-108">$n $ of 振幅放大的反覆運算次數</span><span class="sxs-lookup"><span data-stu-id="2a72d-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="2a72d-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="2a72d-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="2a72d-110">準備開始狀態的單一 oracle $A $</span><span class="sxs-lookup"><span data-stu-id="2a72d-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="2a72d-111">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a72d-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a72d-112">索引至旗標量子位</span><span class="sxs-lookup"><span data-stu-id="2a72d-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="2a72d-113">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2a72d-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2a72d-114">實作為標準振幅放大量子演算法的作業</span><span class="sxs-lookup"><span data-stu-id="2a72d-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="2a72d-115">備註</span><span class="sxs-lookup"><span data-stu-id="2a72d-115">Remarks</span></span>

<span data-ttu-id="2a72d-116">這是藉由 `AmpAmpPhasesStandard` 假設 \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} s + \sqrt{1-| \lambda | ^ 2} \ket f\cdots，所計算的一系列反映階段所取得的標準幅度放大演算法 \_ {0} \_ \end{align} 這項作業會在大部分情況下準備狀態 \begin{align} \Operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \Sin ( # B1 2n + 1) \sin ^ {-1} ( \lambda) # A5\ket {1} \_ f\ket {\ text {target}} \_ s + \cdots\ket {0} \_ f \end{align}， `flagQubit` 並且在 `auxiliaryRegister` 狀態 $ \ket {0} \_ f\ket {0} \_ a $ 中初始化。</span><span class="sxs-lookup"><span data-stu-id="2a72d-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="2a72d-117">參考資料</span><span class="sxs-lookup"><span data-stu-id="2a72d-117">References</span></span>

- [<span data-ttu-id="2a72d-118">*G. Brassard、Hoyer、Mosca、Tapp*</span><span class="sxs-lookup"><span data-stu-id="2a72d-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)