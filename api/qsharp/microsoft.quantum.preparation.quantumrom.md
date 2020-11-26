---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229880"
---
# <a name="quantumrom-function"></a><span data-ttu-id="14b31-102">QuantumROM 函式</span><span class="sxs-lookup"><span data-stu-id="14b31-102">QuantumROM function</span></span>

<span data-ttu-id="14b31-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="14b31-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="14b31-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14b31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="14b31-105">QuantumROM 已被取代。</span><span class="sxs-lookup"><span data-stu-id="14b31-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="14b31-106">請改用 <xref:Microsoft.Quantum.Preparation.PurifiedMixedState>。</span><span class="sxs-lookup"><span data-stu-id="14b31-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="14b31-107">使用量子 ROM 技術來代表指定的密度矩陣。</span><span class="sxs-lookup"><span data-stu-id="14b31-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="14b31-108">假設有一份 $N $ 係數 $ \ Alpha_j $ 的清單，這會傳回單一 $U $，其使用量子 ROM 技術來準備近似 $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ 淨化的密度對照表 $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j} $。</span><span class="sxs-lookup"><span data-stu-id="14b31-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="14b31-109">在此近似值中，錯誤 $ \epsilon $ 為 $ | p_j-\frac{| Alpha_j |}{\ sum_k | \ Alpha_k |} |\le \epsilon/N $ 和 $ \| \tilde\rho-\rho \| \le \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="14b31-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="14b31-110">換句話說，$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ ket {0} ^ {m} = \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}。</span><span class="sxs-lookup"><span data-stu-id="14b31-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="14b31-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="14b31-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="14b31-112">輸入</span><span class="sxs-lookup"><span data-stu-id="14b31-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="14b31-113">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="14b31-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="14b31-114">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="14b31-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="14b31-115">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="14b31-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="14b31-116">$N $ 係數的陣列，指定基礎狀態的機率。</span><span class="sxs-lookup"><span data-stu-id="14b31-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="14b31-117">負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="14b31-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="14b31-118">Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int)) # A4，[Double](xref:microsoft.quantum.lang-ref.double)， ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="14b31-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="14b31-119">第一個參數</span><span class="sxs-lookup"><span data-stu-id="14b31-119">First parameter</span></span>

<span data-ttu-id="14b31-120">元組， `(x,(y,z))` 其中 `x = y + z` 是配置的量子位總數， `y` 是註冊的量子位數目 `LittleEndian` ，而 `z` 是垃圾量子位的數目。</span><span class="sxs-lookup"><span data-stu-id="14b31-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="14b31-121">第二個參數</span><span class="sxs-lookup"><span data-stu-id="14b31-121">Second parameter</span></span>

<span data-ttu-id="14b31-122">係數陣列的單一標準 $ \ sum_j | \ Alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="14b31-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="14b31-123">第三個參數</span><span class="sxs-lookup"><span data-stu-id="14b31-123">Third parameter</span></span>

<span data-ttu-id="14b31-124">單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="14b31-124">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="14b31-125">參考</span><span class="sxs-lookup"><span data-stu-id="14b31-125">References</span></span>

- <span data-ttu-id="14b31-126">使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="14b31-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>