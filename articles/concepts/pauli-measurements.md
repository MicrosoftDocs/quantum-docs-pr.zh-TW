---
title: Pauli 測量
description: 瞭解如何使用單一和多 qubit 的 Pauli 測量作業。
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
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
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630309"
---
# <a name="pauli-measurements"></a><span data-ttu-id="e4e4c-103">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="e4e4c-103">Pauli Measurements</span></span>

<span data-ttu-id="e4e4c-104">在先前的討論中，我們著重于計算基礎測量。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="e4e4c-105">事實上，從標記的角度來看，在計量運算中所發生的其他常見測量，在計算基礎測量方面很方便表達。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="e4e4c-106">當您使用 Q # 時，您會遇到的最常見測量類型可能是*Pauli 測量*，這會將計算基礎測量一般化以包含其他基底的度量，以及不同 qubits 之間的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="e4e4c-107">在這種情況下，通常會討論測量 Pauli 運算子，通常是 $X、Y、Z $ 或 $Z \otimes Z、x \otimes x、x \otimes Y 等等的運算子 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="e4e4c-108">在 Q # 中，多 qubit 的 Pauli 運算子通常會由類型的陣列表示 `Pauli[]` 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="e4e4c-109">例如，若要代表 $X \otimes Z \otimes Y $ ，您可以使用陣列 `[PauliX, PauliZ, PauliY]` 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="e4e4c-110">討論 Pauli 運算子方面的測量，特別是在量子錯誤更正的子欄位中。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="e4e4c-111">在 Q # 中，我們遵循類似的慣例。我們現在會說明這種替代的度量觀點。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="e4e4c-112">在探究到如何思考 Pauli 測量的詳細資料之前，請考慮測量量子電腦內的單一 qubit 對量子狀態的作用。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="e4e4c-113">假設我們有 $n $ qubit 的量子狀態，然後測量一個 qubit，立即將該狀態的一半，視為可能出現在其中的 $ 2 ^ n 個 $ 可能性。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="e4e4c-114">換句話說，測量會將量子狀態投射到兩個半形的其中一個。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="e4e4c-115">我們可以將我們認為測量的方式一般化，以反映此直覺。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="e4e4c-116">為了簡潔地識別這些 subspaces，我們需要用來描述它們的語言。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="e4e4c-117">描述兩個 subspaces 的其中一種方式，是透過只具有兩個唯一特徵值的矩陣來指定它們，慣例是 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="e4e4c-118">如需以這種方式描述 subspaces 的簡單範例，請考慮 $Z $ ：</span><span class="sxs-lookup"><span data-stu-id="e4e4c-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="e4e4c-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-119">$$ \begin{align}</span></span>
  <span data-ttu-id="e4e4c-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="e4e4c-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-121">\end{align}</span></span>
$$

<span data-ttu-id="e4e4c-122">藉由讀取 Pauli $Z 矩陣的對角線元素 $ ，我們可以看到 $Z $ 有兩個特徵向量、$ \ket{0 } $ 和 $ \ket{1 } $，以及對應的特徵值 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="e4e4c-123">因此，如果我們測量 qubit 並取得 `Zero` （對應至 state $ \ket{0 } $），我們就知道 qubit 的狀態是 $Z 運算子的 $ + 1 $ eigenstate $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="e4e4c-124">同樣地，如果我們取得 `One` ，我們知道 qubit 的狀態是 $Z 的 $-1 $ eigenstate $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="e4e4c-125">此程式在 Pauli 測量的語言中稱為「測量 Pauli $Z」 $ ，完全等同于執行計算基礎測量。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="e4e4c-126">任何 \times $ 屬於 $Z 單一轉換的 $2 2 矩陣也都 $ 符合此準則。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="e4e4c-127">也就是說，我們也可以使用矩陣 $A = U ^ \dagger Z U $ ，其中 $U $ 是任何其他的單一矩陣，以便在其 $ \pm 1 特徵向量中定義度量的兩個結果 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="e4e4c-128">Pauli 量值的標記法會藉由將 $X、Y、Z $ 度量識別為對等的測量，以取得 qubit 中的資訊，來參考這個單一等價項。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="e4e4c-129">為了方便起見，以下提供這些測量。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="e4e4c-130">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="e4e4c-130">Pauli Measurement</span></span>  |<span data-ttu-id="e4e4c-131">單一轉換</span><span class="sxs-lookup"><span data-stu-id="e4e4c-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="e4e4c-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-132">$Z$</span></span>               | <span data-ttu-id="e4e4c-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-133">$\boldone$</span></span>             |
| <span data-ttu-id="e4e4c-134">$X$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-134">$X$</span></span>               | <span data-ttu-id="e4e4c-135">$H$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-135">$H$</span></span>                    |
| <span data-ttu-id="e4e4c-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-136">$Y$</span></span>               | <span data-ttu-id="e4e4c-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="e4e4c-138">也就是說，使用這種語言，「量值 $Y」等同于套用 $ $HS ^ \dagger， $ 然後以計算為基礎，其中是內建 [`S`](xref:microsoft.quantum.intrinsic.s) 的量子作業，有時稱為「階段閘道」，而且可由單一矩陣模擬</span><span class="sxs-lookup"><span data-stu-id="e4e4c-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="e4e4c-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-139">$$ \begin{align}</span></span>
    <span data-ttu-id="e4e4c-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="e4e4c-141">1 & 0 \\ \\ 0 & i \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="e4e4c-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-142">\end{align}</span></span>
$$

<span data-ttu-id="e4e4c-143">這也相當於將 $HS ^ \dagger 套用 $ 至量子狀態向量，然後測量 $Z $ ，讓下列作業相當於 `Measure([PauliY], [q])` ：</span><span class="sxs-lookup"><span data-stu-id="e4e4c-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

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

<span data-ttu-id="e4e4c-144">藉由轉換回計算基礎，即可找到正確的狀態，這是將 $SH 套用 $ 至量子狀態向量的數量; 在上述程式碼片段中，轉換回計算基礎的動作會透過使用區塊自動處理 `within … apply` 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="e4e4c-145">在 Q # 中，我們會假設結果---也就是，從與狀態互動時所解壓縮的傳統資訊---是由 `Result` 值 $j \in \\ {\Texttt{Zero } ，\texttt{One} $ 所指定， } \\ 指出結果是否在 $ 所測量 Pauli 運算子的 $ （-1） ^ j eigenspace 中。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="e4e4c-146">多 qubit 測量</span><span class="sxs-lookup"><span data-stu-id="e4e4c-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="e4e4c-147">多 qubit Pauli 運算子的度量定義類似，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4e4c-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="e4e4c-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 0&\\\\ 0 & -1&0 \\\\ 0&0&0&1 \end { bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="e4e4c-149">因此，兩個 Pauli $Z 運算子的張量產品會 $ 形成由包含 $ + 1 $ 和 $-1 特徵值的兩個空格所組成的矩陣 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="e4e4c-150">就像單一 qubit 的情況一樣，兩者都構成一半空間，這表示可存取的兩個向量空間一半屬於 $ + 1 $ eigenspace，而其餘一半則是 $-1 $ eigenspace。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="e4e4c-151">一般來說，您可以從張量產品的定義中查看任何 Pauli-$Z 運算子的張量產品， $ 以及身分識別也會遵守這項功能。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="e4e4c-152">例如，</span><span class="sxs-lookup"><span data-stu-id="e4e4c-152">For example,</span></span>

<span data-ttu-id="e4e4c-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-153">$$ \begin{align}</span></span>
    <span data-ttu-id="e4e4c-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="e4e4c-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & \\ \\ 0 &-1 & 0 0 & 0 & \\ \\ 0 &-1 \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="e4e4c-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-156">\end{align}</span></span>
$$

<span data-ttu-id="e4e4c-157">如前所述，這類矩陣的任何單一轉換也會描述由 $ \pm 1 特徵值標記的兩個半形 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="e4e4c-158">例如， \otimes \otimes \otimes \otimes $ 從 $Z = HXH 的身分識別 $X X = H H （Z z） h h $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="e4e4c-159">與一個 qubit 的案例類似，所有的雙 qubit Pauli 量值都可以 \otimes $ $U 的 $4 \times 4 個 $ 單一矩陣的 $ $U ^ \Dagger （Z \id） U 寫入。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="e4e4c-160">我們會列舉下表中的轉換。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="e4e4c-161">在下表中，我們使用 $ \operatorname{SWAP } $ 來表示矩陣 $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="e4e4c-162">\operatorname{SWAP } & = \left （\begin{matrix}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="e4e4c-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{matrix } \right） \end{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="e4e4c-164">$ $ 用來模擬內部作業 [`SWAP`](xref:microsoft.quantum.intrinsic) 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="e4e4c-165">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="e4e4c-165">Pauli Measurement</span></span>     |<span data-ttu-id="e4e4c-166">單一轉換</span><span class="sxs-lookup"><span data-stu-id="e4e4c-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="e4e4c-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="e4e4c-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="e4e4c-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="e4e4c-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="e4e4c-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="e4e4c-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="e4e4c-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="e4e4c-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="e4e4c-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="e4e4c-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="e4e4c-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="e4e4c-178">$ （H \otimes \boldone） \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="e4e4c-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="e4e4c-180">$ （HS ^ \dagger \otimes \boldone） \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="e4e4c-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-181">$Z\otimes Z$</span></span> | <span data-ttu-id="e4e4c-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="e4e4c-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-183">$X\otimes Z$</span></span> | <span data-ttu-id="e4e4c-184">$ \operatorname{CNOT } \_ {10 } （H \otimes \boldone） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="e4e4c-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-185">$Y\otimes Z$</span></span> | <span data-ttu-id="e4e4c-186">$ \operatorname{CNOT } \_ {10 } （HS ^ \dagger \otimes \boldone） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="e4e4c-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-187">$Z\otimes X$</span></span> | <span data-ttu-id="e4e4c-188">$ \operatorname{CNOT } \_ {10 } （\boldone \otimes H） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="e4e4c-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-189">$X\otimes X$</span></span> | <span data-ttu-id="e4e4c-190">$ \operatorname{CNOT } \_ {10 } （h \otimes h） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="e4e4c-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-191">$Y\otimes X$</span></span> | <span data-ttu-id="e4e4c-192">$ \operatorname{CNOT } \_ {10 } （HS ^ \dagger \otimes H） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="e4e4c-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-193">$Z\otimes Y$</span></span> | <span data-ttu-id="e4e4c-194">$ \operatorname{CNOT } \_ {10 } （\boldone \otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="e4e4c-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-195">$X\otimes Y$</span></span> | <span data-ttu-id="e4e4c-196">$ \operatorname{CNOT } \_ {10 } （H \otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="e4e4c-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="e4e4c-197">$Y\otimes Y$</span></span> | <span data-ttu-id="e4e4c-198">$ \operatorname{CNOT } \_ {10 } （HS ^ \dagger \otimes hs ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="e4e4c-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="e4e4c-199">在這裡，作業 [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) 會因為下列原因而出現。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="e4e4c-200">不包含 $ \boldone 矩陣的每個 Pauli 量值， $ 都等同于由上而下的推理來 $Z \otimes Z $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="e4e4c-201">$Z Z 的特徵值 \otimes $ 只取決於組成每個計算基礎向量的 qubits 同位檢查，而受控制的非作業則是用來計算此同位，並將其儲存在第一位。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="e4e4c-202">然後在測量第一個位之後，我們就可以復原結果半形的識別，這相當於測量 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="e4e4c-203">另一個注意事項：雖然假設測量 $Z \otimes Z $ 的 $Z 與依序測量 \otimes \mathbb{1 } $ 和 $ \mathbb{1 } \otimes Z 相同 $ ，但此假設為 false。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="e4e4c-204">原因是測量 $Z \otimes Z $ 將量子狀態投射到這些運算子的 $ + 1 $ 或 $-1 $ eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="e4e4c-205">測量 $Z \otimes \mathbb{1 } $ 然後 $ \Mathbb{1 } \otimes Z 會 $ 先將量子狀態向量投射到 $Z \mathbb{1 $ 的一半 \otimes 空間 } ，然後再到 $ \mathbb{1 \otimes Z 的一半空間 } $ 。因為有四個計算基礎的向量，同時執行這兩個度量會將狀態縮減為四分之一空間，因而減少為單一計算基礎向量。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="e4e4c-206">Qubits 之間的相互關聯</span><span class="sxs-lookup"><span data-stu-id="e4e4c-206">Correlations between qubits</span></span>
<span data-ttu-id="e4e4c-207">另一個查看 Pauli 矩陣（例如 $X X 或 $Z Z）之張量產品的方式， \otimes $ \otimes $ 是這些測量可讓您查看儲存在兩個 qubits 之間相互關聯的資訊。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="e4e4c-208">測量 $X \otimes \id $ 可讓您查看本機儲存在第一個 qubit 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="e4e4c-209">雖然這兩種類型的測量在量子運算中也同樣有價值，但前者也會照亮量子運算的威力。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="e4e4c-210">它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一 qubit 中，而是會一次儲存在所有 qubits 中，因此，只有透過聯合測量來查看（例如 $Z \otimes Z），這項資訊才會 $ 成為資訊清單。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="e4e4c-211">例如，在錯誤修正中，我們通常會想要瞭解在學習嘗試保護的狀態時，所發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="e4e4c-212">「[翻轉」程式碼範例會示範](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)如何使用 $Z \otimes z \otimes \id $ 和 $ \id \Otimes z \otimes z 之類的測量來執行這項操作 $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="e4e4c-213">您也可以測量任意的 Pauli 運算子，例如 $X \otimes Y \Otimes Z \otimes \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="e4e4c-214">Pauli 運算子的所有這類張量產品只有兩個特徵值 $ \pm 1 $ ，而這兩個 eigenspaces 構成整個向量空間的半空格。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="e4e4c-215">因此，它們會符合上面所述的需求。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="e4e4c-216">在 Q # 中，這類測量結果會傳回 $j， $ 如果量值產生 eigenspace 的正負號 $ （-1） ^ j $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="e4e4c-217">將 Pauli 測量當做 Q # 中的內建功能很有説明，因為測量這類運算子需要較長的受控制（而非閘道）和基礎轉換鏈，以描述將作業當做 $ $Z $ 和 $ \id 的張量產品來表達作業所需的 diagonalizing $U 閘道 $ 。藉由指定您想要執行上述其中一項預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎測量提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="e4e4c-218">問 # 會自動為您處理所有必要的基礎轉換。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="e4e4c-219">如需詳細資訊，請參閱 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 和 [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 作業。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="e4e4c-220">無複製定理</span><span class="sxs-lookup"><span data-stu-id="e4e4c-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="e4e4c-221">量子資訊功能強大。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-221">Quantum information is powerful.</span></span>
<span data-ttu-id="e4e4c-222">這讓我們能夠執行令人驚奇的事，像是以指數方式比最佳的傳統演算法更快，或有效率地模擬傳統方式需要指數成本才能正確模擬的相互關聯 electron 系統。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="e4e4c-223">不過，配量運算的功能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="e4e4c-224">其中一項限制是由*無複製定理*所提供。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="e4e4c-225">未複製的定理是名為的恰如其。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="e4e4c-226">它不允許由量子電腦複製一般量子狀態。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="e4e4c-227">定理證明十分簡單。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="e4e4c-228">雖然不復制定理的完整證明在這裡的討論方面有點技術性，但在我們的範圍內沒有其他輔助 qubits 的證明（輔助 qubits 會在計算期間用於臨時空間，而且可以在 Q # 中輕鬆使用和管理），請參閱[借用的 qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)）。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="e4e4c-229">對於這類的量子電腦，複製作業必須由單一矩陣描述。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="e4e4c-230">我們不允許測量，因為它會損毀我們嘗試要複製的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="e4e4c-231">為了模擬複製作業，我們想要使用單一矩陣來擁有 $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi 的屬性。}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="e4e4c-232">任何 state $ \ket \psi $ 的 $ $ { } 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="e4e4c-233">矩陣乘法的線性屬性會暗示任何第二個配量狀態 $ \ket { \phi } $，</span><span class="sxs-lookup"><span data-stu-id="e4e4c-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="e4e4c-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-234">$$ \begin{align}</span></span>
    <span data-ttu-id="e4e4c-235">U \left [\frac{1 } {\sqrt{2 } } \left （\ket { \phi } + \ket { \psi } \right） \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="e4e4c-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="e4e4c-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left （\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="e4e4c-238">\right） \\ \\ & \ne \left （\frac{1 } {\sqrt{2 } } \left （\ket { \phi } + \ket { \psi \right } ） \right） \otimes \left （\frac{1 } {\sqrt{2 } } \left （\ket { \phi } + \ket { \psi } \right） \right）。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="e4e4c-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4e4c-239">\end{align}</span></span>
$$

<span data-ttu-id="e4e4c-240">這提供了不復制定理背後的基礎直覺：任何複製不明量子狀態的裝置，都必須在其複製的至少部分狀態中引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="e4e4c-241">雖然在輸入狀態上以線性方式執行 cloner 的主要假設是透過新增和測量輔助 qubits 來違反，這類互動也會透過測量統計資料來流失系統的相關資訊，並避免在這種情況下進行完全複製。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="e4e4c-242">如需更完整的無複製定理證明，請參閱[以取得詳細資訊](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="e4e4c-243">無複製定理對於區分量子運算而言非常重要，因為如果您可以在較低的情況中複製配量狀態，則會被授與從配量狀態學習的近乎神奇功能。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="e4e4c-244">事實上，您可能違反了海森堡的 vaunted 不確定性原則。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="e4e4c-245">或者，您可以使用最佳的 cloner 從複雜的配量散發取得單一範例，並瞭解您可能會從一個範例中瞭解該散發的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="e4e4c-246">這就像是您翻轉一硬幣和觀察列印頭，然後告訴朋友有關結果的回應「，該硬幣的散佈必須以 $p = 0.512643 \ ldots $ ！」</span><span class="sxs-lookup"><span data-stu-id="e4e4c-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="e4e4c-247">這類語句不會 sensical，因為有一小部分的資訊（列印頭結果）無法提供編碼散發所需的許多資訊，而不需要大量的先前資訊。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="e4e4c-248">同樣地，如果沒有先前的資訊，我們就無法完全複製量子狀態，因為我們無法準備集團這類的硬幣，而不需要知道 $p $ 。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="e4e4c-249">在量子運算中，資訊不是免費的。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="e4e4c-250">每個 qubit 都有提供一項資訊，而不復制定理顯示沒有任何後門可被利用，來解決系統與在其上叫用之騒之間的基本取捨。</span><span class="sxs-lookup"><span data-stu-id="e4e4c-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
