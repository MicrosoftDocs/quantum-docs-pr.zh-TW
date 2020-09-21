---
title: 'Broombridge 架構規格 (ver 0.2) '
description: 詳細說明適用于 Microsoft 量子化學程式庫的 Broombridge 量子化學架構 v 0.2 的規格。
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 851d10c0137deecf8e861aad30b5e08a9ae61754
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833759"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="fe9ff-103">Broombridge 規格 v 0。2</span><span class="sxs-lookup"><span data-stu-id="fe9ff-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="fe9ff-104">本檔中的關鍵字「必須」、「不得」、「必要」、「應該」、「不應」、「應該」、「不應」、「建議」、「可能」和「選擇性」，如 [RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="fe9ff-105">任何標題為「附注」、「資訊」或「警告」的提要欄位都有提供資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="fe9ff-106">簡介</span><span class="sxs-lookup"><span data-stu-id="fe9ff-106">Introduction</span></span> ##

<span data-ttu-id="fe9ff-107">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-107">This section is informative.</span></span>

<span data-ttu-id="fe9ff-108">Broombridge 檔的目的是要傳達量子化學中模擬問題的實例，以使用量子模擬和程式設計工具鏈進行處理。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="fe9ff-109">序列化</span><span class="sxs-lookup"><span data-stu-id="fe9ff-109">Serialization</span></span> ##

<span data-ttu-id="fe9ff-110">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-110">This section is normative.</span></span>

<span data-ttu-id="fe9ff-111">Broombridge 檔必須序列化為 [YAML 1.2 檔](http://yaml.org/spec/) ，以表示 [RFC 4627](https://tools.ietf.org/html/rfc4627) 區段2.2 中所述的 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="fe9ff-112">序列化為 YAML 的物件必須具有 `"$schema"` 其值為的屬性 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` ，而且必須根據 JSON 架構 draft-06 規格 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 來有效。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="fe9ff-113">針對此規格的其餘部分，「Broombridge 物件」會參考從 Broombridge YAML 檔案還原序列化的 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="fe9ff-114">除非另有明確注明，否則物件不能有在本檔中明確指定的屬性以外的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="fe9ff-115">其他定義</span><span class="sxs-lookup"><span data-stu-id="fe9ff-115">Additional Definitions</span></span> ##

<span data-ttu-id="fe9ff-116">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="fe9ff-117">Quantity 物件</span><span class="sxs-lookup"><span data-stu-id="fe9ff-117">Quantity Objects</span></span> ###

<span data-ttu-id="fe9ff-118">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-118">This section is normative.</span></span>

<span data-ttu-id="fe9ff-119">_Quantity 物件_是一個 JSON 物件，且 `units` 其值必須是 [表 1] 所列的其中一個允許值的屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="fe9ff-120">如果 quantity 物件除了屬性之外還具有單一屬性，則它是 _簡單數量的物件_ `value` `units` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="fe9ff-121">屬性的值 `value` 必須是數位。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="fe9ff-122">如果 quantity 物件具有屬性和屬性，則它是一個「 _限定數量」物件_ `lower` `upper` `units` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="fe9ff-123">和屬性的值 `lower` `upper` 必須是數位。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="fe9ff-124">「限定數量」物件的屬性（property）的 `value` 值可以是數位。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="fe9ff-125">如果 quantity 物件具有屬性和屬性（property）及其屬性（property），則此物件為「 _稀疏陣列數量」物件_ `format` `values` `units` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="fe9ff-126">的值 `format` 必須是字串 `sparse` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="fe9ff-127">屬性的值 `values` 必須是陣列。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="fe9ff-128">的每個元素都 `values` 必須是代表稀疏陣列數量之索引和值的陣列。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="fe9ff-129">「稀疏陣列數量」物件的每個專案的索引，在整個「稀疏陣列數量」物件中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="fe9ff-130">如果具有值的索引存在，剖析器就必須將「 `0` 稀疏陣列數量」物件視為完全不存在該索引的「稀疏陣列數量」物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="fe9ff-131">Quantity 物件必須是</span><span class="sxs-lookup"><span data-stu-id="fe9ff-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="fe9ff-132">簡單數量物件，</span><span class="sxs-lookup"><span data-stu-id="fe9ff-132">a simple quantity object,</span></span>
- <span data-ttu-id="fe9ff-133">限定數量物件，或</span><span class="sxs-lookup"><span data-stu-id="fe9ff-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="fe9ff-134">稀疏陣列數量物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="fe9ff-135">範例</span><span class="sxs-lookup"><span data-stu-id="fe9ff-135">Examples</span></span> ###

<span data-ttu-id="fe9ff-136">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-136">This section is informative.</span></span>

<span data-ttu-id="fe9ff-137">代表 $ 1.9844146837 \Mathrm{Ha} $ 的簡單數量 \, ：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="fe9ff-138">代表超過間隔 $ [-7，-6] \Mathrm{Ha} $ 之統一分佈的限定數量 \, ：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="fe9ff-139">以下是具有等於和元素等於的稀疏陣列數量 `[1, 2]` `hello` `[3, 4]` `world` ：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="fe9ff-140">格式區段</span><span class="sxs-lookup"><span data-stu-id="fe9ff-140">Format Section</span></span> ##

<span data-ttu-id="fe9ff-141">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-141">This section is normative.</span></span>

<span data-ttu-id="fe9ff-142">Broombridge 物件必須具有屬性 `format` ，其值為 JSON 物件，且其中一個屬性稱為 `version` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="fe9ff-143">`version`屬性必須具有值 `"0.2"` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="fe9ff-144">範例</span><span class="sxs-lookup"><span data-stu-id="fe9ff-144">Example</span></span> ###

<span data-ttu-id="fe9ff-145">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="fe9ff-146">問題描述區段</span><span class="sxs-lookup"><span data-stu-id="fe9ff-146">Problem Description Section</span></span> ##

<span data-ttu-id="fe9ff-147">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-147">This section is normative.</span></span>

<span data-ttu-id="fe9ff-148">Broombridge 物件必須有一個屬性 `problem_description` ，其值為 JSON 陣列。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="fe9ff-149">屬性值中的每個專案都 `problem_description` 必須是描述一組積分的 JSON 物件，如本節其餘部分所述。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="fe9ff-150">在本節的其餘部分，「問題描述物件」一詞會參考 Broombridge 物件的屬性值中的專案 `problem_description` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="fe9ff-151">每個問題描述物件都必須有一個屬性 `metadata` ，其值為 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="fe9ff-152">的值 `metadata` 可能是空的 JSON 物件 (也就是 `{}`) ，或可能包含由實作項所定義的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="fe9ff-153">Hamiltonian 區段</span><span class="sxs-lookup"><span data-stu-id="fe9ff-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="fe9ff-154">概觀</span><span class="sxs-lookup"><span data-stu-id="fe9ff-154">Overview</span></span> ####

<span data-ttu-id="fe9ff-155">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-155">This section is informative.</span></span>

<span data-ttu-id="fe9ff-156">`hamiltonian`每個問題描述物件的屬性會說明特定量子化學問題的 Hamiltonian，方法是將它的一或兩個主體詞彙列為稀疏陣列的實數。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="fe9ff-157">每個問題描述物件所描述的 Hamiltonian 運算子採用格式</span><span class="sxs-lookup"><span data-stu-id="fe9ff-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="fe9ff-158">$ $ H = \sum \_ \{ i，j \} \sum \_ {\sigma\in \\ {\uparrow，\downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i，\sigma} a \_ {j，\sigma} + \frac {1} {2} \sum \_ \{ i，j，k，l \} \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i，\sigma} a ^ \dagger \_ {k，\rho} a \_ {l，\rho} a \_ {j，\sigma}，$ $</span><span class="sxs-lookup"><span data-stu-id="fe9ff-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="fe9ff-159">這裡 $h _ {ijkl} = (ij | kl) $ in Mulliken 慣例。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="fe9ff-160">為了清楚起見，electron 一詞是</span><span class="sxs-lookup"><span data-stu-id="fe9ff-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="fe9ff-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left ( \frac {1} {2} \nabla ^ 2 + \sum \_ {a} \frac{Z \_ A} {| x-x \_ a |} \right) \psi \_ j (x) ，$ $</span><span class="sxs-lookup"><span data-stu-id="fe9ff-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="fe9ff-162">這兩個 electron 詞彙是</span><span class="sxs-lookup"><span data-stu-id="fe9ff-162">and the two-electron term is</span></span>

<span data-ttu-id="fe9ff-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2) 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="fe9ff-164">如同屬性之每個元素的[ `basis_set` 屬性](#basis-set-object)描述中所述 `integral_sets` ，我們會進一步明確假設使用的基礎函數是真正的值。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="fe9ff-165">這可讓我們在詞彙之間使用下列 symmetries，以壓縮 Hamiltonian 的表示。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="fe9ff-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="fe9ff-167">內容</span><span class="sxs-lookup"><span data-stu-id="fe9ff-167">Contents</span></span> ####

<span data-ttu-id="fe9ff-168">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-168">This section is normative.</span></span>

<span data-ttu-id="fe9ff-169">每個問題描述物件都必須有一個屬性 `hamiltonian` ，其值為 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="fe9ff-170">屬性的值 `hamiltonian` 稱為 Hamiltonian 物件，而且必須具有屬性 `one_electron_integrals` ， `two_electron_integrals` 如本節的其餘部分所述。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="fe9ff-171">每個問題描述物件都必須有一個屬性 `coulomb_repulsion` ，其值為簡單數量物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="fe9ff-172">每個問題描述物件都必須有一個屬性 `energy_offet` ，其值為簡單數量物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="fe9ff-173">記和相加的值會 `coulomb_repulsion` `energy_offet` 一起捕捉到 Hamiltonian 的身分識別字詞。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="fe9ff-174">一個 Electron 的積分物件</span><span class="sxs-lookup"><span data-stu-id="fe9ff-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="fe9ff-175">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-175">This section is normative.</span></span>

<span data-ttu-id="fe9ff-176">`one_electron_integrals`Hamiltonian 物件的屬性必須是稀疏陣列數量，其索引為兩個整數且其值為數字。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="fe9ff-177">每個詞彙都必須有 `[i, j]` 的索引 `i >= j` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="fe9ff-178">記這會反映 $h _ {ij} = h_ {ji} $ 的對稱，這是 Hamiltonian Hermitian 的事實結果。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="fe9ff-179">範例</span><span class="sxs-lookup"><span data-stu-id="fe9ff-179">Example</span></span> ######

<span data-ttu-id="fe9ff-180">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-180">This section is informative.</span></span>

<span data-ttu-id="fe9ff-181">下列稀疏陣列數量代表 Hamiltonian $ $ H = \left (-5.0 (^ \{ \dagger \} \_ {1，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {1，\downarrow} ) + 0.17 (^ \{ \dagger \} \_ {2，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {2，\uparrow} + a ^ \{ \dagger \} \_ {2，\downarrow} a { \_ 1，\downarrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {2，\downarrow} ) \right) \\ ，\mathrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="fe9ff-182">Broombridge 使用以1為基礎的索引。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="fe9ff-183">雙 Electron 的積分物件</span><span class="sxs-lookup"><span data-stu-id="fe9ff-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="fe9ff-184">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-184">This section is normative.</span></span>

<span data-ttu-id="fe9ff-185">`two_electron_integrals`Hamiltonian 物件的屬性必須是稀疏陣列數量，並有一個稱為的額外屬性 `index_convention` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="fe9ff-186">值的每個元素都 `two_electron_integrals` 必須有四個索引。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="fe9ff-187">每個 `two_electron_integrals` 屬性都必須有 `index_convention` 屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="fe9ff-188">屬性的值 `index_convention` 必須是 [表 1] 所列的其中一個允許值。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="fe9ff-189">如果的值 `index_convention` 為 `mulliken` ，則針對每個 `two_electron_integrals` 稀疏陣列數量的元素，載入 Broombridge 檔的剖析器必須具現化等於雙 Electron 運算子的 Hamiltonian 詞彙 $h _ {i，j、k、l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $、$j $、$k $ 和 $l $ 必須是值至少為1的整數，其中 $h _ {i，j，k，l} $ 是 `[i, j, k, l, h(i, j, k, l)]` 稀疏陣列數量的元素。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="fe9ff-190">對稱</span><span class="sxs-lookup"><span data-stu-id="fe9ff-190">Symmetries</span></span> ######

<span data-ttu-id="fe9ff-191">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-191">This section is normative.</span></span>

<span data-ttu-id="fe9ff-192">如果 `index_convention` 物件的屬性 `two_electron_integrals` 等於 `mulliken` ，則如果有具有索引的元素 `[i, j, k, l]` ，則必須有下列索引，除非它們等於 `[i, j, k, l]` ：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="fe9ff-193">因為 `index_convention` 屬性是「稀疏數量」物件，所以不會在不同的元素上重複任何索引。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="fe9ff-194">尤其是，如果有具有索引的元素 `[i, j, k, l]` ，則其他專案可能會有這些索引。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="fe9ff-195">範例</span><span class="sxs-lookup"><span data-stu-id="fe9ff-195">Example</span></span> #######

<span data-ttu-id="fe9ff-196">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-196">This section is informative.</span></span>

<span data-ttu-id="fe9ff-197">下列物件會指定 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="fe9ff-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="fe9ff-198">$ $ H = \frac12 \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} \Biggr ( 1.6 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {1，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {2，\rho} a \_ {3，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {2，\rho} a \_ {3，\sigma} $ $ $-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {1，\rho} a \_ {6，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {1，\Rho} a \_ {6，\sigma}\Biggr) \\ ，\textrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a><span data-ttu-id="fe9ff-199">初始狀態區段</span><span class="sxs-lookup"><span data-stu-id="fe9ff-199">Initial State Section</span></span> ###

<span data-ttu-id="fe9ff-200">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-200">This section is normative.</span></span>

<span data-ttu-id="fe9ff-201">`initial_state_suggestion`值為 JSON 陣列的物件會指定對指定 Hamiltonian 感興趣的初始量子狀態。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="fe9ff-202">屬性值中的每個專案都 `initial_state_suggestion` 必須是描述一個量子狀態的 JSON 物件，如本節的其餘部分所述。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="fe9ff-203">在本節的其餘部分，「狀態物件」一詞會參考 Broombridge 物件的屬性值中的專案 `initial_state_suggestion` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="fe9ff-204">狀態物件</span><span class="sxs-lookup"><span data-stu-id="fe9ff-204">State object</span></span> ####

<span data-ttu-id="fe9ff-205">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-205">This section is normative.</span></span>

<span data-ttu-id="fe9ff-206">每個狀態物件都必須有一個 `label` 包含字串的屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="fe9ff-207">每個狀態物件都必須有 `method` 屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="fe9ff-208">屬性的值 `method` 必須是 [表 3] 中所列的其中一個允許的值。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="fe9ff-209">每個狀態物件都有一個屬性， `energy` 其值必須是簡單數量的物件。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="fe9ff-210">如果屬性的值 `method` 為 `sparse_multi_configurational` ，則狀態物件必須具有 `superposition` 包含基礎狀態陣列及其未標準化 amplitudes 的屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="fe9ff-211">例如，初始狀態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) + 0.2 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) } {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} ，$ $，其中 $ \ket{E} $ 有能源 $0.987 \textrm{Ha} $，以</span><span class="sxs-lookup"><span data-stu-id="fe9ff-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="fe9ff-212">如果屬性的值 `method` 為 `unitary_coupled_cluster` ，則狀態物件必須具有 `cluster_operator` 其值為 JSON 物件的屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="fe9ff-213">JSON 物件必須具有 `reference_state` 其值為基礎狀態的屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="fe9ff-214">JSON 物件可能具有屬性， `one_body_amplitudes` 其值為單一主體叢集運算子及其 amplitudes 的陣列。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="fe9ff-215">JSON 物件可能具有屬性， `two_body_amplitudes` 其值為兩個主體叢集運算子的陣列及其 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="fe9ff-216">包含基礎狀態的陣列及其未標準化的 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="fe9ff-217">例如，state $ $ \ket{\text{reference}} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} ，$ $</span><span class="sxs-lookup"><span data-stu-id="fe9ff-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="fe9ff-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}，$ $</span><span class="sxs-lookup"><span data-stu-id="fe9ff-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="fe9ff-219">$ $ T = 0.1 a ^ {\dagger} \_ {3，\uparrow}a \_ {2，\downarrow} + 0.2 a ^ {\dagger} \_ {2，\uparrow}a \_ {2，\downarrow}-0.3 a ^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\downarrow}a \_ {3，\uparrow}a \_ {2，\downarrow} $ $ 由</span><span class="sxs-lookup"><span data-stu-id="fe9ff-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="fe9ff-220">基礎 Set 物件</span><span class="sxs-lookup"><span data-stu-id="fe9ff-220">Basis Set Object</span></span> ####

<span data-ttu-id="fe9ff-221">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-221">This section is normative.</span></span>

<span data-ttu-id="fe9ff-222">每個問題描述物件都可以有 `basis_set` 屬性。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="fe9ff-223">如果有的話，屬性的值 `basis_set` 必須是具有兩個屬性的物件： `type` 和 `name` 。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="fe9ff-224">由屬性值所識別的基礎函數 `basis_set` 必須是實值。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="fe9ff-225">在此規格的未來版本中，假設所有基礎函數都是真正的值。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="fe9ff-226">資料表和清單</span><span class="sxs-lookup"><span data-stu-id="fe9ff-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="fe9ff-227">表 1.</span><span class="sxs-lookup"><span data-stu-id="fe9ff-227">Table 1.</span></span> <span data-ttu-id="fe9ff-228">允許的實體單位</span><span class="sxs-lookup"><span data-stu-id="fe9ff-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="fe9ff-229">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-229">This section is normative.</span></span>

<span data-ttu-id="fe9ff-230">指定單位的任何字串都必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="fe9ff-231">剖析器和生產者必須將下列簡單數量物件視為對等：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="fe9ff-232">表 2.</span><span class="sxs-lookup"><span data-stu-id="fe9ff-232">Table 2.</span></span> <span data-ttu-id="fe9ff-233">允許的索引慣例</span><span class="sxs-lookup"><span data-stu-id="fe9ff-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="fe9ff-234">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-234">This section is normative.</span></span>

<span data-ttu-id="fe9ff-235">指定索引慣例的任何字串都必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="fe9ff-236">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-236">This section is informative.</span></span>

<span data-ttu-id="fe9ff-237">此規格的未來版本可能會引進額外的索引慣例。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="fe9ff-238">索引慣例的解讀</span><span class="sxs-lookup"><span data-stu-id="fe9ff-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="fe9ff-239">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="fe9ff-240">表格 3.</span><span class="sxs-lookup"><span data-stu-id="fe9ff-240">Table 3.</span></span> <span data-ttu-id="fe9ff-241">允許的狀態方法</span><span class="sxs-lookup"><span data-stu-id="fe9ff-241">Allowed State methods</span></span> ###

<span data-ttu-id="fe9ff-242">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-242">This section is normative.</span></span>

<span data-ttu-id="fe9ff-243">任何指定 state 方法的字串都必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe9ff-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="fe9ff-244">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-244">This section is informative.</span></span>

<span data-ttu-id="fe9ff-245">此規格的未來版本可能會引進其他狀態方法。</span><span class="sxs-lookup"><span data-stu-id="fe9ff-245">Additional state methods may be introduced in future versions of this specification.</span></span>
