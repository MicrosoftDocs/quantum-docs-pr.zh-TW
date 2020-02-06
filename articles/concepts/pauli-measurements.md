---
title: Pauli 測量
description: Pauli 測量
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 300a1ebcfd5d7bca8b025c69adebaad03106433d
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036591"
---
# <a name="pauli-measurements"></a><span data-ttu-id="eca91-103">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="eca91-103">Pauli Measurements</span></span>

<span data-ttu-id="eca91-104">在先前的討論中，我們著重于計算基礎測量。</span><span class="sxs-lookup"><span data-stu-id="eca91-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="eca91-105">事實上，從標記的角度來看，在計量運算中所發生的其他常見測量，在計算基礎測量方面很方便表達。</span><span class="sxs-lookup"><span data-stu-id="eca91-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="eca91-106">當您使用 Q # 時，您會遇到的最常見測量類型可能是*Pauli 測量*，這會將計算基礎測量一般化以包含其他基底的度量，以及不同 qubits 之間的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="eca91-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="eca91-107">在這種情況下，通常會討論測量 Pauli 運算子，通常是 $X、Y、Z $ 或 $Z \otimes Z、X\otimes X、X\otimes Y $ 等等的運算子。</span><span class="sxs-lookup"><span data-stu-id="eca91-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="eca91-108">在 Q # 中，多 qubit 的 Pauli 運算子通常會由 `Pauli[]`類型的陣列來表示。</span><span class="sxs-lookup"><span data-stu-id="eca91-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="eca91-109">例如，若要表示 $X \otimes Z \otimes Y $，您可以使用陣列 `[PauliX, PauliZ, PauliY]`。</span><span class="sxs-lookup"><span data-stu-id="eca91-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="eca91-110">討論 Pauli 運算子方面的測量，特別是在量子錯誤更正的子欄位中。</span><span class="sxs-lookup"><span data-stu-id="eca91-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="eca91-111">在 Q # 中，我們遵循類似的慣例。我們現在會說明這種替代的度量觀點。</span><span class="sxs-lookup"><span data-stu-id="eca91-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="eca91-112">在探究到如何思考 Pauli 測量的詳細資料之前，請考慮測量量子電腦內的單一 qubit 對量子狀態的作用。</span><span class="sxs-lookup"><span data-stu-id="eca91-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="eca91-113">假設我們有一個 $n $-qubit 量子狀態;然後，測量一個 qubit 會立即將該狀態所可能處於 $ 2 ^ n $ 可能性的一半。</span><span class="sxs-lookup"><span data-stu-id="eca91-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="eca91-114">換句話說，測量會將量子狀態投射到兩個半形的其中一個。</span><span class="sxs-lookup"><span data-stu-id="eca91-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="eca91-115">我們可以將我們認為測量的方式一般化，以反映此直覺。</span><span class="sxs-lookup"><span data-stu-id="eca91-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="eca91-116">為了簡潔地識別這些 subspaces，我們需要用來描述它們的語言。</span><span class="sxs-lookup"><span data-stu-id="eca91-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="eca91-117">描述兩個 subspaces 的其中一種方式，是透過只具有兩個唯一特徵值的矩陣來指定它們，慣例是 $ \pm $1。</span><span class="sxs-lookup"><span data-stu-id="eca91-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="eca91-118">如需以這種方式描述 subspaces 的簡單範例，請考慮 $Z $：</span><span class="sxs-lookup"><span data-stu-id="eca91-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="eca91-119">$ $ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="eca91-119">$$ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="eca91-120">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eca91-120">\end{align} $$</span></span>

<span data-ttu-id="eca91-121">藉由讀取 Pauli-$Z $ 矩陣的對角線元素，我們可以看到 $Z $ 有兩個特徵向量，$ \ket{0}$ 和 $ \ket{1}$，其對應的特徵值 $ \pm $1。</span><span class="sxs-lookup"><span data-stu-id="eca91-121">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="eca91-122">因此，如果我們測量 qubit 並取得 `Zero` （對應至 state $ \ket{0}$），我們知道 qubit 的狀態是 $Z $ 運算子的 $ + $1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="eca91-122">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="eca91-123">同樣地，如果我們取得 `One`，我們知道 qubit 的狀態是 $Z $ 的 $-$1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="eca91-123">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="eca91-124">此程式在 Pauli 測量的語言中稱為「測量 Pauli $Z $」，而且完全等同于執行計算基礎測量。</span><span class="sxs-lookup"><span data-stu-id="eca91-124">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="eca91-125">屬於 $Z $ 之單一轉換的任何 $ 2 \ 乘以 $2 矩陣，也都符合此準則。</span><span class="sxs-lookup"><span data-stu-id="eca91-125">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="eca91-126">也就是，我們也可以使用矩陣 $A = U ^ \dagger Z U $，其中 $U $ 是任何其他的單一矩陣，以提供在其 $ \pm $1 特徵向量中定義度量兩個結果的矩陣。</span><span class="sxs-lookup"><span data-stu-id="eca91-126">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="eca91-127">Pauli 量值的標記法會藉由將 $X、Y、Z $ 度量識別為對等的測量，以取得 qubit 中的資訊，來參考這個單一等價項。</span><span class="sxs-lookup"><span data-stu-id="eca91-127">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="eca91-128">為了方便起見，以下提供這些測量。</span><span class="sxs-lookup"><span data-stu-id="eca91-128">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="eca91-129">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="eca91-129">Pauli Measurement</span></span>  |<span data-ttu-id="eca91-130">單一轉換</span><span class="sxs-lookup"><span data-stu-id="eca91-130">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="eca91-131">$Z $</span><span class="sxs-lookup"><span data-stu-id="eca91-131">$Z$</span></span>               | <span data-ttu-id="eca91-132">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-132">$\boldone$</span></span>             |
| <span data-ttu-id="eca91-133">$X $</span><span class="sxs-lookup"><span data-stu-id="eca91-133">$X$</span></span>               | <span data-ttu-id="eca91-134">$H $</span><span class="sxs-lookup"><span data-stu-id="eca91-134">$H$</span></span>                    |
| <span data-ttu-id="eca91-135">$Y $</span><span class="sxs-lookup"><span data-stu-id="eca91-135">$Y$</span></span>               | <span data-ttu-id="eca91-136">$HS ^ {\dagger} $</span><span class="sxs-lookup"><span data-stu-id="eca91-136">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="eca91-137">也就是說，使用這種語言，「量值 $Y $」等同于套用 $HS ^ \dagger $，然後以計算為基礎，其中[`S`](xref:microsoft.quantum.intrinsic.s)是內建的量子作業，有時稱為「階段閘道」，而且可由單一矩陣模擬</span><span class="sxs-lookup"><span data-stu-id="eca91-137">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="eca91-138">$ $ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="eca91-138">$$ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="eca91-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eca91-139">\end{align} $$</span></span>

<span data-ttu-id="eca91-140">這也相當於將 $HS ^ \dagger $ 套用至量子狀態向量，然後測量 $Z $，讓下列作業等同于 `Measure([PauliY], [q]])`：</span><span class="sxs-lookup"><span data-stu-id="eca91-140">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q]])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="eca91-141">接著，轉換回計算基礎，即可找到正確的狀態，這是將 $SH $ 套用至量子狀態向量的數量;在上述程式碼片段中，轉換回計算基礎是使用 `within … apply` 區塊自動處理。</span><span class="sxs-lookup"><span data-stu-id="eca91-141">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="eca91-142">在 Q # 中，我們會假設結果---也就是，從與狀態互動---的傳統資訊是由 `Result` 值所提供 $j \in \\{\texttt{Zero}，\texttt{One}\\} $，指出結果是否在所測量 Pauli 運算子的 $ （-1） ^ j $ eigenspace 中。</span><span class="sxs-lookup"><span data-stu-id="eca91-142">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="eca91-143">多 qubit 測量</span><span class="sxs-lookup"><span data-stu-id="eca91-143">Multiple-qubit measurements</span></span>

<span data-ttu-id="eca91-144">多 qubit Pauli 運算子的度量定義類似，如下所示：</span><span class="sxs-lookup"><span data-stu-id="eca91-144">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="eca91-145">$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ end {bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="eca91-145">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="eca91-146">因此，兩個 Pauli $Z $ 運算子的張量產品會形成一個矩陣，其中包含由 $ + $1 和 $-$1 特徵值組成的兩個空格。</span><span class="sxs-lookup"><span data-stu-id="eca91-146">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="eca91-147">就像單一 qubit 的情況一樣，兩者都構成一半空間，這表示可存取的兩個向量空間一半屬於 $ + $1 eigenspace，而其餘一半則是 $-$1 eigenspace。</span><span class="sxs-lookup"><span data-stu-id="eca91-147">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="eca91-148">一般來說，您可以從張量產品的定義中查看 Pauli-$Z $ operators 的任何張量產品，以及身分識別也會遵守這項功能。</span><span class="sxs-lookup"><span data-stu-id="eca91-148">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="eca91-149">例如：</span><span class="sxs-lookup"><span data-stu-id="eca91-149">For example,</span></span>

<span data-ttu-id="eca91-150">$ $ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 &-1 & 0 \\\\ 0 & 0 & 0 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="eca91-150">$$ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="eca91-151">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eca91-151">\end{align} $$</span></span>

<span data-ttu-id="eca91-152">如前所述，這類矩陣的任何單一轉換也會描述由 $ \pm $1 特徵值標記的兩個半形。</span><span class="sxs-lookup"><span data-stu-id="eca91-152">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="eca91-153">例如，從 $Z = HXH $ 的身分識別 $X \otimes X = H\otimes H （Z\otimes Z） H\otimes H $。</span><span class="sxs-lookup"><span data-stu-id="eca91-153">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="eca91-154">與一個 qubit 的案例類似，所有的雙 qubit Pauli 量值都可以撰寫為 $U ^ \dagger （Z\otimes \id） U $ （適用于 $ 4 \ 次 $4 單一矩陣 $U $）。</span><span class="sxs-lookup"><span data-stu-id="eca91-154">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="eca91-155">我們會列舉下表中的轉換。</span><span class="sxs-lookup"><span data-stu-id="eca91-155">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="eca91-156">在下表中，我們使用 $ \operatorname{SWAP} $ 來表示矩陣 $ $ \begin{align} \operatorname{SWAP} & = \left （\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right） \end{align} $ $ 用來模擬內建函式[`SWAP`](xref:microsoft.quantum.intrinsic)。</span><span class="sxs-lookup"><span data-stu-id="eca91-156">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align} \operatorname{SWAP} & = \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align} $$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="eca91-157">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="eca91-157">Pauli Measurement</span></span>     |<span data-ttu-id="eca91-158">單一轉換</span><span class="sxs-lookup"><span data-stu-id="eca91-158">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="eca91-159">$Z \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-159">$Z \otimes \boldone$</span></span> | <span data-ttu-id="eca91-160">$ \boldone \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-160">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="eca91-161">$Z \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-161">$Z\otimes \boldone$</span></span> | <span data-ttu-id="eca91-162">$ \boldone\otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-162">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="eca91-163">$X \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-163">$X\otimes \boldone$</span></span> | <span data-ttu-id="eca91-164">$H \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-164">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="eca91-165">$Y \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-165">$Y\otimes \boldone$</span></span> | <span data-ttu-id="eca91-166">$HS ^ \dagger\otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="eca91-166">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="eca91-167">$ \boldone \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="eca91-167">$\boldone \otimes Z$</span></span> | <span data-ttu-id="eca91-168">$ \operatorname{SWAP} $</span><span class="sxs-lookup"><span data-stu-id="eca91-168">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="eca91-169">$ \boldone \otimes X $</span><span class="sxs-lookup"><span data-stu-id="eca91-169">$\boldone \otimes X$</span></span> | <span data-ttu-id="eca91-170">$ （H\otimes \boldone） \operatorname{SWAP} $</span><span class="sxs-lookup"><span data-stu-id="eca91-170">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="eca91-171">$ \boldone \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="eca91-171">$\boldone \otimes Y$</span></span> | <span data-ttu-id="eca91-172">$ （HS ^ \dagger\otimes \boldone） \operatorname{SWAP} $</span><span class="sxs-lookup"><span data-stu-id="eca91-172">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="eca91-173">$Z \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="eca91-173">$Z\otimes Z$</span></span> | <span data-ttu-id="eca91-174">$ \operatorname{CNOT}\_{10}$</span><span class="sxs-lookup"><span data-stu-id="eca91-174">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="eca91-175">$X \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="eca91-175">$X\otimes Z$</span></span> | <span data-ttu-id="eca91-176">$ \operatorname{CNOT}\_{10}（H\otimes \boldone） $</span><span class="sxs-lookup"><span data-stu-id="eca91-176">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="eca91-177">$Y \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="eca91-177">$Y\otimes Z$</span></span> | <span data-ttu-id="eca91-178">$ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes \boldone） $</span><span class="sxs-lookup"><span data-stu-id="eca91-178">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="eca91-179">$Z \otimes X $</span><span class="sxs-lookup"><span data-stu-id="eca91-179">$Z\otimes X$</span></span> | <span data-ttu-id="eca91-180">$ \operatorname{CNOT}\_{10}（\boldone\otimes H） $</span><span class="sxs-lookup"><span data-stu-id="eca91-180">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="eca91-181">$X \otimes X $</span><span class="sxs-lookup"><span data-stu-id="eca91-181">$X\otimes X$</span></span> | <span data-ttu-id="eca91-182">$ \operatorname{CNOT}\_{10}（H\otimes H） $</span><span class="sxs-lookup"><span data-stu-id="eca91-182">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="eca91-183">$Y \otimes X $</span><span class="sxs-lookup"><span data-stu-id="eca91-183">$Y\otimes X$</span></span> | <span data-ttu-id="eca91-184">$ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes H） $</span><span class="sxs-lookup"><span data-stu-id="eca91-184">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="eca91-185">$Z \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="eca91-185">$Z\otimes Y$</span></span> | <span data-ttu-id="eca91-186">$ \operatorname{CNOT}\_{10}（\boldone \otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="eca91-186">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="eca91-187">$X \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="eca91-187">$X\otimes Y$</span></span> | <span data-ttu-id="eca91-188">$ \operatorname{CNOT}\_{10}（H\otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="eca91-188">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="eca91-189">$Y \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="eca91-189">$Y\otimes Y$</span></span> | <span data-ttu-id="eca91-190">$ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="eca91-190">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="eca91-191">在這裡， [`CNOT`](xref:microsoft.quantum.intrinsic.cnot)作業會因為下列原因而出現。</span><span class="sxs-lookup"><span data-stu-id="eca91-191">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="eca91-192">不包含 $ \boldone $ 矩陣的每個 Pauli 量值，都相當於單一的，以由上述推理 $Z \otimes Z $。</span><span class="sxs-lookup"><span data-stu-id="eca91-192">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="eca91-193">$Z \otimes Z $ 的特徵值僅取決於組成每個計算基礎向量的 qubits 同位檢查，而受控制的非作業則是用來計算此同位，並將其儲存在第一位。</span><span class="sxs-lookup"><span data-stu-id="eca91-193">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="eca91-194">然後在測量第一個位之後，我們就可以復原結果半形的識別，這相當於測量 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="eca91-194">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="eca91-195">另一個注意事項：雖然假設測量 $Z \otimes Z $ 的量值與依序測量 $Z \otimes \mathbb{1}$ 和 $ \mathbb{1} \otimes Z $ 相同，但此假設為 false。</span><span class="sxs-lookup"><span data-stu-id="eca91-195">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="eca91-196">原因是測量 $Z \otimes Z $ 將量子狀態投射到這些運算子的 $ + $1 或 $-$1 eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="eca91-196">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="eca91-197">測量 $Z \otimes \mathbb{1}$ 和 $ \mathbb{1} \otimes Z $ 會先將量子狀態向量投射到 $Z \otimes \mathbb{1}$ 的一半空間，然後再到 $ \mathbb{1} \otimes Z $ 的一半空間。</span><span class="sxs-lookup"><span data-stu-id="eca91-197">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$.</span></span>
<span data-ttu-id="eca91-198">因為有四個計算基礎的向量，同時執行這兩個度量會將狀態縮減為四分之一空間，因而減少為單一計算基礎向量。</span><span class="sxs-lookup"><span data-stu-id="eca91-198">As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="eca91-199">Qubits 之間的相互關聯</span><span class="sxs-lookup"><span data-stu-id="eca91-199">Correlations between qubits</span></span>
<span data-ttu-id="eca91-200">另一個查看 Pauli 矩陣的張量產品（例如 $X \otimes X $ 或 $Z \otimes Z $）的方法，就是這些測量可讓您查看儲存在兩個 qubits 之間關聯性的資訊。</span><span class="sxs-lookup"><span data-stu-id="eca91-200">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="eca91-201">測量 $X \otimes \id $，可讓您查看本機儲存在第一個 qubit 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="eca91-201">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="eca91-202">雖然這兩種類型的測量在量子運算中也同樣有價值，但前者也會照亮量子運算的威力。</span><span class="sxs-lookup"><span data-stu-id="eca91-202">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="eca91-203">它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一 qubit 中，而是一次儲存在所有 qubits 中的非本機，因此，只有透過聯合測量（例如 $Z \otimes Z $）來查看資訊會變成資訊清單。</span><span class="sxs-lookup"><span data-stu-id="eca91-203">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="eca91-204">例如，在錯誤修正中，我們通常會想要瞭解在學習嘗試保護的狀態時，所發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="eca91-204">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="eca91-205">「[翻轉」程式碼範例示範](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)如何使用 $Z \otimes z \otimes \id $ 和 $ \Id \otimes Z \otimes z $ 這類測量來執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="eca91-205">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="eca91-206">您也可以測量任意的 Pauli 運算子，例如 $X \otimes Y \otimes Z \otimes \boldone $。</span><span class="sxs-lookup"><span data-stu-id="eca91-206">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="eca91-207">Pauli 運算子的所有這類張量產品只有兩個特徵值 $ \pm $1，而這兩個 eigenspaces 構成整個向量空間的半個空格。</span><span class="sxs-lookup"><span data-stu-id="eca91-207">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="eca91-208">因此，它們會符合上面所述的需求。</span><span class="sxs-lookup"><span data-stu-id="eca91-208">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="eca91-209">在 Q # 中，這類測量結果會在 eigenspace 中產生正負號 $ （-1） ^ j $ 的值時，傳回 $j $。</span><span class="sxs-lookup"><span data-stu-id="eca91-209">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="eca91-210">將 Pauli 測量當做 Q # 中的內建功能會很有説明，因為測量這類運算子時，需要長鏈的受控制（而非閘道和基礎轉換）來描述將作業表示為 $Z $ 和 $ \id $ 的張量產品所需的 diagonalizing $U $ 閘道。</span><span class="sxs-lookup"><span data-stu-id="eca91-210">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="eca91-211">藉由指定您想要執行上述其中一項預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎測量提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="eca91-211">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="eca91-212">問 # 會自動為您處理所有必要的基礎轉換。</span><span class="sxs-lookup"><span data-stu-id="eca91-212">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="eca91-213">如需詳細資訊，請參閱[`Measure`](xref:microsoft.quantum.intrinsic.measure)和[`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis)作業。</span><span class="sxs-lookup"><span data-stu-id="eca91-213">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="eca91-214">無複製定理</span><span class="sxs-lookup"><span data-stu-id="eca91-214">The No-Cloning Theorem</span></span>

<span data-ttu-id="eca91-215">量子資訊功能強大。</span><span class="sxs-lookup"><span data-stu-id="eca91-215">Quantum information is powerful.</span></span>
<span data-ttu-id="eca91-216">這讓我們能夠執行令人驚奇的事，像是以指數方式比最佳的傳統演算法更快，或有效率地模擬傳統方式需要指數成本才能正確模擬的相互關聯 electron 系統。</span><span class="sxs-lookup"><span data-stu-id="eca91-216">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="eca91-217">不過，配量運算的功能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="eca91-217">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="eca91-218">其中一項限制是由*無複製定理*所提供。</span><span class="sxs-lookup"><span data-stu-id="eca91-218">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="eca91-219">未複製的定理是名為的恰如其。</span><span class="sxs-lookup"><span data-stu-id="eca91-219">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="eca91-220">它不允許由量子電腦複製一般量子狀態。</span><span class="sxs-lookup"><span data-stu-id="eca91-220">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="eca91-221">定理證明十分簡單。</span><span class="sxs-lookup"><span data-stu-id="eca91-221">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="eca91-222">雖然不復制定理的完整證明在這裡的討論方面有點技術性，但在我們的範圍內沒有其他輔助 qubits 的證明（輔助 qubits 會 qubits 用於計算期間的臨時空間，而且可以在 Q # 中輕鬆使用和管理），請參閱 <xref:microsoft.quantum.techniques.qubits>）。</span><span class="sxs-lookup"><span data-stu-id="eca91-222">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see <xref:microsoft.quantum.techniques.qubits>).</span></span>

<span data-ttu-id="eca91-223">對於這類的量子電腦，複製作業必須由單一矩陣描述。</span><span class="sxs-lookup"><span data-stu-id="eca91-223">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="eca91-224">我們不允許測量，因為它會損毀我們嘗試要複製的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="eca91-224">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="eca91-225">為了模擬複製作業，我們想要使用單一矩陣將 $ $ U \ket{\psi} \ket 的屬性用於任何 state $ \ket{\psi} $ 的屬性{0} = \ket{\psi} \ket{\psi} $ $。</span><span class="sxs-lookup"><span data-stu-id="eca91-225">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi} $$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="eca91-226">矩陣乘法的線性屬性會暗示任何第二個配量狀態 $ \ket{\phi} $，</span><span class="sxs-lookup"><span data-stu-id="eca91-226">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="eca91-227">$ $ \begin{align} U \left [\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket {\ phi} \ ket{0} + \frac{1}{\sqrt{2}} U\ket {\ psi} \ ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left （\ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right） \\\\ & \ne \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right） \otimes \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right）。</span><span class="sxs-lookup"><span data-stu-id="eca91-227">$$ \begin{align} U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0} + \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="eca91-228">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eca91-228">\end{align} $$</span></span>

<span data-ttu-id="eca91-229">這提供了不復制定理背後的基礎直覺：任何複製不明量子狀態的裝置，都必須在其複製的至少部分狀態中引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="eca91-229">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="eca91-230">雖然 cloner 在輸入狀態上以線性方式運作的關鍵假設，可以透過新增和測量輔助 qubits 來違反，這類互動也會透過測量統計資料來流失系統的相關資訊，並防止實際的情況在這種情況下，也會進行複製。</span><span class="sxs-lookup"><span data-stu-id="eca91-230">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="eca91-231">如需更完整的無複製定理證明，請參閱[以取得詳細資訊](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="eca91-231">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="eca91-232">無複製定理對於區分量子運算而言非常重要，因為如果您可以在較低的情況中複製配量狀態，則會被授與從配量狀態學習的近乎神奇功能。</span><span class="sxs-lookup"><span data-stu-id="eca91-232">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="eca91-233">事實上，您可能違反了海森堡的 vaunted 不確定性原則。</span><span class="sxs-lookup"><span data-stu-id="eca91-233">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="eca91-234">或者，您可以使用最佳的 cloner 從複雜的配量散發取得單一範例，並瞭解您可能會從一個範例中瞭解該散發的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="eca91-234">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="eca91-235">這就像是您翻轉一硬幣和觀察列印頭，然後告訴朋友有關結果的回應「，該硬幣的散佈必須以 $p = 0.512643 \ ldots $！</span><span class="sxs-lookup"><span data-stu-id="eca91-235">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="eca91-236">這類語句不會 sensical，因為有一小部分的資訊（列印頭結果）無法提供編碼散發所需的許多資訊，而不需要大量的先前資訊。</span><span class="sxs-lookup"><span data-stu-id="eca91-236">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="eca91-237">同樣地，如果沒有先前的資訊，我們就無法完全複製配量狀態，因為我們無法準備集團這類的硬幣，而不需要知道 $p $。</span><span class="sxs-lookup"><span data-stu-id="eca91-237">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="eca91-238">在量子運算中，資訊不是免費的。</span><span class="sxs-lookup"><span data-stu-id="eca91-238">Information is not free in quantum computing.</span></span>
<span data-ttu-id="eca91-239">每個 qubit 都有提供一項資訊，而不復制定理顯示沒有任何後門可被利用，來解決系統與在其上叫用之騒之間的基本取捨。</span><span class="sxs-lookup"><span data-stu-id="eca91-239">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
