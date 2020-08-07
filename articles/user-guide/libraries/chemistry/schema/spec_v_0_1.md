---
title: 'Broombridge 架構規格 (ver 0.1) '
description: 詳細說明 Microsoft 量子化學程式庫之 Broombridge 量子化學架構 v 0.1 的規格。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: abbc63b8801c774e6ba06cff99b7382d64424b2c
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869132"
---
# <a name="broombridge-specification-v01"></a>Broombridge 規格 v 0。1 #

本檔中的關鍵字「必須」、「不得」、「必要」、「應」、「不得」、「應該」、「不應」、「建議」、「可能」和「選擇性」，如[RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。

具有標題「附注」、「資訊」或「警告」的任何提要欄位都有資訊。

## <a name="introduction"></a>簡介 ##

這一節有資訊。

Broombridge 檔的目的是要在量子化學中傳達模擬問題的實例，以使用量子模擬和程式設計工具鏈進行處理。

## <a name="serialization"></a>序列化 ##

本節為標準化。

Broombridge 檔必須序列化為代表 JSON 物件的[YAML 1.2 檔](http://yaml.org/spec/)，如[RFC 4627](https://tools.ietf.org/html/rfc4627)區段2.2 中所述。
序列化至 YAML 的物件必須具有 `"$schema"` 其值為的屬性 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` ，而且必須根據 JSON 架構 draft-06 規格 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 來有效。

在此規格的其餘部分中，「Broombridge 物件」將會參考從 Broombridge YAML 檔案還原序列化的 JSON 物件。

除非另有明確注明，否則物件除了在此檔中明確指定的屬性以外，不能有其他內容。

## <a name="additional-definitions"></a>其他定義 ##

本節為標準化。

### <a name="quantity-objects"></a>數量物件 ###

本節為標準化。

_Quantity 物件_是 JSON 物件，而且必須具有屬性， `units` 其值是 [表 1] 中所列的其中一個允許值。

Quantity 物件是一個_簡單的 quantity 物件_，如果它 `value` 除了屬性之外還有單一屬性 `units` 。
屬性的值 `value` 必須是數位。

Quantity 物件是一個_限定數量物件_，如果它 `lower` `upper` 除了屬性之外還有屬性 `units` 。
和屬性的值 `lower` `upper` 必須是數位。
限定數量物件的屬性（property）的 `value` 值可能是數位。

Quantity 物件是一個_稀疏陣列數量物件_，如果它 `format` `values` 除了屬性之外還有屬性和屬性 `units` 。
的值 `format` 必須是字串 `sparse` 。
屬性的值 `values` 必須是陣列。
的每個元素都 `values` 必須是代表稀疏陣列數量之索引和值的陣列。

Sparse 陣列數量物件的每個元素的索引在整個 sparse 陣列數量物件中必須是唯一的。
如果有值為的索引，剖析器就 `0` 必須將 sparse 陣列數量物件視為完全不存在該索引的稀疏陣列數量物件。


Quantity 物件必須是

- 簡單數量物件，
- 限定數量物件，或
- 稀疏陣列數量物件。


### <a name="examples"></a>範例 ###

這一節有資訊。

代表 $ 1.9844146837 \Mathrm{Ha} $ 的簡單數量 \, ：

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

代表間隔 $ [-7，-6] \Mathrm{Ha} $ 之統一散發的限定數量 \, ：

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

以下是一個專案 `[1, 2]` 等於 `hello` 且元素等於的稀疏陣列數量 `[3, 4]` `world` ：

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

Broombridge 物件必須具有屬性 `format` ，其值為具有一個名為之屬性的 JSON 物件 `version` 。
`version`屬性必須具有值 `"0.1"` 。

### <a name="example"></a>範例 ###

這一節有資訊。

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>整陣列區段 ##

本節為標準化。

Broombridge 物件必須有一個屬性 `integral_sets` ，其值為 JSON 陣列。
屬性值中的每個專案都 `integral_sets` 必須是描述一組整型的 JSON 物件，如本節其餘部分所述。
在本節的其餘部分，「整數集合物件」一詞會參考 Broombridge 物件的屬性值中的專案 `integral_sets` 。

每個整數集物件都必須有一個屬性 `metadata` ，其值為 JSON 物件。
的值 `metadata` 可以是空的 JSON 物件 (也就是、 `{}`) ，或可能包含實作項所定義的其他屬性。

### <a name="hamiltonian-section"></a>Hamiltonian 區段 ###

#### <a name="overview"></a>概觀 ####

這一節有資訊。

`hamiltonian`每個整數集物件的屬性描述特定量子化學問題的 Hamiltonian，其方式是將其一對一和二主體詞彙列示為實數陣列。
每個整數集合物件所描述的 Hamiltonian 運算子採用的格式

$ $ H = \sum \_ \{ i，j \} \sum \_ {\sigma\in \\ {\uparrow，\downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i，\sigma} a \_ {j，\sigma} + \frac {1} {2} \sum \_ \{ i，j，k，l \} \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i，\sigma} a ^ \dagger \_ {k，\rho} a \_ {l，\rho} a \_ {j，\sigma}，$ $

這裡 $h _ {ijkl} = (ij | kl) $ in Mulliken 慣例。

為了清楚起見，electron 一詞是

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ * \_ i (x) \left ( \frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ A} {| x-x \_ A |} \right) \psi \_ j (x) ，$ $

而這兩個 electron 的詞彙是

$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2) 。
$$

如我們在屬性的每個專案的[ `basis_set` 屬性](#basis-set-object)說明中所述 `integral_sets` ，我們會進一步明確假設使用的基礎函數是實際值。
這可讓我們在詞彙之間使用下列 symmetries 來壓縮 Hamiltonian 的標記法。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>目錄 ####

本節為標準化。

每個整陣列都必須有一個屬性 `hamiltonian` ，其值為 JSON 物件。
屬性的值 `hamiltonian` 稱為 Hamiltonian 物件，而且必須具有屬性， `one_electron_integrals` 如本節其餘部分 `two_electron_integrals` 所述。
Hamiltonian 物件也可能有屬性 `particle_hole_representation` 。
如果存在，則的值 `particle_hole_representation` 必須遵循本節其餘部分所述的格式。

##### <a name="one-electron-integrals-object"></a>一個 Electron 的積分物件 #####

本節為標準化。

`one_electron_integrals`Hamiltonian 物件的屬性必須是一個稀疏陣列數量，其索引為兩個整數，而其值為數字。
每個詞彙都必須有索引 `[i, j]` ，其中 `i >= j` 。

> 下這會反映 $h _ {ij} = h_ {ji} $ 的對稱，這是 Hamiltonian Hermitian 的事實結果。


###### <a name="example"></a>範例 ######

這一節有資訊。

下列 sparse 陣列數量代表 Hamiltonian $ $ H = \left (-5.0 (^ \{ \dagger \} \_ {1，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {1，\downarrow} ) + 0.17 (^ \{ \dagger \} \_ {2，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {2，\uparrow} + a ^ \{ \dagger \} \_ {2，\downarrow} a { \_ 1，\downarrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {2，\downarrow} ) \right) \\ ，\mathrm{Ha}。
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

`two_electron_integrals`Hamiltonian 物件的屬性必須是具有另一個稱為的額外屬性的稀疏陣列數量 `index_convention` 。
值的每個元素都 `two_electron_integrals` 必須有四個索引。

每個 `two_electron_integrals` 屬性都必須有 `index_convention` 屬性。
屬性的值 `index_convention` 必須是 [表 1] 中所列的其中一個允許值。
如果的值 `index_convention` 是 `mulliken` ，則針對每個 `two_electron_integrals` sparse 陣列數量的元素，載入 Broombridge 檔的剖析器必須具現化 Hamiltonian 詞彙，其等於兩個 electron 運算子 $h _ {i，j，k，l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $，$j $，$k $，而 $l $ 必須是包含範圍從1到整數集合物件之屬性所指定的 electrons 數目 `n_electrons` ，其中 $h _ {i，j，k，l} $ 是 `[i, j, k, l, h(i, j, k, l)]` 稀疏陣列數量的元素。

###### <a name="symmetries"></a>Symmetries ######

本節為標準化。

如果 `index_convention` 物件的屬性 `two_electron_integrals` 等於 `mulliken` ，則如果有具有索引的元素 `[i, j, k, l]` ，則除非它們相等，否則不能出現下列索引 `[i, j, k, l]` ：

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> 因為 `index_convention` 屬性是一個稀疏數量物件，所以不會在不同的元素上重複使用任何索引。
> 特別是，如果有具有索引的元素 `[i, j, k, l]` ，則沒有其他元素可以有這些索引。


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>範例 #######

這一節有資訊。

下列物件會指定 Hamiltonian

$ $ H = \frac12 \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} \Biggr ( 1.6 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {1，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} { \_ 6，\sigma} a ^ {\dagger} { \_ 1，\rho} a { \_ 2，\rho} a {3，\sigma}-a ^ {\dagger} {1，\sigma} a \_ \_ ^ {\dagger} { \_ 6，0.1 \rho} \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {2，\rho} a \_ {3，\sigma} $ $ $ $-0.1 a ^ {\dagger} { \_ 3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {1，\rho} a \_ {6，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {1，\Rho} a \_ {6，\sigma}\Biggr) \\ ，\textrm{Ha}。
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

##### <a name="particlehole-representation-object"></a>物件–洞表示物件 #####

本節為標準化。

[物件類型] – [洞標記法] 物件會指定所儲存的一併定義的是「物件」，而建立和 annihilation 運算子會從所使用的參考狀態（例如 Hartree – Fock 狀態）描述 excitations。
物件是選擇性的。
如果未指定物件，則會將 Hamiltonian 視為不會在物件標記法中提供。
如果存在，的值 `particle_hole_representation` 必須是一個稀疏陣列數量物件，其索引為四個整數，而其值為數字和字串。
每個專案值的字串部分只能包含個字元 `'+'` ，並 `'-'` 指定詞彙中的指定因素是否為物件中的建立或 annihilation 運算子–洞標記法。  例如 `"-+++"` ，coresponds 至在網站上建立的洞 $i $ 和要在網站上建立的微粒 $j，k $ 和 $l $。

> [!NOTE]
> 因為的值 `particle_hole_representation` 是一個稀疏陣列數量物件，所以 `unit` `format` 必須指定和屬性。
> [表 1] 列出可接受的單位。
> `format`屬性是必要的，而且會指出是否將 Hamiltonian 係數指定為密集或稀疏陣列。
> 在目前版本中，只支援稀疏陣列，並將所有未指定的元素轉譯為 $0 $，但未來的版本可能會加入屬性的其他值支援 `format` 。

### <a name="initial-state-section"></a>初始狀態區段 ###

Initial_state_suggestion 物件會指定所指定 Hamiltonian 的相關初始配量狀態。 此物件必須是 JSON 物件的陣列 `state` 。

#### <a name="state-object"></a>狀態物件 ####

每個狀態都代表已佔用的 orbitals 的重迭。 每個狀態物件都必須有 `label` 包含字串的屬性。 每個狀態物件都必須有一個 `superposition` 屬性，其中包含基礎狀態陣列及其未標準化的 amplitudes。

例如，初始狀態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) + 0.2 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) } {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ 的表示方式
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

#### <a name="basis-set-object"></a>基本設定物件 ####

本節為標準化。

每個整數集物件都可能有 `basis_set` 屬性。
如果存在，屬性的值 `basis_set` 必須是具有兩個屬性的物件： `type` 和 `name` 。

屬性值所識別的基礎函數 `basis_set` 必須是實值。

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
