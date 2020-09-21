---
title: 'Broombridge 架構規格 (ver 0.1) '
description: 詳細說明 Microsoft 量子化學程式庫的 Broombridge 量子化學架構 v 0.1 規格。
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: b99c90c434958f7b04712580789b203766cd084d
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835735"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="1d8f6-103">Broombridge 規格 v 0。1</span><span class="sxs-lookup"><span data-stu-id="1d8f6-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="1d8f6-104">本檔中的關鍵字「必須」、「不得」、「必要」、「應該」、「不應」、「應該」、「不應」、「建議」、「可能」和「選擇性」，如 [RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="1d8f6-105">任何標題為「附注」、「資訊」或「警告」的提要欄位都有提供資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="1d8f6-106">簡介</span><span class="sxs-lookup"><span data-stu-id="1d8f6-106">Introduction</span></span> ##

<span data-ttu-id="1d8f6-107">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-107">This section is informative.</span></span>

<span data-ttu-id="1d8f6-108">Broombridge 檔的目的是要傳達量子化學中模擬問題的實例，以使用量子模擬和程式設計工具鏈進行處理。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="1d8f6-109">序列化</span><span class="sxs-lookup"><span data-stu-id="1d8f6-109">Serialization</span></span> ##

<span data-ttu-id="1d8f6-110">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-110">This section is normative.</span></span>

<span data-ttu-id="1d8f6-111">Broombridge 檔必須序列化為 [YAML 1.2 檔](http://yaml.org/spec/) ，以表示 [RFC 4627](https://tools.ietf.org/html/rfc4627) 區段2.2 中所述的 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="1d8f6-112">序列化為 YAML 的物件必須具有 `"$schema"` 其值為的屬性 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` ，而且必須根據 JSON 架構 draft-06 規格 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 來有效。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="1d8f6-113">針對此規格的其餘部分，「Broombridge 物件」會參考從 Broombridge YAML 檔案還原序列化的 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="1d8f6-114">除非另有明確注明，否則物件不能有在本檔中明確指定的屬性以外的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="1d8f6-115">其他定義</span><span class="sxs-lookup"><span data-stu-id="1d8f6-115">Additional Definitions</span></span> ##

<span data-ttu-id="1d8f6-116">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="1d8f6-117">Quantity 物件</span><span class="sxs-lookup"><span data-stu-id="1d8f6-117">Quantity Objects</span></span> ###

<span data-ttu-id="1d8f6-118">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-118">This section is normative.</span></span>

<span data-ttu-id="1d8f6-119">_Quantity 物件_是一個 JSON 物件，且 `units` 其值必須是 [表 1] 所列的其中一個允許值的屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="1d8f6-120">如果 quantity 物件除了屬性之外還具有單一屬性，則它是 _簡單數量的物件_ `value` `units` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="1d8f6-121">屬性的值 `value` 必須是數位。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="1d8f6-122">如果 quantity 物件具有屬性和屬性，則它是一個「 _限定數量」物件_ `lower` `upper` `units` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="1d8f6-123">和屬性的值 `lower` `upper` 必須是數位。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="1d8f6-124">「限定數量」物件的屬性（property）的 `value` 值可以是數位。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="1d8f6-125">如果 quantity 物件具有屬性和屬性（property）及其屬性（property），則此物件為「 _稀疏陣列數量」物件_ `format` `values` `units` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="1d8f6-126">的值 `format` 必須是字串 `sparse` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="1d8f6-127">屬性的值 `values` 必須是陣列。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="1d8f6-128">的每個元素都 `values` 必須是代表稀疏陣列數量之索引和值的陣列。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="1d8f6-129">「稀疏陣列數量」物件的每個專案的索引，在整個「稀疏陣列數量」物件中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="1d8f6-130">如果具有值的索引存在，剖析器就必須將「 `0` 稀疏陣列數量」物件視為完全不存在該索引的「稀疏陣列數量」物件。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="1d8f6-131">Quantity 物件必須是</span><span class="sxs-lookup"><span data-stu-id="1d8f6-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="1d8f6-132">簡單數量物件，</span><span class="sxs-lookup"><span data-stu-id="1d8f6-132">a simple quantity object,</span></span>
- <span data-ttu-id="1d8f6-133">限定數量物件，或</span><span class="sxs-lookup"><span data-stu-id="1d8f6-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="1d8f6-134">稀疏陣列數量物件。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="1d8f6-135">範例</span><span class="sxs-lookup"><span data-stu-id="1d8f6-135">Examples</span></span> ###

<span data-ttu-id="1d8f6-136">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-136">This section is informative.</span></span>

<span data-ttu-id="1d8f6-137">代表 $ 1.9844146837 \Mathrm{Ha} $ 的簡單數量 \, ：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="1d8f6-138">代表超過間隔 $ [-7，-6] \Mathrm{Ha} $ 之統一分佈的限定數量 \, ：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="1d8f6-139">以下是具有等於和元素等於的稀疏陣列數量 `[1, 2]` `hello` `[3, 4]` `world` ：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="1d8f6-140">格式區段</span><span class="sxs-lookup"><span data-stu-id="1d8f6-140">Format Section</span></span> ##

<span data-ttu-id="1d8f6-141">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-141">This section is normative.</span></span>

<span data-ttu-id="1d8f6-142">Broombridge 物件必須具有屬性 `format` ，其值為 JSON 物件，且其中一個屬性稱為 `version` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="1d8f6-143">`version`屬性必須具有值 `"0.1"` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="1d8f6-144">範例</span><span class="sxs-lookup"><span data-stu-id="1d8f6-144">Example</span></span> ###

<span data-ttu-id="1d8f6-145">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="1d8f6-146">整數集區段</span><span class="sxs-lookup"><span data-stu-id="1d8f6-146">Integral Sets Section</span></span> ##

<span data-ttu-id="1d8f6-147">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-147">This section is normative.</span></span>

<span data-ttu-id="1d8f6-148">Broombridge 物件必須有一個屬性 `integral_sets` ，其值為 JSON 陣列。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="1d8f6-149">屬性值中的每個專案都 `integral_sets` 必須是描述一組積分的 JSON 物件，如本節其餘部分所述。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="1d8f6-150">在本節的其餘部分，「整陣列物件」一詞會參考 Broombridge 物件的屬性值中的專案 `integral_sets` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="1d8f6-151">每個整陣列物件都必須有一個屬性 `metadata` ，其值為 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="1d8f6-152">的值 `metadata` 可能是空的 JSON 物件 (也就是 `{}`) ，或可能包含由實作項所定義的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="1d8f6-153">Hamiltonian 區段</span><span class="sxs-lookup"><span data-stu-id="1d8f6-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="1d8f6-154">概觀</span><span class="sxs-lookup"><span data-stu-id="1d8f6-154">Overview</span></span> ####

<span data-ttu-id="1d8f6-155">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-155">This section is informative.</span></span>

<span data-ttu-id="1d8f6-156">`hamiltonian`每個整陣列物件的屬性，會將它的一或兩個內文詞彙列為稀疏陣列的實數，以描述特定量子化學問題的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="1d8f6-157">每個整數集物件所描述的 Hamiltonian 運算子採用格式</span><span class="sxs-lookup"><span data-stu-id="1d8f6-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="1d8f6-158">$ $ H = \sum \_ \{ i，j \} \sum \_ {\sigma\in \\ {\uparrow，\downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i，\sigma} a \_ {j，\sigma} + \frac {1} {2} \sum \_ \{ i，j，k，l \} \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i，\sigma} a ^ \dagger \_ {k，\rho} a \_ {l，\rho} a \_ {j，\sigma}，$ $</span><span class="sxs-lookup"><span data-stu-id="1d8f6-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="1d8f6-159">這裡 $h _ {ijkl} = (ij | kl) $ in Mulliken 慣例。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="1d8f6-160">為了清楚起見，electron 一詞是</span><span class="sxs-lookup"><span data-stu-id="1d8f6-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="1d8f6-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left ( \frac {1} {2} \nabla ^ 2 + \sum \_ {a} \frac{Z \_ A} {| x-x \_ a |} \right) \psi \_ j (x) ，$ $</span><span class="sxs-lookup"><span data-stu-id="1d8f6-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="1d8f6-162">這兩個 electron 詞彙是</span><span class="sxs-lookup"><span data-stu-id="1d8f6-162">and the two-electron term is</span></span>

<span data-ttu-id="1d8f6-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2) 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="1d8f6-164">如同屬性之每個元素的[ `basis_set` 屬性](#basis-set-object)描述中所述 `integral_sets` ，我們會進一步明確假設使用的基礎函數是真正的值。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="1d8f6-165">這可讓我們在詞彙之間使用下列 symmetries，以壓縮 Hamiltonian 的表示。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="1d8f6-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="1d8f6-167">內容</span><span class="sxs-lookup"><span data-stu-id="1d8f6-167">Contents</span></span> ####

<span data-ttu-id="1d8f6-168">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-168">This section is normative.</span></span>

<span data-ttu-id="1d8f6-169">每個整陣列都必須有一個屬性 `hamiltonian` ，其值為 JSON 物件。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="1d8f6-170">屬性的值 `hamiltonian` 稱為 Hamiltonian 物件，而且必須具有屬性 `one_electron_integrals` ， `two_electron_integrals` 如本節的其餘部分所述。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="1d8f6-171">Hamiltonian 物件也可以有屬性 `particle_hole_representation` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="1d8f6-172">如果有的話，的值 `particle_hole_representation` 必須遵循本節其餘部分所述的格式。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="1d8f6-173">一個 Electron 的積分物件</span><span class="sxs-lookup"><span data-stu-id="1d8f6-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="1d8f6-174">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-174">This section is normative.</span></span>

<span data-ttu-id="1d8f6-175">`one_electron_integrals`Hamiltonian 物件的屬性必須是稀疏陣列數量，其索引為兩個整數且其值為數字。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="1d8f6-176">每個詞彙都必須有 `[i, j]` 的索引 `i >= j` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="1d8f6-177">記這會反映 $h _ {ij} = h_ {ji} $ 的對稱，這是 Hamiltonian Hermitian 的事實結果。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="1d8f6-178">範例</span><span class="sxs-lookup"><span data-stu-id="1d8f6-178">Example</span></span> ######

<span data-ttu-id="1d8f6-179">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-179">This section is informative.</span></span>

<span data-ttu-id="1d8f6-180">下列稀疏陣列數量代表 Hamiltonian $ $ H = \left (-5.0 (^ \{ \dagger \} \_ {1，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {1，\downarrow} ) + 0.17 (^ \{ \dagger \} \_ {2，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {2，\uparrow} + a ^ \{ \dagger \} \_ {2，\downarrow} a { \_ 1，\downarrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {2，\downarrow} ) \right) \\ ，\mathrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="1d8f6-181">Broombridge 使用以1為基礎的索引。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="1d8f6-182">雙 Electron 的積分物件</span><span class="sxs-lookup"><span data-stu-id="1d8f6-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="1d8f6-183">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-183">This section is normative.</span></span>

<span data-ttu-id="1d8f6-184">`two_electron_integrals`Hamiltonian 物件的屬性必須是稀疏陣列數量，並有一個稱為的額外屬性 `index_convention` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="1d8f6-185">值的每個元素都 `two_electron_integrals` 必須有四個索引。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="1d8f6-186">每個 `two_electron_integrals` 屬性都必須有 `index_convention` 屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="1d8f6-187">屬性的值 `index_convention` 必須是 [表 1] 所列的其中一個允許值。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="1d8f6-188">如果的值 `index_convention` 為 `mulliken` ，則針對每個 `two_electron_integrals` 稀疏陣列數量的元素，載入 Broombridge 檔的剖析器必須具現化等於雙 Electron 運算子的 Hamiltonian 詞彙 $h _ {i，j，k、l} ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $、$j $、$k $ 和 $l $ 必須是包含範圍中的整數，介於1到整陣列物件的屬性所指定的電子數目之間 `n_electrons` ，其中 $h _ {i，j，k，l} $ 是 `[i, j, k, l, h(i, j, k, l)]` 稀疏陣列數量的元素。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="1d8f6-189">對稱</span><span class="sxs-lookup"><span data-stu-id="1d8f6-189">Symmetries</span></span> ######

<span data-ttu-id="1d8f6-190">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-190">This section is normative.</span></span>

<span data-ttu-id="1d8f6-191">如果 `index_convention` 物件的屬性 `two_electron_integrals` 等於 `mulliken` ，則如果有具有索引的元素 `[i, j, k, l]` ，則必須有下列索引，除非它們等於 `[i, j, k, l]` ：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="1d8f6-192">因為 `index_convention` 屬性是「稀疏數量」物件，所以不會在不同的元素上重複任何索引。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="1d8f6-193">尤其是，如果有具有索引的元素 `[i, j, k, l]` ，則其他專案可能會有這些索引。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="1d8f6-194">範例</span><span class="sxs-lookup"><span data-stu-id="1d8f6-194">Example</span></span> #######

<span data-ttu-id="1d8f6-195">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-195">This section is informative.</span></span>

<span data-ttu-id="1d8f6-196">下列物件會指定 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="1d8f6-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="1d8f6-197">$ $ H = \frac12 \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} \Biggr ( 1.6 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {1，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {2，\rho} a \_ {3，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {2，\rho} a \_ {3，\sigma} $ $ $-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {1，\rho} a \_ {6，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {1，\Rho} a \_ {6，\sigma}\Biggr) \\ ，\textrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="1d8f6-198">物件-洞標記法物件</span><span class="sxs-lookup"><span data-stu-id="1d8f6-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="1d8f6-199">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-199">This section is normative.</span></span>

<span data-ttu-id="1d8f6-200">「物件」-「洞表示」物件會指定所儲存的積分是針對「粒子」標記法所定義，其中建立和 annihilation 運算子會從所使用的參考狀態中描述 excitations，例如 Hf – Fock 狀態。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="1d8f6-201">物件是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="1d8f6-202">如果未指定物件，則會將 Hamiltonian 解釋為在粒子標記法中未提供。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="1d8f6-203">如果存在，的值 `particle_hole_representation` 必須是「稀疏陣列數量」物件，其索引為四個整數，而且其值為數字和字串。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="1d8f6-204">每個元素之值的字串部分必須只包含字元 `'+'` ，並 `'-'` 指定詞彙中的指定因數是否為物件-洞標記法中的建立或 annihilation 運算子。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="1d8f6-205">例如 `"-+++"` ，coresponds 至在網站上建立的洞 $i $ 和在網站上建立的粒子 $j、k $ 和 $l $。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8f6-206">因為的值 `particle_hole_representation` 是稀疏陣列數量物件，所以 `unit` `format` 必須指定和屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="1d8f6-207">[表 1] 列出可接受的單位。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="1d8f6-208">`format`需要屬性，並指出 Hamiltonian 係數是否指定為密集或稀疏陣列。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="1d8f6-209">在目前的版本中，只支援稀疏陣列，並將所有未指定的元素轉譯為 $0 $，但未來的版本可能會新增其他屬性值的支援 `format` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="1d8f6-210">初始狀態區段</span><span class="sxs-lookup"><span data-stu-id="1d8f6-210">Initial State Section</span></span> ###

<span data-ttu-id="1d8f6-211">Initial_state_suggestion 物件指定指定 Hamiltonian 的相關初始量子狀態。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="1d8f6-212">此物件必須是 JSON 物件的陣列 `state` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="1d8f6-213">狀態物件</span><span class="sxs-lookup"><span data-stu-id="1d8f6-213">State object</span></span> ####

<span data-ttu-id="1d8f6-214">每個狀態都代表已佔用 orbitals 的迭加。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="1d8f6-215">每個狀態物件都必須有一個 `label` 包含字串的屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="1d8f6-216">每個狀態物件都必須有一個 `superposition` 包含基礎狀態陣列及其未標準化 amplitudes 的屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="1d8f6-217">例如，初始狀態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) + 0.2 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) } {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ 由</span><span class="sxs-lookup"><span data-stu-id="1d8f6-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="1d8f6-218">基礎 Set 物件</span><span class="sxs-lookup"><span data-stu-id="1d8f6-218">Basis Set Object</span></span> ####

<span data-ttu-id="1d8f6-219">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-219">This section is normative.</span></span>

<span data-ttu-id="1d8f6-220">每個整陣列物件都可以有 `basis_set` 屬性。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="1d8f6-221">如果有的話，屬性的值 `basis_set` 必須是具有兩個屬性的物件： `type` 和 `name` 。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="1d8f6-222">由屬性值所識別的基礎函數 `basis_set` 必須是實值。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8f6-223">在此規格的未來版本中，假設所有基礎函數都是真正的值。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="1d8f6-224">資料表和清單</span><span class="sxs-lookup"><span data-stu-id="1d8f6-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="1d8f6-225">表 1.</span><span class="sxs-lookup"><span data-stu-id="1d8f6-225">Table 1.</span></span> <span data-ttu-id="1d8f6-226">允許的實體單位</span><span class="sxs-lookup"><span data-stu-id="1d8f6-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="1d8f6-227">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-227">This section is normative.</span></span>

<span data-ttu-id="1d8f6-228">指定單位的任何字串都必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="1d8f6-229">剖析器和生產者必須將下列簡單數量物件視為對等：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="1d8f6-230">表 2.</span><span class="sxs-lookup"><span data-stu-id="1d8f6-230">Table 2.</span></span> <span data-ttu-id="1d8f6-231">允許的索引慣例</span><span class="sxs-lookup"><span data-stu-id="1d8f6-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="1d8f6-232">本節為標準化。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-232">This section is normative.</span></span>

<span data-ttu-id="1d8f6-233">指定索引慣例的任何字串都必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1d8f6-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="1d8f6-234">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-234">This section is informative.</span></span>

<span data-ttu-id="1d8f6-235">此規格的未來版本可能會引進額外的索引慣例。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="1d8f6-236">索引慣例的解讀</span><span class="sxs-lookup"><span data-stu-id="1d8f6-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="1d8f6-237">本節說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1d8f6-237">This section is informative.</span></span>
