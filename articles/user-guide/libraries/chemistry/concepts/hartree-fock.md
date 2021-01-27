---
title: Hartree-Fock 理論
description: 瞭解 Hf – Fock 理論，這是一個簡單的方式，可供您用來建立量子系統的初始狀態。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 48d6bc4face90046271dd8705188a92daafad98a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854100"
---
# <a name="hartreefock-theory"></a>Hf – Fock 理論

量子化學模擬中最重要的數量或許是地面狀態，也就是 Hamiltonian 矩陣的最小能源 eigenvector。
這是因為大部分分子的房間溫度數量（例如，反應率）都是由配量狀態之間的自由能源差異所組成，此狀態會描述反應路徑中步驟的開頭和結尾，而房間溫度則通常是地面狀態。
雖然地面狀態通常太難學習 (即使是量子電腦) ，因為它是以指數方式進行大量設定的散發。
您可以瞭解基礎狀態能源等數量。
例如，如果 $ \ket{\psi} $ 是任何純量子狀態，則 \begin{equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{equation} 會提供系統在該狀態中的平均能源。
而地面狀態則是提供最小的這類值的狀態。 如此一來，選擇盡可能接近真正地面狀態的狀態非常重要，因為它可以直接 (在 variational eigensolvers) 或透過階段估計來評估能源。

Hf – Fock 理論提供簡單的方式來建立量子系統的初始狀態。 它會針對量子系統的接地狀態產生單一 Slater 行列式近似值。 因此，它會在 Fock 空間內找到旋轉，以將地面狀態的能源降至最低。 尤其是針對 $N $ 電子的系統，方法會執行旋轉 \begin{equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {n-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {n-1} \widetilde{a} ^ \ dagger_j \ket {0} ，具有反 Hermitian 的 \end{equation} (亦即 $u =-u ^ \dagger $) 矩陣 $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $。 請注意，矩陣 $u $ 代表 orbital 旋轉，而 $ \widetilde{a} ^ \ dagger_j $ 和 $ \widetilde{a} _j $ 代表電子佔用 Hf – Fock 分子微調 orbitals 的建立和 annihilation 運算子。


接著會優化矩陣 $u $，以將預期的能源 $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $。 雖然這類優化問題可能很常見，但在實務上，Hf – Fock 演算法通常會快速地會合至優化問題的接近理想解決方案，尤其是均衡幾何中的封閉 shell 分子。 我們可以將這些狀態指定為物件的實例 `FermionWavefunction` 。 例如，狀態 $a ^ \ dagger_ ^ \ {1} dagger_ {2} ^ \ dagger_ {6} \ket {0} $ 會在化學程式庫中具現化，如下所示。
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
您也可以使用索引來編制 wave 函數的索引 `SpinOrbital` ，然後將這些索引轉換成整數，如下所示。
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Hf – Fock 理論上最顯著的功能是，它會產生電子之間沒有纏結的量子狀態。
這表示它通常會提供分子系統屬性的適當定性描述。 

也可以從重建 Hartree-Fock 狀態 `FermionHamiltonian`  ，如下所示。
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

不過，若要取得精確的結果，尤其是針對強式關聯的系統，則會強制執行超過 Hf – Fock 理論的量子狀態。
