---
title: 'Q # 技術-本機變數 |Microsoft Docs'
description: 'Q # 技術-本機變數'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183279"
---
# <a name="local-variables"></a><span data-ttu-id="8c438-103">區域變數</span><span class="sxs-lookup"><span data-stu-id="8c438-103">Local Variables</span></span> #

<span data-ttu-id="8c438-104">您可以使用 `let` 關鍵字，將 Q # 中任何類型的值指派給變數，以便在作業或函數內重複使用。</span><span class="sxs-lookup"><span data-stu-id="8c438-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="8c438-105">例如：</span><span class="sxs-lookup"><span data-stu-id="8c438-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="8c438-106">這會將特定的 Pauli 運算子陣列指派給名為 `measurementOperator`的變數。</span><span class="sxs-lookup"><span data-stu-id="8c438-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="8c438-107">請注意，我們不需要明確指定新變數的類型，因為 `let` 語句右邊的運算式是明確的，而且該類型是由編譯器推斷。</span><span class="sxs-lookup"><span data-stu-id="8c438-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="8c438-108">Q # 中的變數是*不可變*的，這表示一旦以這種方式定義變數之後，就無法再以任何方式進行變更。</span><span class="sxs-lookup"><span data-stu-id="8c438-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="8c438-109">這可提供數個有用的優化，包括優化要重新排序之變數的傳統邏輯，以套用作業的 `Adjoint` 變體。</span><span class="sxs-lookup"><span data-stu-id="8c438-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="8c438-110">使用上述 `let` 系結所定義的變數是特定範圍的區域，例如作業的主體或 `for` 迴圈的內容。</span><span class="sxs-lookup"><span data-stu-id="8c438-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="8c438-111">可變動性</span><span class="sxs-lookup"><span data-stu-id="8c438-111">Mutability</span></span> ##

<span data-ttu-id="8c438-112">做為使用 `let`建立變數的替代方法，`mutable` 關鍵字會建立一開始使用 `set` 關鍵字來建立的特殊可變變數。</span><span class="sxs-lookup"><span data-stu-id="8c438-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="8c438-113">Q # 中的所有類型（包括陣列）都會遵循值的語義。</span><span class="sxs-lookup"><span data-stu-id="8c438-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="8c438-114">特別是，不可能更新陣列專案。</span><span class="sxs-lookup"><span data-stu-id="8c438-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="8c438-115">若要修改現有的陣列，您必須利用與中F#記錄相同的複製和更新機制。</span><span class="sxs-lookup"><span data-stu-id="8c438-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="8c438-116">針對[`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)中提供的陣列使用程式庫工具，我們可以輕鬆地定義函式，以傳回 Paulis 的陣列，其中 index `i` 的會採用指定的值，而所有其他專案都是身分識別：</span><span class="sxs-lookup"><span data-stu-id="8c438-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="8c438-117">在討論問 # 語句和運算式時，我們將詳細說明如何使用陣列。</span><span class="sxs-lookup"><span data-stu-id="8c438-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="8c438-118">Q # 中的可變動性是套用至*符號*（而不是類型或值）的概念。</span><span class="sxs-lookup"><span data-stu-id="8c438-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="8c438-119">具體而言，它沒有隱含或明確的類型系統中的標記法，而且系結是否可變動（如 `mutable` 關鍵字所指示）或不可變（如 `let`所表示）不會變更系結變數的類型。</span><span class="sxs-lookup"><span data-stu-id="8c438-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="8c438-120">這會提供一個重要的方式來隔離特定函式和作業中的可變動性。</span><span class="sxs-lookup"><span data-stu-id="8c438-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="8c438-121">特別的是，即使使用可變動變數之作業的 adjoint 特製化無法自動產生，當作業呼叫使用可變動性的函式時，自動產生功能也會正常運作。</span><span class="sxs-lookup"><span data-stu-id="8c438-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="8c438-122">基於這個理由，最好的做法是讓使用可變動性的函式和作業盡可能精簡，讓其餘的量副程式可以使用一般的不可變變數來撰寫。</span><span class="sxs-lookup"><span data-stu-id="8c438-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="8c438-123">解構</span><span class="sxs-lookup"><span data-stu-id="8c438-123">Deconstruction</span></span> ##

<span data-ttu-id="8c438-124">除了指派單一變數之外，`let` 和 `mutable` 關鍵字，或事實上任何其他系結結構，也允許將[元組類型](xref:microsoft.quantum.language.type-model#tuple-types)的內容解壓縮。</span><span class="sxs-lookup"><span data-stu-id="8c438-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="8c438-125">這個表單的指派是用來*解構*該元組的元素。</span><span class="sxs-lookup"><span data-stu-id="8c438-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="8c438-126">比方說，如果我們以元組為 Hamiltonian 中的詞彙建立模型，則可以使用解構來存取我們在該詞彙下需要模擬的不同資料：</span><span class="sxs-lookup"><span data-stu-id="8c438-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


