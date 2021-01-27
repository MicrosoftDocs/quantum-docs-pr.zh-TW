---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855519"
---
# <a name="decomposedon-function"></a><span data-ttu-id="03503-102">DecomposedOn 函式</span><span class="sxs-lookup"><span data-stu-id="03503-102">DecomposedOn function</span></span>

<span data-ttu-id="03503-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="03503-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="03503-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03503-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03503-105">分解變數上的排列</span><span class="sxs-lookup"><span data-stu-id="03503-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="03503-106">描述</span><span class="sxs-lookup"><span data-stu-id="03503-106">Description</span></span>

<span data-ttu-id="03503-107">指定排列 $ \pi $ (`perm`) 和索引 $i $ (`index`) ，這個方法會傳回三個排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，讓 $ \ pi_l $ 和 $ \ pi_r $ 的影像不會變更其元素中 $i $ 和 $ \pi ' $ 的影像中的位，而不會變更其專案中的位 $i $。</span><span class="sxs-lookup"><span data-stu-id="03503-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="03503-108">輸入</span><span class="sxs-lookup"><span data-stu-id="03503-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="03503-109">為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="03503-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="03503-110">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03503-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="03503-111">Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) </span><span class="sxs-lookup"><span data-stu-id="03503-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="03503-112">範例</span><span class="sxs-lookup"><span data-stu-id="03503-112">Example</span></span>

<span data-ttu-id="03503-113">假設輸入是為永久 = [0，2，3，5，7，1，4，6] 和 index = 0，則此函式會根據下表來計算三個排列，這會以 `perm` 二進位標記法來列出以二進位標記法排列，並以群組 A 中的元素和群組 D 中的影像來列出排列。 資料行列出位索引。</span><span class="sxs-lookup"><span data-stu-id="03503-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="03503-114">|  A |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="03503-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="03503-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-115">2 1 0</span></span> | <span data-ttu-id="03503-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-116">2 1 0</span></span> | <span data-ttu-id="03503-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-117">2 1 0</span></span> | <span data-ttu-id="03503-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="03503-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-119">0 0 0</span></span> |       |       | <span data-ttu-id="03503-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-120">0 0 0</span></span> | <span data-ttu-id="03503-121">0</span><span class="sxs-lookup"><span data-stu-id="03503-121">0</span></span>
| <span data-ttu-id="03503-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-122">0 0 1</span></span> |       |       | <span data-ttu-id="03503-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-123">0 1 0</span></span> | <span data-ttu-id="03503-124">2</span><span class="sxs-lookup"><span data-stu-id="03503-124">2</span></span>
| <span data-ttu-id="03503-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-125">0 1 0</span></span> |       |       | <span data-ttu-id="03503-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-126">0 1 1</span></span> | <span data-ttu-id="03503-127">3</span><span class="sxs-lookup"><span data-stu-id="03503-127">3</span></span>
| <span data-ttu-id="03503-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-128">0 1 1</span></span> |       |       | <span data-ttu-id="03503-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-129">1 0 1</span></span> | <span data-ttu-id="03503-130">5</span><span class="sxs-lookup"><span data-stu-id="03503-130">5</span></span>
| <span data-ttu-id="03503-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-131">1 0 0</span></span> |       |       | <span data-ttu-id="03503-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-132">1 1 1</span></span> | <span data-ttu-id="03503-133">7</span><span class="sxs-lookup"><span data-stu-id="03503-133">7</span></span>
| <span data-ttu-id="03503-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-134">1 0 1</span></span> |       |       | <span data-ttu-id="03503-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-135">0 0 1</span></span> | <span data-ttu-id="03503-136">1</span><span class="sxs-lookup"><span data-stu-id="03503-136">1</span></span>
| <span data-ttu-id="03503-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-137">1 1 0</span></span> |       |       | <span data-ttu-id="03503-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-138">1 0 0</span></span> | <span data-ttu-id="03503-139">4</span><span class="sxs-lookup"><span data-stu-id="03503-139">4</span></span>
| <span data-ttu-id="03503-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-140">1 1 1</span></span> |       |       | <span data-ttu-id="03503-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-141">1 1 0</span></span> | <span data-ttu-id="03503-142">6</span><span class="sxs-lookup"><span data-stu-id="03503-142">6</span></span>

<span data-ttu-id="03503-143">索引的所有值不等於 0 (= index) 會從 A 複製到 B，而從 D 複製到 C。</span><span class="sxs-lookup"><span data-stu-id="03503-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="03503-144">|  A |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="03503-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="03503-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-145">2 1 0</span></span> | <span data-ttu-id="03503-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-146">2 1 0</span></span> | <span data-ttu-id="03503-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-147">2 1 0</span></span> | <span data-ttu-id="03503-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="03503-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-149">0 0 0</span></span> | <span data-ttu-id="03503-150">0 0</span><span class="sxs-lookup"><span data-stu-id="03503-150">0 0</span></span>   | <span data-ttu-id="03503-151">0 0</span><span class="sxs-lookup"><span data-stu-id="03503-151">0 0</span></span>   | <span data-ttu-id="03503-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-152">0 0 0</span></span> |
| <span data-ttu-id="03503-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-153">0 0 1</span></span> | <span data-ttu-id="03503-154">0 0</span><span class="sxs-lookup"><span data-stu-id="03503-154">0 0</span></span>   | <span data-ttu-id="03503-155">0 1</span><span class="sxs-lookup"><span data-stu-id="03503-155">0 1</span></span>   | <span data-ttu-id="03503-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-156">0 1 0</span></span> |
| <span data-ttu-id="03503-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-157">0 1 0</span></span> | <span data-ttu-id="03503-158">0 1</span><span class="sxs-lookup"><span data-stu-id="03503-158">0 1</span></span>   | <span data-ttu-id="03503-159">0 1</span><span class="sxs-lookup"><span data-stu-id="03503-159">0 1</span></span>   | <span data-ttu-id="03503-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-160">0 1 1</span></span> |
| <span data-ttu-id="03503-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-161">0 1 1</span></span> | <span data-ttu-id="03503-162">0 1</span><span class="sxs-lookup"><span data-stu-id="03503-162">0 1</span></span>   | <span data-ttu-id="03503-163">1 0</span><span class="sxs-lookup"><span data-stu-id="03503-163">1 0</span></span>   | <span data-ttu-id="03503-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-164">1 0 1</span></span> |
| <span data-ttu-id="03503-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-165">1 0 0</span></span> | <span data-ttu-id="03503-166">1 0</span><span class="sxs-lookup"><span data-stu-id="03503-166">1 0</span></span>   | <span data-ttu-id="03503-167">1 1</span><span class="sxs-lookup"><span data-stu-id="03503-167">1 1</span></span>   | <span data-ttu-id="03503-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-168">1 1 1</span></span> |
| <span data-ttu-id="03503-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-169">1 0 1</span></span> | <span data-ttu-id="03503-170">1 0</span><span class="sxs-lookup"><span data-stu-id="03503-170">1 0</span></span>   | <span data-ttu-id="03503-171">0 0</span><span class="sxs-lookup"><span data-stu-id="03503-171">0 0</span></span>   | <span data-ttu-id="03503-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-172">0 0 1</span></span> |
| <span data-ttu-id="03503-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-173">1 1 0</span></span> | <span data-ttu-id="03503-174">1 1</span><span class="sxs-lookup"><span data-stu-id="03503-174">1 1</span></span>   | <span data-ttu-id="03503-175">1 0</span><span class="sxs-lookup"><span data-stu-id="03503-175">1 0</span></span>   | <span data-ttu-id="03503-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-176">1 0 0</span></span> |
| <span data-ttu-id="03503-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-177">1 1 1</span></span> | <span data-ttu-id="03503-178">1 1</span><span class="sxs-lookup"><span data-stu-id="03503-178">1 1</span></span>   | <span data-ttu-id="03503-179">1 1</span><span class="sxs-lookup"><span data-stu-id="03503-179">1 1</span></span>   | <span data-ttu-id="03503-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-180">1 1 0</span></span> |

<span data-ttu-id="03503-181">接下來，會針對第一個專案放置0，而第一個元素的第0個專案中的第一個專案具有空的索引，而在第一個案例中，前置詞 (符合第一個案例中的第一個資料列（索引 0 0) 的另一個資料列）</span><span class="sxs-lookup"><span data-stu-id="03503-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="03503-182">之後，會在區塊 C 的相同資料列中加入1，然後在區塊 C 中將對應的前置詞加上0。 此程式會重複，直到所有索引都放在區塊 B 和 C 中的資料行0為止。</span><span class="sxs-lookup"><span data-stu-id="03503-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="03503-183">|  A |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="03503-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="03503-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-184">2 1 0</span></span> | <span data-ttu-id="03503-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-185">2 1 0</span></span> | <span data-ttu-id="03503-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-186">2 1 0</span></span> | <span data-ttu-id="03503-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="03503-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-188">0 0 0</span></span> | <span data-ttu-id="03503-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-189">0 0 0</span></span> | <span data-ttu-id="03503-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-190">0 0 0</span></span> | <span data-ttu-id="03503-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-191">0 0 0</span></span> |
| <span data-ttu-id="03503-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-192">0 0 1</span></span> | <span data-ttu-id="03503-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-193">0 0 1</span></span> | <span data-ttu-id="03503-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-194">0 1 1</span></span> | <span data-ttu-id="03503-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-195">0 1 0</span></span> |
| <span data-ttu-id="03503-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-196">0 1 0</span></span> | <span data-ttu-id="03503-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-197">0 1 0</span></span> | <span data-ttu-id="03503-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-198">0 1 0</span></span> | <span data-ttu-id="03503-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-199">0 1 1</span></span> |
| <span data-ttu-id="03503-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-200">0 1 1</span></span> | <span data-ttu-id="03503-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-201">0 1 1</span></span> | <span data-ttu-id="03503-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-202">1 0 1</span></span> | <span data-ttu-id="03503-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-203">1 0 1</span></span> |
| <span data-ttu-id="03503-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-204">1 0 0</span></span> | <span data-ttu-id="03503-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-205">1 0 0</span></span> | <span data-ttu-id="03503-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-206">1 1 0</span></span> | <span data-ttu-id="03503-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-207">1 1 1</span></span> |
| <span data-ttu-id="03503-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-208">1 0 1</span></span> | <span data-ttu-id="03503-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-209">1 0 1</span></span> | <span data-ttu-id="03503-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-210">0 0 1</span></span> | <span data-ttu-id="03503-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="03503-211">0 0 1</span></span> |
| <span data-ttu-id="03503-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-212">1 1 0</span></span> | <span data-ttu-id="03503-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-213">1 1 0</span></span> | <span data-ttu-id="03503-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-214">1 0 0</span></span> | <span data-ttu-id="03503-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="03503-215">1 0 0</span></span> |
| <span data-ttu-id="03503-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-216">1 1 1</span></span> | <span data-ttu-id="03503-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-217">1 1 1</span></span> | <span data-ttu-id="03503-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="03503-218">1 1 1</span></span> | <span data-ttu-id="03503-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="03503-219">1 1 0</span></span> |

<span data-ttu-id="03503-220">我們可以從資料表讀取三個新的排列：</span><span class="sxs-lookup"><span data-stu-id="03503-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="03503-221">$ \ pi_l $ 中的元素，B 中的影像 (左) </span><span class="sxs-lookup"><span data-stu-id="03503-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="03503-222">$ \ pi_r $ （含 D 的元素），C 中的影像 (right) </span><span class="sxs-lookup"><span data-stu-id="03503-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="03503-223">$ \pi ' $ （具有 B 中的元素），C 中的影像 (餘數) </span><span class="sxs-lookup"><span data-stu-id="03503-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="03503-224">請注意，在索引1和2中，設計位值不會變更 $ \ pi_l $ 和 $ \ pi_r $，而且在 $ \ pi_ ' $ 中的索引0不會變更位值。</span><span class="sxs-lookup"><span data-stu-id="03503-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="03503-225">另請注意，$ \ pi_l $ 和 $ \ pi_r $ 必須是自反向。</span><span class="sxs-lookup"><span data-stu-id="03503-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="03503-226">衍生和傳回的排列如下： left = [0，1，2，3，4，5，6，7] right = [0，1，3，2，4，5，7，6] 餘數 = [0，3，2，5，6，1，4，7]</span><span class="sxs-lookup"><span data-stu-id="03503-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>