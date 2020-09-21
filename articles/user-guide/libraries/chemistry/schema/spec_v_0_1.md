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
# <a name="broombridge-specification-v01"></a>Broombridge 規格 v 0。1 #

本檔中的關鍵字「必須」、「不得」、「必要」、「應該」、「不應」、「應該」、「不應」、「建議」、「可能」和「選擇性」，如 [RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。

任何標題為「附注」、「資訊」或「警告」的提要欄位都有提供資訊。

## <a name="introduction"></a>簡介 ##

本節說明資訊。

Broombridge 檔的目的是要傳達量子化學中模擬問題的實例，以使用量子模擬和程式設計工具鏈進行處理。

## <a name="serialization"></a>序列化 ##

本節為標準化。

Broombridge 檔必須序列化為 [YAML 1.2 檔](http://yaml.org/spec/) ，以表示 [RFC 4627](https://tools.ietf.org/html/rfc4627) 區段2.2 中所述的 JSON 物件。
序列化為 YAML 的物件必須具有 `"$schema"` 其值為的屬性 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` ，而且必須根據 JSON 架構 draft-06 規格 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 來有效。

針對此規格的其餘部分，「Broombridge 物件」會參考從 Broombridge YAML 檔案還原序列化的 JSON 物件。

除非另有明確注明，否則物件不能有在本檔中明確指定的屬性以外的其他屬性。

## <a name="additional-definitions"></a>其他定義 ##

本節為標準化。

### <a name="quantity-objects"></a>Quantity 物件 ###

本節為標準化。

_Quantity 物件_是一個 JSON 物件，且 `units` 其值必須是 [表 1] 所列的其中一個允許值的屬性。

如果 quantity 物件除了屬性之外還具有單一屬性，則它是 _簡單數量的物件_ `value` `units` 。
屬性的值 `value` 必須是數位。

如果 quantity 物件具有屬性和屬性，則它是一個「 _限定數量」物件_ `lower` `upper` `units` 。
和屬性的值 `lower` `upper` 必須是數位。
「限定數量」物件的屬性（property）的 `value` 值可以是數位。

如果 quantity 物件具有屬性和屬性（property）及其屬性（property），則此物件為「 _稀疏陣列數量」物件_ `format` `values` `units` 。
的值 `format` 必須是字串 `sparse` 。
屬性的值 `values` 必須是陣列。
的每個元素都 `values` 必須是代表稀疏陣列數量之索引和值的陣列。

「稀疏陣列數量」物件的每個專案的索引，在整個「稀疏陣列數量」物件中必須是唯一的。
如果具有值的索引存在，剖析器就必須將「 `0` 稀疏陣列數量」物件視為完全不存在該索引的「稀疏陣列數量」物件。


Quantity 物件必須是

- 簡單數量物件，
- 限定數量物件，或
- 稀疏陣列數量物件。


### <a name="examples"></a>範例 ###

本節說明資訊。

代表 $ 1.9844146837 \Mathrm{Ha} $ 的簡單數量 \, ：

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

代表超過間隔 $ [-7，-6] \Mathrm{Ha} $ 之統一分佈的限定數量 \, ：

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

以下是具有等於和元素等於的稀疏陣列數量 `[1, 2]` `hello` `[3, 4]` `world` ：

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>格式區段 ##

本節為標準化。

Broombridge 物件必須具有屬性 `format` ，其值為 JSON 物件，且其中一個屬性稱為 `version` 。
`version`屬性必須具有值 `"0.1"` 。

### <a name="example"></a>範例 ###

本節說明資訊。

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>整數集區段 ##

本節為標準化。

Broombridge 物件必須有一個屬性 `integral_sets` ，其值為 JSON 陣列。
屬性值中的每個專案都 `integral_sets` 必須是描述一組積分的 JSON 物件，如本節其餘部分所述。
在本節的其餘部分，「整陣列物件」一詞會參考 Broombridge 物件的屬性值中的專案 `integral_sets` 。

每個整陣列物件都必須有一個屬性 `metadata` ，其值為 JSON 物件。
的值 `metadata` 可能是空的 JSON 物件 (也就是 `{}`) ，或可能包含由實作項所定義的其他屬性。

### <a name="hamiltonian-section"></a>Hamiltonian 區段 ###

#### <a name="overview"></a>概觀 ####

本節說明資訊。

`hamiltonian`每個整陣列物件的屬性，會將它的一或兩個內文詞彙列為稀疏陣列的實數，以描述特定量子化學問題的 Hamiltonian。
每個整數集物件所描述的 Hamiltonian 運算子採用格式

$ $ H = \sum \_ \{ i，j \} \sum \_ {\sigma\in \\ {\uparrow，\downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i，\sigma} a \_ {j，\sigma} + \frac {1} {2} \sum \_ \{ i，j，k，l \} \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i，\sigma} a ^ \dagger \_ {k，\rho} a \_ {l，\rho} a \_ {j，\sigma}，$ $

這裡 $h _ {ijkl} = (ij | kl) $ in Mulliken 慣例。

為了清楚起見，electron 一詞是

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ * \_ i (x) \left ( \frac {1} {2} \nabla ^ 2 + \sum \_ {a} \frac{Z \_ A} {| x-x \_ a |} \right) \psi \_ j (x) ，$ $

這兩個 electron 詞彙是

$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2) 。
$$

如同屬性之每個元素的[ `basis_set` 屬性](#basis-set-object)描述中所述 `integral_sets` ，我們會進一步明確假設使用的基礎函數是真正的值。
這可讓我們在詞彙之間使用下列 symmetries，以壓縮 Hamiltonian 的表示。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>內容 ####

本節為標準化。

每個整陣列都必須有一個屬性 `hamiltonian` ，其值為 JSON 物件。
屬性的值 `hamiltonian` 稱為 Hamiltonian 物件，而且必須具有屬性 `one_electron_integrals` ， `two_electron_integrals` 如本節的其餘部分所述。
Hamiltonian 物件也可以有屬性 `particle_hole_representation` 。
如果有的話，的值 `particle_hole_representation` 必須遵循本節其餘部分所述的格式。

##### <a name="one-electron-integrals-object"></a>一個 Electron 的積分物件 #####

本節為標準化。

`one_electron_integrals`Hamiltonian 物件的屬性必須是稀疏陣列數量，其索引為兩個整數且其值為數字。
每個詞彙都必須有 `[i, j]` 的索引 `i >= j` 。

> 記這會反映 $h _ {ij} = h_ {ji} $ 的對稱，這是 Hamiltonian Hermitian 的事實結果。


###### <a name="example"></a>範例 ######

本節說明資訊。

下列稀疏陣列數量代表 Hamiltonian $ $ H = \left (-5.0 (^ \{ \dagger \} \_ {1，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {1，\downarrow} ) + 0.17 (^ \{ \dagger \} \_ {2，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {2，\uparrow} + a ^ \{ \dagger \} \_ {2，\downarrow} a { \_ 1，\downarrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {2，\downarrow} ) \right) \\ ，\mathrm{Ha}。
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
> Broombridge 使用以1為基礎的索引。


##### <a name="two-electron-integrals-object"></a>雙 Electron 的積分物件 #####

本節為標準化。

`two_electron_integrals`Hamiltonian 物件的屬性必須是稀疏陣列數量，並有一個稱為的額外屬性 `index_convention` 。
值的每個元素都 `two_electron_integrals` 必須有四個索引。

每個 `two_electron_integrals` 屬性都必須有 `index_convention` 屬性。
屬性的值 `index_convention` 必須是 [表 1] 所列的其中一個允許值。
如果的值 `index_convention` 為 `mulliken` ，則針對每個 `two_electron_integrals` 稀疏陣列數量的元素，載入 Broombridge 檔的剖析器必須具現化等於雙 Electron 運算子的 Hamiltonian 詞彙 $h _ {i，j，k、l} ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $、$j $、$k $ 和 $l $ 必須是包含範圍中的整數，介於1到整陣列物件的屬性所指定的電子數目之間 `n_electrons` ，其中 $h _ {i，j，k，l} $ 是 `[i, j, k, l, h(i, j, k, l)]` 稀疏陣列數量的元素。

###### <a name="symmetries"></a>對稱 ######

本節為標準化。

如果 `index_convention` 物件的屬性 `two_electron_integrals` 等於 `mulliken` ，則如果有具有索引的元素 `[i, j, k, l]` ，則必須有下列索引，除非它們等於 `[i, j, k, l]` ：

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> 因為 `index_convention` 屬性是「稀疏數量」物件，所以不會在不同的元素上重複任何索引。
> 尤其是，如果有具有索引的元素 `[i, j, k, l]` ，則其他專案可能會有這些索引。


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>範例 #######

本節說明資訊。

下列物件會指定 Hamiltonian

$ $ H = \frac12 \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} \Biggr ( 1.6 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {1，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {2，\rho} a \_ {3，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {2，\rho} a \_ {3，\sigma} $ $ $-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {1，\rho} a \_ {6，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {1，\Rho} a \_ {6，\sigma}\Biggr) \\ ，\textrm{Ha}。
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

##### <a name="particlehole-representation-object"></a>物件-洞標記法物件 #####

本節為標準化。

「物件」-「洞表示」物件會指定所儲存的積分是針對「粒子」標記法所定義，其中建立和 annihilation 運算子會從所使用的參考狀態中描述 excitations，例如 Hf – Fock 狀態。
物件是選擇性的。
如果未指定物件，則會將 Hamiltonian 解釋為在粒子標記法中未提供。
如果存在，的值 `particle_hole_representation` 必須是「稀疏陣列數量」物件，其索引為四個整數，而且其值為數字和字串。
每個元素之值的字串部分必須只包含字元 `'+'` ，並 `'-'` 指定詞彙中的指定因數是否為物件-洞標記法中的建立或 annihilation 運算子。  例如 `"-+++"` ，coresponds 至在網站上建立的洞 $i $ 和在網站上建立的粒子 $j、k $ 和 $l $。

> [!NOTE]
> 因為的值 `particle_hole_representation` 是稀疏陣列數量物件，所以 `unit` `format` 必須指定和屬性。
> [表 1] 列出可接受的單位。
> `format`需要屬性，並指出 Hamiltonian 係數是否指定為密集或稀疏陣列。
> 在目前的版本中，只支援稀疏陣列，並將所有未指定的元素轉譯為 $0 $，但未來的版本可能會新增其他屬性值的支援 `format` 。

### <a name="initial-state-section"></a>初始狀態區段 ###

Initial_state_suggestion 物件指定指定 Hamiltonian 的相關初始量子狀態。 此物件必須是 JSON 物件的陣列 `state` 。

#### <a name="state-object"></a>狀態物件 ####

每個狀態都代表已佔用 orbitals 的迭加。 每個狀態物件都必須有一個 `label` 包含字串的屬性。 每個狀態物件都必須有一個 `superposition` 包含基礎狀態陣列及其未標準化 amplitudes 的屬性。

例如，初始狀態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) + 0.2 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) } {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ 由
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

#### <a name="basis-set-object"></a>基礎 Set 物件 ####

本節為標準化。

每個整陣列物件都可以有 `basis_set` 屬性。
如果有的話，屬性的值 `basis_set` 必須是具有兩個屬性的物件： `type` 和 `name` 。

由屬性值所識別的基礎函數 `basis_set` 必須是實值。

> [!NOTE]
> 在此規格的未來版本中，假設所有基礎函數都是真正的值。

## <a name="tables-and-lists"></a>資料表和清單 ##

### <a name="table-1-allowed-physical-units"></a>表 1. 允許的實體單位 ###

本節為標準化。

指定單位的任何字串都必須是下列其中一項：

- `hartree`
- `ev`

剖析器和生產者必須將下列簡單數量物件視為對等：

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>表 2. 允許的索引慣例 ###

本節為標準化。

指定索引慣例的任何字串都必須是下列其中一項：

- `mulliken`

本節說明資訊。

此規格的未來版本可能會引進額外的索引慣例。

#### <a name="interpretation-of-index-conventions"></a>索引慣例的解讀 ####

本節說明資訊。
