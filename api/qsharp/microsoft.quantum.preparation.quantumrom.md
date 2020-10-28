---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700419"
---
# <a name="quantumrom-function"></a><span data-ttu-id="d90f3-102">QuantumROM 函式</span><span class="sxs-lookup"><span data-stu-id="d90f3-102">QuantumROM function</span></span>

<span data-ttu-id="d90f3-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d90f3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d90f3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d90f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d90f3-105">使用量子 ROM 技術來代表指定的密度矩陣。</span><span class="sxs-lookup"><span data-stu-id="d90f3-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="d90f3-106">假設有一份 $N $ 係數 $ \ Alpha_j $ 的清單，這會傳回單一 $U $，其使用量子 ROM 技術來準備近似 $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ 淨化的密度對照表 $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j} $。</span><span class="sxs-lookup"><span data-stu-id="d90f3-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="d90f3-107">在此近似值中，錯誤 $ \epsilon $ 為 $ | p_j-\frac{| Alpha_j |}{\ sum_k | \ Alpha_k |} |\le \epsilon/N $ 和 $ \| \tilde\rho-\rho \| \le \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="d90f3-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="d90f3-108">換句話說，$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ ket {0} ^ {m} = \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}。</span><span class="sxs-lookup"><span data-stu-id="d90f3-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="d90f3-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d90f3-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="d90f3-110">輸入</span><span class="sxs-lookup"><span data-stu-id="d90f3-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="d90f3-111">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d90f3-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d90f3-112">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="d90f3-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="d90f3-113">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d90f3-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d90f3-114">$N $ 係數的陣列，指定基礎狀態的機率。</span><span class="sxs-lookup"><span data-stu-id="d90f3-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="d90f3-115">負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="d90f3-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="d90f3-116">Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int)) # A4，[Double](xref:microsoft.quantum.lang-ref.double)， ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="d90f3-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="d90f3-117">第一個參數</span><span class="sxs-lookup"><span data-stu-id="d90f3-117">First parameter</span></span>

<span data-ttu-id="d90f3-118">元組， `(x,(y,z))` 其中 `x = y + z` 是配置的量子位總數， `y` 是註冊的量子位數目 `LittleEndian` ，而 `z` 是垃圾量子位的數目。</span><span class="sxs-lookup"><span data-stu-id="d90f3-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="d90f3-119">第二個參數</span><span class="sxs-lookup"><span data-stu-id="d90f3-119">Second parameter</span></span>

<span data-ttu-id="d90f3-120">係數陣列的單一標準 $ \ sum_j | \ Alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="d90f3-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="d90f3-121">第三個參數</span><span class="sxs-lookup"><span data-stu-id="d90f3-121">Third parameter</span></span>

<span data-ttu-id="d90f3-122">單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="d90f3-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="d90f3-123">參考</span><span class="sxs-lookup"><span data-stu-id="d90f3-123">References</span></span>

- <span data-ttu-id="d90f3-124">使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="d90f3-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>