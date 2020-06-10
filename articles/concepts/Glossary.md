---
title: 量子運算詞彙
description: 用於量子運算的常見詞彙、動作和物件的詞彙。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630097"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="a091a-103">量子運算詞彙</span><span class="sxs-lookup"><span data-stu-id="a091a-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="a091a-104">Adjoint</span><span class="sxs-lookup"><span data-stu-id="a091a-104">Adjoint</span></span>

<span data-ttu-id="a091a-105">[運算](xref:microsoft.quantum.glossary#operation)的複雜共軛轉置。</span><span class="sxs-lookup"><span data-stu-id="a091a-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="a091a-106">針對實作為[單一](xref:microsoft.quantum.glossary#unitary-operator)運算子的作業，adjoint 是運算的反向，並以 dagger 符號表示。</span><span class="sxs-lookup"><span data-stu-id="a091a-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="a091a-107">例如，如果作業 `U` 表示 $U 的單一運算子 $ ，則 `Adjoint U` 表示 $U ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="a091a-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="a091a-108">如需詳細資訊，請參閱[Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。</span><span class="sxs-lookup"><span data-stu-id="a091a-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="a091a-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="a091a-109">Ancilla</span></span>

<span data-ttu-id="a091a-110">一種[qubit](xref:microsoft.quantum.glossary#qubit) ，可作為量子電腦的暫存記憶體，並視需要配置和解除配置。</span><span class="sxs-lookup"><span data-stu-id="a091a-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="a091a-111">如需詳細資訊，請參閱[多個 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="a091a-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="a091a-112">鐘州</span><span class="sxs-lookup"><span data-stu-id="a091a-112">Bell state</span></span>

<span data-ttu-id="a091a-113">兩個 qubits 的四個特定最常[光子](xref:microsoft.quantum.glossary#entanglement)配量[狀態](xref:microsoft.quantum.glossary#quantum-state)之一。</span><span class="sxs-lookup"><span data-stu-id="a091a-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="a091a-114">四個狀態定義為 $ \ket { \ Beta_ {ij } } = （\Mathbb{I } \Otimes X ^ iZ ^ j）（\ket{00 } + \ket{11 } ）/\sqrt{2 } $。</span><span class="sxs-lookup"><span data-stu-id="a091a-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="a091a-115">鐘狀態也稱為[EPR 配對](xref:microsoft.quantum.glossary#epr-pair)。</span><span class="sxs-lookup"><span data-stu-id="a091a-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="a091a-116">Bloch 球體</span><span class="sxs-lookup"><span data-stu-id="a091a-116">Bloch sphere</span></span>

<span data-ttu-id="a091a-117">單一[qubit](xref:microsoft.quantum.glossary#qubit) [量子狀態](xref:microsoft.quantum.glossary#quantum-state)的圖形表示，做為三維單位球體中的點。</span><span class="sxs-lookup"><span data-stu-id="a091a-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="a091a-118">如需詳細資訊，請參閱[使用 Bloch 球體視覺化 Qubits 和轉換](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。</span><span class="sxs-lookup"><span data-stu-id="a091a-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="a091a-119">多次</span><span class="sxs-lookup"><span data-stu-id="a091a-119">Callable</span></span>

<span data-ttu-id="a091a-120">Q # 語言[中的作業或](xref:microsoft.quantum.glossary#operation)[函數](xref:microsoft.quantum.glossary#function)。</span><span class="sxs-lookup"><span data-stu-id="a091a-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="a091a-121">如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="a091a-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="a091a-122">Clifford 群組</span><span class="sxs-lookup"><span data-stu-id="a091a-122">Clifford group</span></span>

<span data-ttu-id="a091a-123">這組作業會佔用[Bloch 球體](xref:microsoft.quantum.glossary#bloch-sphere)的 octants，以及[Pauli 運算子](xref:microsoft.quantum.glossary#pauli-operators)的效果排列。</span><span class="sxs-lookup"><span data-stu-id="a091a-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="a091a-124">其中包括[$X $ ](xref:microsoft.quantum.intrinsic.x)、 [$Y $ ](xref:microsoft.quantum.intrinsic.y)、 [$Z $ ](xref:microsoft.quantum.intrinsic.z)、 [$H $ ](xref:microsoft.quantum.intrinsic.h)和[$S $ ](xref:microsoft.quantum.intrinsic.s)的作業。</span><span class="sxs-lookup"><span data-stu-id="a091a-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="a091a-125">管理</span><span class="sxs-lookup"><span data-stu-id="a091a-125">Controlled</span></span>

<span data-ttu-id="a091a-126">接受一或多個[qubits](xref:microsoft.quantum.glossary#qubit)做為目標[作業的啟用程式的量子作業](xref:microsoft.quantum.glossary#operation)。</span><span class="sxs-lookup"><span data-stu-id="a091a-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="a091a-127">如需詳細資訊，請參閱[控制和 adjoint 作業](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。</span><span class="sxs-lookup"><span data-stu-id="a091a-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="a091a-128">Dirac 標記法</span><span class="sxs-lookup"><span data-stu-id="a091a-128">Dirac Notation</span></span>

<span data-ttu-id="a091a-129">符號速記，可簡化[量子狀態](xref:microsoft.quantum.glossary#quantum-state)的標記法，亦稱為*bra-ket* notation。</span><span class="sxs-lookup"><span data-stu-id="a091a-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="a091a-130">*Bra*部分代表一個資料列向量，例如 $ \bra{A } = \begin{ bmatrix } a {_1 } & a {_2 } \end{ bmatrix } $，而*ket*部分代表一個資料行向量，$ \ket{B } = \begin{ bmatrix } B {_1 } \\ \\ B {_2 } \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="a091a-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="a091a-131">如需詳細資訊，請參閱[Dirac 標記法](xref:microsoft.quantum.concepts.dirac)。</span><span class="sxs-lookup"><span data-stu-id="a091a-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="a091a-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="a091a-132">Eigenvalue</span></span>

<span data-ttu-id="a091a-133">轉換的應用程式變更指定轉換的[eigenvector](xref:microsoft.quantum.glossary#eigenvector)大小的因數。</span><span class="sxs-lookup"><span data-stu-id="a091a-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="a091a-134">假設有一個方形矩陣 $M $ 和一個 eigenvector $v $ ，然後 $Mv = cv $ ，其中 $c $ 是 eigenvalue，而且可以是任何引數的複數。</span><span class="sxs-lookup"><span data-stu-id="a091a-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="a091a-135">如需詳細資訊，請參閱[Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。</span><span class="sxs-lookup"><span data-stu-id="a091a-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="a091a-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="a091a-136">Eigenvector</span></span>

<span data-ttu-id="a091a-137">向量，其方向不會由指定的轉換變更，且其大小會由對應于該向量之[eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)的因數來改變。</span><span class="sxs-lookup"><span data-stu-id="a091a-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="a091a-138">假設有一個方形矩陣 $M $ 和一個 eigenvalue $c $ ，然後 $Mv = cv $ ，其中 $v $ 是矩陣的 eigenvector，而且可以是任何引數的複數。</span><span class="sxs-lookup"><span data-stu-id="a091a-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="a091a-139">如需詳細資訊，請參閱[Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。</span><span class="sxs-lookup"><span data-stu-id="a091a-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="a091a-140">糾纏</span><span class="sxs-lookup"><span data-stu-id="a091a-140">Entanglement</span></span>

<span data-ttu-id="a091a-141">配量粒子（例如[qubits](xref:microsoft.quantum.glossary#qubit)）可以連接或*光子*，使其無法彼此獨立地進行描述。</span><span class="sxs-lookup"><span data-stu-id="a091a-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="a091a-142">它們的測量結果會相互關聯，即使它們的距離是無限的。</span><span class="sxs-lookup"><span data-stu-id="a091a-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="a091a-143">會任何牽連是[測量](xref:microsoft.quantum.glossary#measurement)qubit[狀態](xref:microsoft.quantum.glossary#quantum-state)時不可或缺的。</span><span class="sxs-lookup"><span data-stu-id="a091a-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="a091a-144">如需詳細資訊，請參閱[Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。</span><span class="sxs-lookup"><span data-stu-id="a091a-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="a091a-145">EPR 配對</span><span class="sxs-lookup"><span data-stu-id="a091a-145">EPR pair</span></span>

<span data-ttu-id="a091a-146">兩個[qubits](xref:microsoft.quantum.glossary#qubit)的四個特定最常光子配量[狀態](xref:microsoft.quantum.glossary#quantum-state)之一。</span><span class="sxs-lookup"><span data-stu-id="a091a-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="a091a-147">四個狀態定義為 $ \ket { \ Beta_ {ij } } = （\Mathbb{1 } \Otimes X ^ iZ ^ j）（\ket{00 } + \ket{11 } ）/\sqrt{2 } $。</span><span class="sxs-lookup"><span data-stu-id="a091a-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="a091a-148">EPR 配對也稱為「[鐘」狀態](xref:microsoft.quantum.glossary#bell-state)</span><span class="sxs-lookup"><span data-stu-id="a091a-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="a091a-149">改革</span><span class="sxs-lookup"><span data-stu-id="a091a-149">Evolution</span></span>

<span data-ttu-id="a091a-150">[量子狀態](xref:microsoft.quantum.glossary#quantum-state)隨著時間變更的方式。</span><span class="sxs-lookup"><span data-stu-id="a091a-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="a091a-151">如需詳細資訊，請參閱[矩陣指數](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。</span><span class="sxs-lookup"><span data-stu-id="a091a-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="a091a-152">函式</span><span class="sxs-lookup"><span data-stu-id="a091a-152">Function</span></span>
<span data-ttu-id="a091a-153">Q # 語言中純粹為傳統（非配量）的副程式類型。</span><span class="sxs-lookup"><span data-stu-id="a091a-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="a091a-154">雖然在配量演算法中使用函式，但它們無法對[qubits](xref:microsoft.quantum.glossary#qubit)或呼叫[作業](xref:microsoft.quantum.glossary#operation)採取動作。</span><span class="sxs-lookup"><span data-stu-id="a091a-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="a091a-155">如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="a091a-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="a091a-156">蓋</span><span class="sxs-lookup"><span data-stu-id="a091a-156">Gate</span></span>

<span data-ttu-id="a091a-157">適用[于量子作業](xref:microsoft.quantum.glossary#operation)的舊版詞彙，以傳統邏輯閘道的概念為基礎。</span><span class="sxs-lookup"><span data-stu-id="a091a-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="a091a-158">配量[線路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是閘道（或作業）的網路，以傳統邏輯電路的類似概念為基礎。</span><span class="sxs-lookup"><span data-stu-id="a091a-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="a091a-159">全域階段</span><span class="sxs-lookup"><span data-stu-id="a091a-159">Global phase</span></span>

<span data-ttu-id="a091a-160">當兩個[狀態](xref:microsoft.quantum.glossary#quantum-state)與複數 $e ^ {i $ 之間的倍數相同時 \phi } ，就表示它們的最大值與全域階段不同。</span><span class="sxs-lookup"><span data-stu-id="a091a-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="a091a-161">與本機階段不同的是，全域階段無法透過任何[測量](xref:microsoft.quantum.glossary#measurement)觀察到。</span><span class="sxs-lookup"><span data-stu-id="a091a-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="a091a-162">如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="a091a-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="a091a-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="a091a-163">Hadamard</span></span>

<span data-ttu-id="a091a-164">Hadamard 作業（也稱為 Hadamard 閘道或轉換）會在單一[qubit](xref:microsoft.quantum.glossary#qubit)上運作，並將它放在 $ \ket{0 $ 或 $ \ket{1 $ 的偶數[重迭](xref:microsoft.quantum.glossary#superposition)中（ } } 如果 qubit 一開始是在 $ \ket{0 } $ 狀態中）。</span><span class="sxs-lookup"><span data-stu-id="a091a-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="a091a-165">在 Q # 中，這項作業是由預先定義的作業所套用 [`H`](xref:microsoft.quantum.intrinsic.h) 。</span><span class="sxs-lookup"><span data-stu-id="a091a-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="a091a-166">固定</span><span class="sxs-lookup"><span data-stu-id="a091a-166">Immutable</span></span>

<span data-ttu-id="a091a-167">無法變更其值的變數。</span><span class="sxs-lookup"><span data-stu-id="a091a-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="a091a-168">Q # 中的不可變變數是使用關鍵字所建立 `let` 。</span><span class="sxs-lookup"><span data-stu-id="a091a-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="a091a-169">若要宣告*可以*變更的變數，請使用[mutable](xref:microsoft.quantum.glossary#immutable)關鍵字來宣告和 `set` 關鍵字，以修改值。</span><span class="sxs-lookup"><span data-stu-id="a091a-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="a091a-170">測量</span><span class="sxs-lookup"><span data-stu-id="a091a-170">Measurement</span></span>

<span data-ttu-id="a091a-171">[Qubit](xref:microsoft.quantum.glossary#qubit) （或一組 qubits）的操作，其會產生觀察結果，實際上是取得古典位。</span><span class="sxs-lookup"><span data-stu-id="a091a-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="a091a-172">如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。</span><span class="sxs-lookup"><span data-stu-id="a091a-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="a091a-173">可變動</span><span class="sxs-lookup"><span data-stu-id="a091a-173">Mutable</span></span>

<span data-ttu-id="a091a-174">其值在建立之後可能會變更的變數。</span><span class="sxs-lookup"><span data-stu-id="a091a-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="a091a-175">Q # 中的可變變數是使用關鍵字來宣告 `mutable` ，並使用關鍵字進行修改 `set` 。</span><span class="sxs-lookup"><span data-stu-id="a091a-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="a091a-176">使用關鍵字建立的變數 `let` 是[不可變](xref:microsoft.quantum.glossary#immutable)的，而且無法變更其值。</span><span class="sxs-lookup"><span data-stu-id="a091a-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="a091a-177">命名空間</span><span class="sxs-lookup"><span data-stu-id="a091a-177">Namespace</span></span>

<span data-ttu-id="a091a-178">相關名稱集合的標籤（亦即[作業](xref:microsoft.quantum.glossary#operation) [、函式和](xref:microsoft.quantum.glossary#function)[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)）。</span><span class="sxs-lookup"><span data-stu-id="a091a-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="a091a-179">例如，命名空間 [ [Microsoft 量子. 準備](xref:microsoft.quantum.preparation)標籤] 會標示標準程式庫中定義的所有符號，以協助準備初始狀態。</span><span class="sxs-lookup"><span data-stu-id="a091a-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="a091a-180">操作</span><span class="sxs-lookup"><span data-stu-id="a091a-180">Operation</span></span>

<span data-ttu-id="a091a-181">Q # 中的基本量子執行單位。</span><span class="sxs-lookup"><span data-stu-id="a091a-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="a091a-182">它大致等同于 C、c + + 或 Python 中的函式，或是 c # 或 JAVA 中的靜態方法。</span><span class="sxs-lookup"><span data-stu-id="a091a-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="a091a-183">如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="a091a-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="a091a-184">操作員應用程式</span><span class="sxs-lookup"><span data-stu-id="a091a-184">Operator application</span></span>

<span data-ttu-id="a091a-185">執行量子作業。</span><span class="sxs-lookup"><span data-stu-id="a091a-185">Performing a quantum operation.</span></span> <span data-ttu-id="a091a-186">這通常會將單一矩陣套用至目前的量子狀態向量。</span><span class="sxs-lookup"><span data-stu-id="a091a-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="a091a-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="a091a-187">Oracle</span></span>

<span data-ttu-id="a091a-188">副程式，在執行時間提供資料相依的資訊給量子演算法。</span><span class="sxs-lookup"><span data-stu-id="a091a-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="a091a-189">一般來說，其目標是要提供對應于重迭中輸入的輸出[重迭](xref:microsoft.quantum.glossary#superposition)。</span><span class="sxs-lookup"><span data-stu-id="a091a-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="a091a-190">如需詳細資訊，請參閱[Oracles](xref:microsoft.quantum.libraries.data-structures#oracles)。</span><span class="sxs-lookup"><span data-stu-id="a091a-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="a091a-191">部分應用程式</span><span class="sxs-lookup"><span data-stu-id="a091a-191">Partial application</span></span>

<span data-ttu-id="a091a-192">呼叫[沒有所有](xref:microsoft.quantum.glossary#operation)必要[輸入的函式或作業](xref:microsoft.quantum.glossary#function)。</span><span class="sxs-lookup"><span data-stu-id="a091a-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="a091a-193">這會[傳回新的可呼叫](xref:microsoft.quantum.glossary#callable)，其只需要在未來的應用程式期間提供遺漏的參數（以底線表示）。</span><span class="sxs-lookup"><span data-stu-id="a091a-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="a091a-194">例如，假設函式可以 `MyFunc(x : int, y : int) : int {return x + y;}` 部分套用至新的函式 `let NewFunc = MyFunc(_, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="a091a-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="a091a-195">然後，您可以在稍後使用遺漏參數來呼叫新的函式，傳回 `NewFunc(2)` 值*5*。</span><span class="sxs-lookup"><span data-stu-id="a091a-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="a091a-196">如需詳細資訊，請參閱[部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)。</span><span class="sxs-lookup"><span data-stu-id="a091a-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="a091a-197">Pauli 運算子</span><span class="sxs-lookup"><span data-stu-id="a091a-197">Pauli operators</span></span>

<span data-ttu-id="a091a-198">一組三個 2 x 2 個單一矩陣，稱為 `X` `Y` 和 `Z` 量子作業。</span><span class="sxs-lookup"><span data-stu-id="a091a-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="a091a-199">「身分識別矩陣」（$I $ ）通常也會包含在集合中。</span><span class="sxs-lookup"><span data-stu-id="a091a-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="a091a-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $，$X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $，$Y = \begin{ bmatrix } 0 &-i \\ \\ i & 0 \end{ bmatrix } $，$Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="a091a-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="a091a-201">如需詳細資訊，請參閱[單一 qubit 作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。</span><span class="sxs-lookup"><span data-stu-id="a091a-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="a091a-202">量子線路圖</span><span class="sxs-lookup"><span data-stu-id="a091a-202">Quantum circuit diagram</span></span>

<span data-ttu-id="a091a-203">以圖形方式表示簡單量副程式之[作業](xref:microsoft.quantum.glossary#operation)（或網[關](xref:microsoft.quantum.glossary#gate)）順序的方法，例如</span><span class="sxs-lookup"><span data-stu-id="a091a-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![範例電路圖表](~/media/qpe.png)<span data-ttu-id="a091a-205">.</span><span class="sxs-lookup"><span data-stu-id="a091a-205">.</span></span> 

<span data-ttu-id="a091a-206">如需詳細資訊，請參閱[量子線路](xref:microsoft.quantum.concepts.circuits)。</span><span class="sxs-lookup"><span data-stu-id="a091a-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="a091a-207">量子程式庫</span><span class="sxs-lookup"><span data-stu-id="a091a-207">Quantum libraries</span></span>

<span data-ttu-id="a091a-208">用於建立 Q # 程式的[作業](xref:microsoft.quantum.glossary#operation) [、函](xref:microsoft.quantum.glossary#function)式和[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)集合。</span><span class="sxs-lookup"><span data-stu-id="a091a-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="a091a-209">預設會安裝[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)。</span><span class="sxs-lookup"><span data-stu-id="a091a-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="a091a-210">其他可用的程式庫包括[化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)、[數值](xref:microsoft.quantum.numerics.intro)程式庫和[機器學習程式庫](xref:microsoft.quantum.machine-learning.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="a091a-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="a091a-211">量子狀態</span><span class="sxs-lookup"><span data-stu-id="a091a-211">Quantum state</span></span>

<span data-ttu-id="a091a-212">隔離的量子系統的精確狀態，可從中解壓縮[測量](xref:microsoft.quantum.glossary#measurement)機率。</span><span class="sxs-lookup"><span data-stu-id="a091a-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="a091a-213">在量子運算中，配量模擬器會使用這項資訊來模擬 qubits 如何回應作業。</span><span class="sxs-lookup"><span data-stu-id="a091a-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="a091a-214">如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="a091a-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="a091a-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="a091a-215">Qubit</span></span>

<span data-ttu-id="a091a-216">一種基本的量子資訊單位，類似于傳統計算中的*一點*。</span><span class="sxs-lookup"><span data-stu-id="a091a-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="a091a-217">如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="a091a-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="a091a-218">重複直到-成功</span><span class="sxs-lookup"><span data-stu-id="a091a-218">Repeat-until-success</span></span>

<span data-ttu-id="a091a-219">機率成功的量子演算法。</span><span class="sxs-lookup"><span data-stu-id="a091a-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="a091a-220">失敗時，常式會重試直到成功為止（或已達到限制）。</span><span class="sxs-lookup"><span data-stu-id="a091a-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="a091a-221">如需詳細資訊，請參閱[重複直到成功（ru）](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="a091a-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="a091a-222">標準程式庫</span><span class="sxs-lookup"><span data-stu-id="a091a-222">Standard libraries</span></span>

<span data-ttu-id="a091a-223">在安裝期間，與 Q # 編譯器一起安裝的[作業](xref:microsoft.quantum.glossary#operation) [、函](xref:microsoft.quantum.glossary#function)式和[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)。</span><span class="sxs-lookup"><span data-stu-id="a091a-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="a091a-224">標準程式庫的執行與目的電腦無關。</span><span class="sxs-lookup"><span data-stu-id="a091a-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="a091a-225">如需詳細資訊，請參閱[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)。</span><span class="sxs-lookup"><span data-stu-id="a091a-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="a091a-226">重迭</span><span class="sxs-lookup"><span data-stu-id="a091a-226">Superposition</span></span>

<span data-ttu-id="a091a-227">量子計算中的概念是， [qubit](xref:microsoft.quantum.glossary#qubit)是兩個狀態的線性組合，$ \ket{0 } $ 和 $ \ket{1 } $，直到[測量](xref:microsoft.quantum.glossary#measurement)為止。</span><span class="sxs-lookup"><span data-stu-id="a091a-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="a091a-228">如需詳細資訊，請參閱瞭解配量[計算](xref:microsoft.quantum.overview.understanding)。</span><span class="sxs-lookup"><span data-stu-id="a091a-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="a091a-229">目的電腦</span><span class="sxs-lookup"><span data-stu-id="a091a-229">Target machine</span></span>

<span data-ttu-id="a091a-230">將抽象的量副程式降低到硬體或模擬的編譯目標。</span><span class="sxs-lookup"><span data-stu-id="a091a-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="a091a-231">這通常包括重新寫入的許多用途，包括閘道更換、錯誤更正的編碼、幾何版面配置等等。</span><span class="sxs-lookup"><span data-stu-id="a091a-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="a091a-232">如需詳細資訊，請參閱[量子模擬器和主機應用程式](xref:microsoft.quantum.machines)。</span><span class="sxs-lookup"><span data-stu-id="a091a-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="a091a-233">遙傳</span><span class="sxs-lookup"><span data-stu-id="a091a-233">Teleportation</span></span>

<span data-ttu-id="a091a-234">一種方法，可使用[會任何牽連](xref:microsoft.quantum.glossary#entanglement)和[測量](xref:microsoft.quantum.glossary#measurement)，將一個[qubit](xref:microsoft.quantum.glossary#qubit)的資料（或[量子狀態](xref:microsoft.quantum.glossary#quantum-state)）從一個位置重新產生至另一個位置，而不需要實際移動 qubit。</span><span class="sxs-lookup"><span data-stu-id="a091a-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="a091a-235">如需詳細資訊，請參閱[量子線路](xref:microsoft.quantum.concepts.circuits)和各 Kata 的[Katas](xref:microsoft.quantum.overview.katas)。</span><span class="sxs-lookup"><span data-stu-id="a091a-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="a091a-236">Tuple</span><span class="sxs-lookup"><span data-stu-id="a091a-236">Tuple</span></span>

<span data-ttu-id="a091a-237">以逗號分隔的值集合，可作為單一值。</span><span class="sxs-lookup"><span data-stu-id="a091a-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="a091a-238">元組的*類型*是由它所包含的數值型別所定義。</span><span class="sxs-lookup"><span data-stu-id="a091a-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="a091a-239">在 Q # 中，元組是[不可變](xref:microsoft.quantum.glossary#immutable)的，而且可以嵌套、包含陣列，或用於陣列中。</span><span class="sxs-lookup"><span data-stu-id="a091a-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="a091a-240">如需詳細資訊，請參閱[元組類型](xref:microsoft.quantum.guide.types#tuple-types)。</span><span class="sxs-lookup"><span data-stu-id="a091a-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="a091a-241">單一運算子</span><span class="sxs-lookup"><span data-stu-id="a091a-241">Unitary operator</span></span>

<span data-ttu-id="a091a-242">其反向等於其[adjoint](xref:microsoft.quantum.glossary#adjoint)的運算子，亦即 $UU ^ {\dagger } = \id $ 。</span><span class="sxs-lookup"><span data-stu-id="a091a-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="a091a-243">使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="a091a-243">User-defined type</span></span>

<span data-ttu-id="a091a-244">內建或先前定義之類型的集合，可能稱為單一單位。</span><span class="sxs-lookup"><span data-stu-id="a091a-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="a091a-245">如需詳細資訊，請參閱[使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)。</span><span class="sxs-lookup"><span data-stu-id="a091a-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>