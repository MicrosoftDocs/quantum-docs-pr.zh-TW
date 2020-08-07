---
title: QDK 中的內部作業和函數
description: 瞭解 QDK 中的內建作業和函式，包括傳統函數和單一、旋轉和測量作業。
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 283504a5f5635a4996c804e514a6f52eb4966d22
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868435"
---
# <a name="the-prelude"></a><span data-ttu-id="17009-103">序言</span><span class="sxs-lookup"><span data-stu-id="17009-103">The Prelude</span></span> #

<span data-ttu-id="17009-104">包含在配 Q# 量開發工具組中的編譯器和目的電腦，會提供一組內建函式和作業，可在中撰寫配量程式時使用 Q# 。</span><span class="sxs-lookup"><span data-stu-id="17009-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="17009-105">內部作業和函數</span><span class="sxs-lookup"><span data-stu-id="17009-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="17009-106">標準程式庫中定義的內建作業，大致分為數個類別的其中一種：</span><span class="sxs-lookup"><span data-stu-id="17009-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="17009-107">在命名空間中收集的基本傳統函數 <xref:microsoft.quantum.core> 。</span><span class="sxs-lookup"><span data-stu-id="17009-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="17009-108">代表由[Clifford 和 $T $ 閘道](xref:microsoft.quantum.concepts.qubit)組成之 unitaries 的作業。</span><span class="sxs-lookup"><span data-stu-id="17009-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="17009-109">代表各種運算子旋轉的作業。</span><span class="sxs-lookup"><span data-stu-id="17009-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="17009-110">執行測量的作業。</span><span class="sxs-lookup"><span data-stu-id="17009-110">Operations implementing measurements.</span></span>

<span data-ttu-id="17009-111">由於 Clifford + $T $ 閘道集是適用于配量運算的[通用](xref:microsoft.quantum.concepts.multiple-qubits)集合，因此這些作業已足以在 negligibly 小型錯誤中執行任何量子演算法。</span><span class="sxs-lookup"><span data-stu-id="17009-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="17009-112">藉由提供旋轉功能，可讓程式設計人員在 Q# 單一 qubit 單一和 cnot-contains 閘道程式庫中工作。</span><span class="sxs-lookup"><span data-stu-id="17009-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="17009-113">此程式庫較容易考慮，因為它不需要程式設計人員直接表達 Clifford + $T $ 分解，而且因為有高效率的方法可以將單一 qubit unitaries 編譯成 Clifford 和 $T $ 閘道 (如需詳細資訊，請參閱[這裡](xref:microsoft.quantum.more-information)) 。</span><span class="sxs-lookup"><span data-stu-id="17009-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="17009-114">可能的話，在序言中定義的作業（作用於 qubits）允許套用 `Controlled` variant，如此目的電腦就會執行適當的分解。</span><span class="sxs-lookup"><span data-stu-id="17009-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="17009-115">在序言的這個部分中定義的許多函式和作業都在 @"microsoft.quantum.intrinsic" 命名空間中，因此大部分的 Q# 原始程式檔會 `open Microsoft.Quantum.Intrinsic;` 緊接在初始命名空間宣告之後的指示詞。</span><span class="sxs-lookup"><span data-stu-id="17009-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="17009-116"><xref:microsoft.quantum.core>命名空間會自動開啟，如此一來，就 <xref:microsoft.quantum.core.length> 可以在沒有語句的情況下使用這類函數 `open` 。</span><span class="sxs-lookup"><span data-stu-id="17009-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="17009-117">一般單一 Qubit 單一作業</span><span class="sxs-lookup"><span data-stu-id="17009-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="17009-118">序言也會定義許多常見[的單一 qubit 作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。</span><span class="sxs-lookup"><span data-stu-id="17009-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="17009-119">所有這些作業都允許 `Controlled` 和 `Adjoint` 函子。</span><span class="sxs-lookup"><span data-stu-id="17009-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="17009-120">Pauli 運算子</span><span class="sxs-lookup"><span data-stu-id="17009-120">Pauli Operators</span></span> ####

<span data-ttu-id="17009-121">作業會執行 <xref:microsoft.quantum.intrinsic.x> Pauli $X $ 運算子。</span><span class="sxs-lookup"><span data-stu-id="17009-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="17009-122">這有時候也稱為網 `NOT` 關。</span><span class="sxs-lookup"><span data-stu-id="17009-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="17009-123">它具有簽章 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-124">它會對應至單一 qubit 單一：</span><span class="sxs-lookup"><span data-stu-id="17009-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="17009-125">\begin{equation} \begin{bmatrix} 0 & 1 \\ \\ % FIXME：這目前使用 quadwhack 的駭客攻擊。</span><span class="sxs-lookup"><span data-stu-id="17009-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="17009-126">1 & 0 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="17009-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="17009-127">作業會執行 <xref:microsoft.quantum.intrinsic.y> Pauli $Y $ 運算子。</span><span class="sxs-lookup"><span data-stu-id="17009-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="17009-128">它具有簽章 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-129">它會對應至單一 qubit 單一：</span><span class="sxs-lookup"><span data-stu-id="17009-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="17009-130">\begin{equation} \begin{bmatrix} 0 &-i \\ \\ % FIXME：這目前使用 quadwhack 的駭客攻擊。</span><span class="sxs-lookup"><span data-stu-id="17009-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="17009-131">我 & 0 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="17009-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="17009-132">作業會執行 <xref:microsoft.quantum.intrinsic.z> Pauli $Z $ 運算子。</span><span class="sxs-lookup"><span data-stu-id="17009-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="17009-133">它具有簽章 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-134">它會對應至單一 qubit 單一：</span><span class="sxs-lookup"><span data-stu-id="17009-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="17009-135">\begin{equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：這目前使用 quadwhack 的駭客攻擊。</span><span class="sxs-lookup"><span data-stu-id="17009-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="17009-136">0 &-1 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="17009-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="17009-137">在下方，我們會看到這些轉換對應至[Bloch 球體](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (在每個案例中，旋轉軸會反白顯示為紅色) ：</span><span class="sxs-lookup"><span data-stu-id="17009-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![對應至 Bloch 球體的 Pauli 作業](~/media/prelude_pauliBloch.png)

<span data-ttu-id="17009-139">請務必注意，將相同的 Pauli 閘道套用至相同的 qubit 會取消作業 (因為您現在已在表面上執行2π (360 °) 的完整旋轉，而不是 Bloch 球體的) 。</span><span class="sxs-lookup"><span data-stu-id="17009-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="17009-140">這會將我們帶入下列身分識別：</span><span class="sxs-lookup"><span data-stu-id="17009-140">This brings us to the following identity:</span></span>

<span data-ttu-id="17009-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="17009-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="17009-142">這可以在 Bloch 球體上 visualised：</span><span class="sxs-lookup"><span data-stu-id="17009-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="17009-144">其他單一 Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="17009-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="17009-145">作業會執行 <xref:microsoft.quantum.intrinsic.h> Hadamard 閘道。</span><span class="sxs-lookup"><span data-stu-id="17009-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="17009-146">這會交換目標 qubit 的 Pauli $X $ 和 $Z $ 軸，因此 $H \ket {0} = \ket{+} \mathrel{： =} ( \ket {0} + \ket {1}) /\sqrt {2} $ and $H \ket{+} = \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="17009-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="17009-147">它具有 `(Qubit => Unit is Adj + Ctl)` 簽章，並對應至單一 qubit 單一：</span><span class="sxs-lookup"><span data-stu-id="17009-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="17009-148">\begin{equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME：這目前使用 quadwhack 的駭客攻擊。</span><span class="sxs-lookup"><span data-stu-id="17009-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="17009-149">1 &-1 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="17009-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="17009-150">Hadamard 閘道特別重要，因為它可以用來建立 $ \ket {0} $ 和 $ \ket {1} $ 狀態的重迭。</span><span class="sxs-lookup"><span data-stu-id="17009-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="17009-151">在 Bloch 球體標記法中，最簡單的方式是將此視為圍繞 X 軸的 $ \ket{\psi} $ 旋轉 ($ 180 ^ \circ $) ，後面接著 (順時針) 繞著 $ \ pi/2 $ 弧度 ($ 90 ^ \circ $) 的 y 軸旋轉：</span><span class="sxs-lookup"><span data-stu-id="17009-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![對應至 Bloch 球體的 Hadamard 作業](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="17009-153">作業會執行 <xref:microsoft.quantum.intrinsic.s> 階段閘道 $S $。</span><span class="sxs-lookup"><span data-stu-id="17009-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="17009-154">這是 Pauli $Z $ 作業的矩陣平方根。</span><span class="sxs-lookup"><span data-stu-id="17009-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="17009-155">也就是 $S ^ 2 = Z $。</span><span class="sxs-lookup"><span data-stu-id="17009-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="17009-156">它具有 `(Qubit => Unit is Adj + Ctl)` 簽章，並對應至單一 qubit 單一：</span><span class="sxs-lookup"><span data-stu-id="17009-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="17009-157">\begin{equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：這目前使用 quadwhack 的駭客攻擊。</span><span class="sxs-lookup"><span data-stu-id="17009-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="17009-158">0 & i \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="17009-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="17009-159">輪替人員</span><span class="sxs-lookup"><span data-stu-id="17009-159">Rotations</span></span> ####

<span data-ttu-id="17009-160">除了上述的 Pauli 和 Clifford 作業以外， Q# 序言提供各種方式來表達旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="17009-161">如[單一 qubit 作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)中所述，旋轉的功能對量子演算法而言非常重要。</span><span class="sxs-lookup"><span data-stu-id="17009-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="17009-162">我們一開始先重新開機，我們可以使用 $H $ 和 $T $ 閘道來表示任何單一 qubit 作業，其中 $H $ 是 Hadamard 作業，其中 \begin{equation} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：這目前使用的是四回摧毀的駭客攻擊。</span><span class="sxs-lookup"><span data-stu-id="17009-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="17009-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{equation} 這是作業的平方根 <xref:microsoft.quantum.intrinsic.s> ，因此 $T ^ 2 = S $。</span><span class="sxs-lookup"><span data-stu-id="17009-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="17009-164">$T $ 閘道接著會由作業執行 <xref:microsoft.quantum.intrinsic.t> ，並具有簽章 `(Qubit => Unit is Adj + Ctl)` ，表示它是單一 qubit 上的單一作業。</span><span class="sxs-lookup"><span data-stu-id="17009-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="17009-165">雖然這是用來描述任何任意單一 qubit 作業的原則，但不同的目的電腦對於 Pauli 運算子的輪替可能會有更有效率的標記法，因此序言包含各種方式來 convienently 表達這類旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="17009-166">其中最基本的作業是作業 <xref:microsoft.quantum.intrinsic.r> ，它會在指定的 Pauli 軸上執行旋轉，\Begin{equation} R ( \sigma，\phi) \mathrel{： =} \exp (-i \phi \sigma/2) ，\end{equation} 其中 $ \sigma $ 是 Pauli 運算子，$ \phi $ 是一個角度，其中 $ \exp $ 代表矩陣指數。</span><span class="sxs-lookup"><span data-stu-id="17009-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="17009-167">它具有簽章 `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` ，其中輸入的前兩個部分代表傳統引數 $ \sigma $ 和 $ \phi $ 所需，以指定單一運算子 $R ( \sigma，\phi) $。</span><span class="sxs-lookup"><span data-stu-id="17009-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="17009-168">我們可以部分套用 $ \sigma $ 和 $ \phi $，以取得其類型為單一 qubit 單一的作業。</span><span class="sxs-lookup"><span data-stu-id="17009-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="17009-169">例如， `R(PauliZ, PI() / 4, _)` 具有類型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="17009-170">作業 <xref:microsoft.quantum.intrinsic.r> 會將輸入角度除以2，並將它乘以-1。</span><span class="sxs-lookup"><span data-stu-id="17009-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="17009-171">針對 $Z $ 旋轉，這表示 $ \ket {0} $ eigenstate 會旋轉 $-\phi/$2，而 $ \ket {1} $ eigenstate 會旋轉 $ \phi/$2，因此 $ \ket $ eigenstate 會旋轉 $ \phi $ （相對於 $ \ket $ {1} {0} eigenstate）。</span><span class="sxs-lookup"><span data-stu-id="17009-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="17009-172">特別是，這表示 `T` 和 `R(PauliZ, PI() / 8, _)` 不同于不相關的[全域階段](xref:microsoft.quantum.glossary#global-phase)。</span><span class="sxs-lookup"><span data-stu-id="17009-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="17009-173">基於這個理由，$T $ 有時稱為 $ \frac{\pi} {8} $-閘道。</span><span class="sxs-lookup"><span data-stu-id="17009-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="17009-174">另請注意，旋轉 `PauliI` 只會套用 $ \phi/$2 的全域階段。</span><span class="sxs-lookup"><span data-stu-id="17009-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="17009-175">雖然這類階段並不相關，但是在[概念檔](xref:microsoft.quantum.concepts.qubit)中有人認為，它們與控制的 `PauliI` 旋轉有關。</span><span class="sxs-lookup"><span data-stu-id="17009-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="17009-176">在量子演算法中，以 dyadic 的分數表示旋轉通常很有用，例如，$ \phi = \pi k/2 ^ n $ 適用于某些 $k \in \mathbb{Z} $ 和 $n \in \mathbb{N} $。</span><span class="sxs-lookup"><span data-stu-id="17009-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="17009-177">作業會 <xref:microsoft.quantum.intrinsic.rfrac> 使用此慣例，在指定的 Pauli 軸周圍執行旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="17009-178">其與不同之處在于， <xref:microsoft.quantum.intrinsic.r> 旋轉角度會指定為類型的兩個輸入，並以 `Int` dyadic 的分數來轉譯。</span><span class="sxs-lookup"><span data-stu-id="17009-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="17009-179">因此， `RFrac` 有簽章 `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-180">它會執行單一 qubit 的單一 $ \exp (i \pi k \sigma/2 ^ n) $，其中 $ \sigma $ 是對應至第一個引數的 Pauli 矩陣，$k $ 是第二個引數，而 $n $ 是第三個引數。</span><span class="sxs-lookup"><span data-stu-id="17009-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="17009-181">`RFrac(_,k,n,_)`與相同， `R(_,-πk/2^n,_)` 請注意角度是分數的*負值*。</span><span class="sxs-lookup"><span data-stu-id="17009-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="17009-182">作業會 <xref:microsoft.quantum.intrinsic.rx> 執行圍繞 Pauli $X $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="17009-183">它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-184">`Rx(_, _)` 與 `R(PauliX, _, _)` 相同。</span><span class="sxs-lookup"><span data-stu-id="17009-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="17009-185">作業會 <xref:microsoft.quantum.intrinsic.ry> 執行圍繞 Pauli $Y $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="17009-186">它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-187">`Ry(_, _)` 與 `R(PauliY,_ , _)` 相同。</span><span class="sxs-lookup"><span data-stu-id="17009-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="17009-188">作業會 <xref:microsoft.quantum.intrinsic.rz> 執行圍繞 Pauli $Z $ 軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="17009-189">它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-190">`Rz(_, _)` 與 `R(PauliZ, _, _)` 相同。</span><span class="sxs-lookup"><span data-stu-id="17009-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="17009-191">作業會 <xref:microsoft.quantum.intrinsic.r1> 依據指定的數量，在 $ \ket {1} $ （$-$1 eigenstate of $Z $）上執行旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="17009-192">它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-193">`R1(phi,_)`與後面的相同 `R(PauliZ,phi,_)` `R(PauliI,-phi,_)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="17009-194">作業會依照 <xref:microsoft.quantum.intrinsic.r1frac> Z = 1 eigenstate 的指定數量來執行小數旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="17009-195">它具有簽章 `((Int,Int, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-196">`R1Frac(k,n,_)`與後面的相同 `RFrac(PauliZ,-k.n+1,_)` `RFrac(PauliI,k,n+1,_)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="17009-197"> (圍繞 Pauli $Z $ 軸的旋轉作業範例，在此實例中，) 對應至 Bloch 球體如下所示：</span><span class="sxs-lookup"><span data-stu-id="17009-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![對應至 Bloch 球體的旋轉作業](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="17009-199">多 Qubit 作業</span><span class="sxs-lookup"><span data-stu-id="17009-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="17009-200">除了上述的單一 qubit 作業，序言也會定義數個多 qubit 的作業。</span><span class="sxs-lookup"><span data-stu-id="17009-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="17009-201">首先，此作業會 <xref:microsoft.quantum.intrinsic.cnot> 執行標準控制的網 `NOT` 關、\begin{equation} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="17009-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="17009-202">\end{equation} 它有簽章 `((Qubit, Qubit) => Unit is Adj + Ctl)` ，代表 $ \operatorname{CNOT} $ act unitarily 在兩個個別 qubits 上。</span><span class="sxs-lookup"><span data-stu-id="17009-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="17009-203">`CNOT(q1, q2)` 與 `(Controlled X)([q1], q2)` 相同。</span><span class="sxs-lookup"><span data-stu-id="17009-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="17009-204">因為 `Controlled` 仿函數允許在暫存器上控制，所以我們使用陣列常值 `[q1]` 來表示我們只需要一個控制項。</span><span class="sxs-lookup"><span data-stu-id="17009-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="17009-205">作業 <xref:microsoft.quantum.intrinsic.ccnot> 會執行雙向控制的 NOT 閘道，有時也稱為 Toffoli 閘道。</span><span class="sxs-lookup"><span data-stu-id="17009-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="17009-206">它具有簽章 `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-207">`CCNOT(q1, q2, q3)` 與 `(Controlled X)([q1, q2], q3)` 相同。</span><span class="sxs-lookup"><span data-stu-id="17009-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="17009-208">作業會 <xref:microsoft.quantum.intrinsic.swap> 交換兩個 qubits 的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="17009-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="17009-209">也就是說，它會實作為單一矩陣 \begin{equation} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="17009-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="17009-210">\end{equation} 它有簽章 `((Qubit, Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="17009-211">`SWAP(q1,q2)`相當於 `CNOT(q1, q2)` 後面接著 `CNOT(q2, q1)` 和的 `CNOT(q1, q2)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="17009-212">交換網*關與重新*排列具有類型之變數的元素不同 `Qubit[]` 。</span><span class="sxs-lookup"><span data-stu-id="17009-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="17009-213">套用 `SWAP(q1, q2)` 會導致和所參考之 qubits 狀態的變更 `q1` `q2` ，而 `let swappedRegister = [q2, q1];` 只會影響我們參考這些 qubits 的方式。</span><span class="sxs-lookup"><span data-stu-id="17009-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="17009-214">此外， `(Controlled SWAP)([q0], (q1, q2))` 允許 `SWAP` 在第三個 qubit 的狀態下進行條件，我們無法藉由重新排列元素來表示。</span><span class="sxs-lookup"><span data-stu-id="17009-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="17009-215">受控制的交換閘道（也稱為 Fredkin 閘道）功能強大，足以包含所有的傳統計算。</span><span class="sxs-lookup"><span data-stu-id="17009-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="17009-216">最後，序言會提供兩個作業來代表多 qubit Pauli 運算子的指數。</span><span class="sxs-lookup"><span data-stu-id="17009-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="17009-217">作業會 <xref:microsoft.quantum.intrinsic.exp> 根據 Pauli 矩陣的張量產品來執行旋轉，如多 qubit 的單一 \Begin{equation} \operatorname{Exp} 所表示 ( \vec{\sigma}、\phi) \mathrel{： =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right) 、\end{equation}，其中 $ \vec{\sigma} = ( \ sigma_0、\ sigma_1、\dots ..、\ sigma_n) $ 是一系列的單一 Qubit Pauli 運算子，其中 $ \phi $ 是一個角度。</span><span class="sxs-lookup"><span data-stu-id="17009-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="17009-218">`Exp`旋轉會將 $ \vec{\sigma} $ 表示為元素的陣列 `Pauli` ，使其具有簽章 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="17009-219">作業會 <xref:microsoft.quantum.intrinsic.expfrac> 使用上述的 dyadic 分數標記法來執行相同的旋轉。</span><span class="sxs-lookup"><span data-stu-id="17009-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="17009-220">它具有簽章 `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="17009-221">Pauli 運算子的張量產品指數與指數運算子 Pauli 的張量產品不同。</span><span class="sxs-lookup"><span data-stu-id="17009-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="17009-222">也就是說，$e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $。</span><span class="sxs-lookup"><span data-stu-id="17009-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="17009-223">量測</span><span class="sxs-lookup"><span data-stu-id="17009-223">Measurements</span></span> ###

<span data-ttu-id="17009-224">測量時，所測量之運算子的 + 1 eigenvalue 會對應至 `Zero` 結果，而-1 會 eigenvalue 至 `One` 結果。</span><span class="sxs-lookup"><span data-stu-id="17009-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="17009-225">雖然此慣例看似奇怪，但它有兩個非常好用的優點。</span><span class="sxs-lookup"><span data-stu-id="17009-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="17009-226">首先，觀察結果 $ \ket {0} $ 會以 `Result` 值表示 `Zero` ，而觀察 $ \ket $ 則會 {1} 對應至 `One` 。</span><span class="sxs-lookup"><span data-stu-id="17009-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="17009-227">其次，我們可以寫出 eigenvalue $ \lambda $ 的對應結果，$r $ is $ \lambda = (-1) ^ r $。</span><span class="sxs-lookup"><span data-stu-id="17009-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="17009-228">量測作業不支援 `Adjoint` 或 `Controlled` 仿函數。</span><span class="sxs-lookup"><span data-stu-id="17009-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="17009-229">作業會 <xref:microsoft.quantum.intrinsic.measure> 在 Pauli 運算子的指定產品中，執行一或多個 qubits 的聯合測量。</span><span class="sxs-lookup"><span data-stu-id="17009-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="17009-230">如果 Pauli 陣列和 qubit 陣列的長度不同，則作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="17009-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="17009-231">`Measure`具有簽章 `((Pauli[], Qubit[]) => Result)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="17009-232">請注意，聯合測量與個別測量每個 qubit 的方式不同。</span><span class="sxs-lookup"><span data-stu-id="17009-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="17009-233">例如，請考慮 state $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $。</span><span class="sxs-lookup"><span data-stu-id="17009-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="17009-234">逐一測量 $Z _0 $ 和 $Z _1 $，我們得到 $r _0 = $1 和 $r _1 = $1 的結果。</span><span class="sxs-lookup"><span data-stu-id="17009-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="17009-235">測量 $Z _0 Z_1 $，我們取得單一結果 $r _ {\textrm{joint}} = $0，代表 $ \ket $ 的 pairity {11} 是正數。</span><span class="sxs-lookup"><span data-stu-id="17009-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="17009-236">以不同的方式放置 $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}} ) $。</span><span class="sxs-lookup"><span data-stu-id="17009-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="17009-237">嚴重的是，因為我們*只*會從這項測量中學習同位檢查，所以會保留正則兩者的 2 2-qubit 狀態之間的重迭中所代表的任何配量資訊，$ \ket {00} $ 和 $ \ket {11} $。</span><span class="sxs-lookup"><span data-stu-id="17009-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="17009-238">此屬性稍後會很重要，因為我們會討論錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="17009-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="17009-239">為了方便起見，序言也提供兩個其他作業來測量 qubits。</span><span class="sxs-lookup"><span data-stu-id="17009-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="17009-240">首先，由於執行單一 qubit 測量非常常見，序言會定義此案例的速記。</span><span class="sxs-lookup"><span data-stu-id="17009-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="17009-241">作業會 <xref:microsoft.quantum.intrinsic.m> 測量單一 qubit 上的 Pauli $Z $ 運算子，並具有簽章 `(Qubit => Result)` 。</span><span class="sxs-lookup"><span data-stu-id="17009-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="17009-242">`M(q)` 相當於 `Measure([PauliZ], [q])`。</span><span class="sxs-lookup"><span data-stu-id="17009-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="17009-243">會在 <xref:microsoft.quantum.measurement.multim> 每個 qubits 陣列上*分別*測量 Pauli $Z $ 運算子，並傳回*array* `Result` 為每個 qubit 取得的值陣列。</span><span class="sxs-lookup"><span data-stu-id="17009-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="17009-244">在某些情況下，可以將此優化。</span><span class="sxs-lookup"><span data-stu-id="17009-244">In some cases this can be optimized.</span></span> <span data-ttu-id="17009-245">它具有簽章 (`Qubit[] => Result[])` 。</span><span class="sxs-lookup"><span data-stu-id="17009-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="17009-246">`MultiM(qs)`相當於：</span><span class="sxs-lookup"><span data-stu-id="17009-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="17009-247">擴充功能和作業</span><span class="sxs-lookup"><span data-stu-id="17009-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="17009-248">此外，序言會在 .NET 層級定義一組豐富的數學和類型轉換函式，以便在程式碼中使用 Q# 。</span><span class="sxs-lookup"><span data-stu-id="17009-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="17009-249">例如， <xref:microsoft.quantum.math> 命名空間會定義有用的作業，例如 <xref:microsoft.quantum.math.sin> 和 <xref:microsoft.quantum.math.log> 。</span><span class="sxs-lookup"><span data-stu-id="17009-249">For instance, the <xref:microsoft.quantum.math> namespace defines useful operations such as <xref:microsoft.quantum.math.sin> and <xref:microsoft.quantum.math.log>.</span></span>
<span data-ttu-id="17009-250">配量開發工具組所提供的實現會使用傳統 .NET 基類庫，因此可能牽涉到配量程式與其傳統驅動程式之間的額外通訊往返。</span><span class="sxs-lookup"><span data-stu-id="17009-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="17009-251">雖然這不會對本機模擬器造成問題，但在使用遠端模擬器或實際硬體做為目的電腦時，這可能會造成效能問題。</span><span class="sxs-lookup"><span data-stu-id="17009-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="17009-252">話雖如此，個別目的電腦可以藉由使用更有效率的特定系統版本來覆寫這些作業，以降低對效能的影響。</span><span class="sxs-lookup"><span data-stu-id="17009-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="17009-253">數學</span><span class="sxs-lookup"><span data-stu-id="17009-253">Math</span></span> ###

<span data-ttu-id="17009-254"><xref:microsoft.quantum.math>命名空間會從 .net 基類庫的[ `System.Math` 類別](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)提供許多有用的函式。</span><span class="sxs-lookup"><span data-stu-id="17009-254">The <xref:microsoft.quantum.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="17009-255">這些函式的使用方式與其他任何 Q# 函數相同：</span><span class="sxs-lookup"><span data-stu-id="17009-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="17009-256">其中 .NET 靜態方法已根據其引數的型別多載，對應的函式 Q# 會以後置詞標注，以指出其輸入的型別：</span><span class="sxs-lookup"><span data-stu-id="17009-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="17009-257">位運算</span><span class="sxs-lookup"><span data-stu-id="17009-257">Bitwise Operations</span></span> ###

<span data-ttu-id="17009-258">最後， <xref:microsoft.quantum.bitwise> 命名空間提供數個實用的函式，可透過位運算子來操作整數。</span><span class="sxs-lookup"><span data-stu-id="17009-258">Finally, the <xref:microsoft.quantum.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="17009-259">例如，會傳回 <xref:microsoft.quantum.bitwise.parity> 整數的位同位檢查，做為另一個整數。</span><span class="sxs-lookup"><span data-stu-id="17009-259">For instance, <xref:microsoft.quantum.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
