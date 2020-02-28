---
title: Broombridge 架構規格（0.2 版）
description: 詳細說明 Microsoft 量子化學程式庫的 Broombridge 量子化學架構 v 0.2 規格。
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907268"
---
# <a name="broombridge-specification-v02"></a>Broombridge 規格 v 0。2 #

本檔中的關鍵字「必須」、「不得」、「必要」、「應」、「不得」、「應該」、「不應」、「建議」、「可能」和「選擇性」，如[RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。

具有標題「附注」、「資訊」或「警告」的任何提要欄位都有資訊。

## <a name="introduction"></a>簡介 ##

這一節有資訊。

Broombridge 檔的目的是要在量子化學中傳達模擬問題的實例，以使用量子模擬和程式設計工具鏈進行處理。

## <a name="serialization"></a>序列化 ##

本節為標準化。

Broombridge 檔必須序列化為代表 JSON 物件的[YAML 1.2 檔](http://yaml.org/spec/)，如[RFC 4627](https://tools.ietf.org/html/rfc4627)區段2.2 中所述。
序列化至 YAML 的物件必須具有 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`值的屬性 `"$schema"`，而且必須根據 JSON 架構 draft-06 規格 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 來有效。

在此規格的其餘部分中，「Broombridge 物件」將會參考從 Broombridge YAML 檔案還原序列化的 JSON 物件。

除非另有明確注明，否則物件除了在此檔中明確指定的屬性以外，不能有其他內容。

## <a name="additional-definitions"></a>其他定義 ##

本節為標準化。

### <a name="quantity-objects"></a>數量物件 ###

本節為標準化。

_Quantity 物件_是 JSON 物件，而且必須具有屬性 `units` 其值是 [表 1] 中所列的其中一個允許值。

Quantity 物件是一個_簡單數量的物件_，如果它除了其 `units` 屬性之外，還 `value` 一個屬性。
`value` 屬性的值必須是數位。

Quantity 物件是一個_限定數量物件_，如果它除了其 `units` 屬性外，還有 `lower` 和 `upper` 屬性。
`lower` 和 `upper` 屬性的值必須是數位。
限定數量物件可以有屬性 `value` 其值為數字。

Quantity 物件是一個_稀疏陣列數量物件_，如果它的屬性 `format`，且屬性 `values` 除了其 `units` 屬性之外。
`format` 的值必須是 `sparse`的字串。
`values` 屬性的值必須是陣列。
`values` 的每個元素都必須是代表稀疏陣列數量之索引和值的陣列。

Sparse 陣列數量物件的每個元素的索引在整個 sparse 陣列數量物件中必須是唯一的。
如果具有 `0`值的索引存在，則剖析器必須將 sparse 陣列數量物件視為完全不存在該索引的稀疏陣列數量物件。


Quantity 物件必須是

- 簡單數量物件，
- 限定數量物件，或
- 稀疏陣列數量物件。


### <a name="examples"></a>範例 ###

這一節有資訊。

代表 $ 1.9844146837\,\mathrm{Ha} $ 的簡單數量：

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

代表間隔 $ [-7，-6]\,\mathrm{Ha} $ 之統一散發的限定數量：

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

以下是具有元素 `[1, 2]` 等於 `hello` 的稀疏陣列數量，以及 `[3, 4]` 等於 `world`的元素：

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Format 區段 ##

本節為標準化。

Broombridge 物件必須具有屬性 `format`，其值為 JSON 物件，其中有一個稱為 `version`的屬性。
`version` 屬性的值必須 `"0.2"`。

### <a name="example"></a>範例 ###

這一節有資訊。

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>問題描述區段 ##

本節為標準化。

Broombridge 物件必須具有屬性 `problem_description` 其值為 JSON 陣列。
`problem_description` 屬性值中的每個專案都必須是描述一組整型的 JSON 物件，如本節其餘部分所述。
在本節的其餘部分中，「問題描述物件」一詞會參考 Broombridge 物件的 `problem_description` 屬性值中的專案。

每個問題描述物件都必須具有屬性 `metadata`，其值為 JSON 物件。
`metadata` 的值可能是空的 JSON 物件（也就是 `{}`），或可能包含實作項所定義的其他屬性。

### <a name="hamiltonian-section"></a>Hamiltonian 區段 ###

#### <a name="overview"></a>概觀 ####

這一節有資訊。

每個問題描述物件的 `hamiltonian` 屬性會描述特定量子化學問題的 Hamiltonian，其方式是將其一對一和二主體詞彙列示為實數陣列。
每個問題描述物件所描述的 Hamiltonian 運算子都會採用表單

$ $ H = \sum\_\{i，j\}\sum\_{\sigma\in\\{\uparrow，\downarrow\\}} H\_\{ij\} a ^\{\dagger\}\_{i，\sigma} a\_{j，\sigma} + \frac{1}{2}\sum\_\{i，j，k，l\}\sum\_{\sigma，\rho\in\\{\uparrow，\downarrow\\}} h\_{ijkl} a ^ \dagger\_{i，\sigma} ^ \dagger\_{k，\rho}\_{l，\rho} a\_{j，\sigma}，$ $

這裡 $h _ {ijkl} = （ij | kl） $ in Mulliken 慣例。

為了清楚起見，electron 一詞是

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ *\_i （x） \left （\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |} \right） \psi\_j （x），$ $

而這兩個 electron 的詞彙是

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i （x\_1） \psi\_j （x\_1） \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*l （x \}2） \psi。\_\_\_
$$

如 `integral_sets` 屬性之每個元素的[`basis_set` 屬性](#basis-set-object)說明中所述，我們會進一步明確假設使用的基礎函數是實際值。
這可讓我們在詞彙之間使用下列 symmetries 來壓縮 Hamiltonian 的標記法。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>內容 ####

本節為標準化。

每個問題描述物件都必須具有屬性 `hamiltonian`，其值為 JSON 物件。
`hamiltonian` 屬性的值稱為 Hamiltonian 物件，而且必須具有 `one_electron_integrals` 和 `two_electron_integrals` 的屬性，如本節其餘部分所述。

每個問題描述物件都必須具有屬性 `coulomb_repulsion` 其值是簡單數量物件。
每個問題描述物件都必須具有屬性 `energy_offet` 其值是簡單數量物件。
> 下`coulomb_repulsion` 和 `energy_offet` 相加的值，會同時捕捉 Hamiltonian 的識別詞彙。

##### <a name="one-electron-integrals-object"></a>一個 Electron 的積分物件 #####

本節為標準化。

Hamiltonian 物件的 `one_electron_integrals` 屬性必須是一個稀疏陣列數量，其索引為兩個整數，而其值為數字。
每個詞彙都必須有 `[i, j]` 的索引，`i >= j`。

> 下這會反映 $h _ {ij} = h_ {ji} $ 的對稱，這是 Hamiltonian Hermitian 的事實結果。


###### <a name="example"></a>範例 ######

這一節有資訊。

下列 sparse 陣列數量代表 Hamiltonian $ $ H = \left （-5.0 （a ^\{\dagger\}\_{1，\uparrow}\_{1，\uparrow} + a ^\{\dagger\}\_{1，\downarrow} a\_{1，\downarrow}） + 0.17 （^\{\dagger\}\_{2，\uparrow} a\_{1，\uparrow} + a ^\{\dagger\}\_{1，\uparrow} a\_{2，\uparrow} + a ^\{\dagger\}\_{2，\downarrow}\_{1，\downarrow} + a ^\{\dagger\}\_{1，\downarrow} a\_{2，\downarrow}） \right）\\，\mathrm{Ha}。
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
> Broombridge 會使用以1為基礎的索引。


##### <a name="two-electron-integrals-object"></a>兩個 Electron 的積分物件 #####

本節為標準化。

Hamiltonian 物件的 `two_electron_integrals` 屬性必須是具有一個稱為 `index_convention`的額外屬性的稀疏陣列數量。
`two_electron_integrals` 值的每個元素都必須有四個索引。

每個 `two_electron_integrals` 屬性都必須具有 `index_convention` 屬性。
`index_convention` 屬性的值必須是 [表 1] 中所列的其中一個允許值。
如果 `index_convention` 的值為 `mulliken`，則針對 `two_electron_integrals` sparse 陣列數量的每個元素，載入 Broombridge 檔的剖析器必須具現化 Hamiltonian 詞彙，其等於兩個 electron 運算子 $h _ {i，j、k、l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $，$j $，$k $，而 $l $ 必須是值至少為1的整數，而 $h _ {i，j，k，l} $ 是稀疏陣列數量的元素 `[i, j, k, l, h(i, j, k, l)]`。

###### <a name="symmetries"></a>Symmetries ######

本節為標準化。

如果 `two_electron_integrals` 物件的 `index_convention` 屬性等於 `mulliken`，則如果有索引 `[i, j, k, l]` 的元素存在，則不能存在下列索引，除非它們等於 `[i, j, k, l]`：

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> 因為 `index_convention` 屬性是一個稀疏數量物件，所以不會在不同的元素上重複使用任何索引。
> 特別是，如果有索引 `[i, j, k, l]` 的元素存在，則沒有其他元素可以有這些索引。


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>範例 #######

這一節有資訊。

下列物件會指定 Hamiltonian

$ $ H = \frac12 \sum\_{\sigma，\rho\in\\{\uparrow，\downarrow\\}} \Biggr （1.6 a ^ {\dagger}\_{1，\sigma} ^ {\dagger}\_{1，\rho} a\_{1，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{6，\sigma} a ^ {\dagger}\_{1，\rho} a\_{3，\rho} a\_{2，\sigma}-0.1 a ^ {\dagger}\_{6，\sigma} a\_{2，\rho}\_{3，\sigma}-0.1 a ^ {\dagger}\_{1，\sigma} a ^ {\dagger}\_{6，\rho} a\_{3，\rho} a\_{2，\sigma}-0.1 a ^ {\dagger}\_{1，\sigma} a ^ {\dagger}\_{6，\rho} a\_{2，\rho} a\_{3，\sigma} $ $ $ $-0.1 a ^ {\dagger}\_{3，\sigma} a ^ {\dagger}\_{2，\rho} a\_{6，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{3，\sigma} ^ {\dagger}\_{2，\rho} a\_{1，\rho} a\_{6，\sigma}-0.1 a ^ {\dagger}\_{2，\sigma} a ^ {\dagger}\_{3，\rho} a\_{6，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{2，\sigma} a ^ {\dagger}\_{3，\rho} a\_{1，\rho} a\_{6，\sigma}\Biggr）\\，\textrm{Ha}。\_
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

### <a name="initial-state-section"></a>初始狀態區段 ###

本節為標準化。

其值為 JSON 陣列的 `initial_state_suggestion` 物件會指定指定 Hamiltonian 的相關初始量子狀態。 `initial_state_suggestion` 屬性值中的每個專案都必須是描述一個配量狀態的 JSON 物件，如本節其餘部分所述。
在本節的其餘部分，「狀態物件」一詞會參考 Broombridge 物件的 `initial_state_suggestion` 屬性值中的專案。

#### <a name="state-object"></a>狀態物件 ####

本節為標準化。

每個狀態物件都必須有一個包含字串的 `label` 屬性。 每個狀態物件都必須具有 `method` 屬性。 `method` 屬性的值必須是 [表 3] 中所列的其中一個允許值。
每個狀態物件都有一個屬性 `energy`，其值必須是簡單數量物件。

如果 `method` 屬性的值為 `sparse_multi_configurational`，則狀態物件必須具有 `superposition` 屬性，其中包含基礎狀態陣列及其未標準化的 amplitudes。

例如，初始狀態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = （a ^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） \ket{0} $ $ $ $ \ket{E} = \frac{0.1 （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） + 0.2 （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{3，\uparrow}a ^ {\dagger}\_{2，\downarrow}）} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}，$ $，其中 $ \ket{E} $ 具有能源 $0.987 \textrm{Ha} $，其以表示
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

如果 `method` 屬性的值為 `unitary_coupled_cluster`，則狀態物件必須具有 `cluster_operator` 屬性，其值為 JSON 物件。
JSON 物件必須有一個 `reference_state` 屬性，其值為「基礎」狀態。
JSON 物件可能會有一個 `one_body_amplitudes` 屬性，其值為一個主體叢集運算子及其 amplitudes 的陣列。
JSON 物件可能有一個 `two_body_amplitudes` 屬性，其值為兩個主體叢集運算子及其 amplitudes 的陣列。
包含基礎狀態陣列及其未標準化的 amplitudes。

例如，state $ $ \ket{\text{reference}} = （a ^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） \ket{0}，$ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}，$ $

$ $ T = 0.1 a ^ {\dagger}\_{3，\uparrow}a\_{2，\downarrow} + 0.2 a ^ {\dagger}\_{2，\uparrow}a\_{2，\downarrow}-0.3 a ^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{3，\downarrow}a\_{3，\uparrow}a\_{2，\downarrow} $ $ 是以
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

#### <a name="basis-set-object"></a>基本設定物件 ####

本節為標準化。

每個問題描述物件都有一個 `basis_set` 屬性。
如果存在的話，`basis_set` 屬性的值必須是具有兩個屬性的物件，`type` 和 `name`。

由 `basis_set` 屬性的值所識別的基礎函數必須是實際值。

> [!NOTE]
> 假設在此規格的未來版本中，所有基礎函數都是實際值。

## <a name="tables-and-lists"></a>資料表和清單 ##

### <a name="table-1-allowed-physical-units"></a>表 1. 允許的實體單位 ###

本節為標準化。

指定單位的任何字串都必須是下列其中一項：

- `hartree`
- `ev`

剖析器和產生者必須將下列簡單數量物件視為對應項：

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>表 2. 允許的索引慣例 ###

本節為標準化。

指定索引慣例的任何字串都必須是下列其中一項：

- `mulliken`

這一節有資訊。

此規格的未來版本可能會引進額外的索引慣例。

#### <a name="interpretation-of-index-conventions"></a>索引慣例的解讀 ####

這一節有資訊。

### <a name="table-3-allowed-state-methods"></a>[表 3] 允許的狀態方法 ###

本節為標準化。

任何指定 state 方法的字串都必須是下列其中一項：

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

這一節有資訊。

此規格的未來版本可能會引進其他狀態方法。
