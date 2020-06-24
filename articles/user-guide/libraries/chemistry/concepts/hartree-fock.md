---
title: Hartree-Fock 理論
description: 深入瞭解 Hartree – Fock 理論，這是一種簡單的方式，可為量子系統建立初始狀態。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274663"
---
# <a name="hartreefock-theory"></a>Hartree – Fock 理論

可能是「量子化學模擬」中最重要的數量是「接地」狀態，也就是 Hamiltonian 矩陣的最小能源 eigenvector。
這是因為對於大部分分子驅使分子的房間溫度數量（例如，反應速率）是由配量狀態間的免費能源差異所造成的，這種情況會描述反應路徑中步驟的開始和結束，而室內溫度（例如中繼狀態）通常是基礎狀態。
雖然地面狀態通常難以學習（即使是使用量子電腦），因為它是以指數的大量設定進行散發。
可以學到的數量，例如地面省電。
例如，如果 $ \ket{\psi} $ 是任何純粹的量子狀態，則 \begin{equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{equation} 會提供系統在該狀態下的平均能源。
而地面狀態則是提供最小這類值的狀態。 因此，選擇盡可能接近實際狀態的狀態，非常重要的是直接評估能源（如同在 variational eigensolvers 中完成），或透過階段估計。

Hartree – Fock 理論提供了一種簡單的方式來建造量子系統的初始狀態。 它會針對量子系統的基礎狀態產生單一 Slater 行列式近似值。 為此，它會在 Fock 空間內尋找旋轉，以將地面狀態的能源降到最低。 特別是，針對 $N $ electrons 的系統，此方法會執行輪替 \begin{equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {n-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} ，具有反 Hermitian 的 \end{equation} （亦即，$u =-u ^ \dagger $）矩陣 $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $。 請注意，矩陣 $u $ 代表 orbital 旋轉，而 $ \widetilde{a} ^ \ dagger_j $ 和 $ \widetilde{a} _j $ 代表 electrons 佔用 Hartree – Fock 分子微調-orbitals 的建立和 annihilation 運算子。


然後，$u $ 的矩陣經過優化，可將預期的能源 $ \bra {0} \ prod_ {j = 0} ^ {N-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $。 雖然這類優化問題可能會很困難，但實際上 Hartree – Fock 演算法會快速地融合到優化問題的接近最佳解決方案，特別是均衡幾何中的封閉式 shell 分子驅使分子。 我們可以將這些狀態指定為物件的實例 `FermionWavefunction` 。 例如，狀態 $a ^ \ dagger_ ^ \ {1} dagger_ ^ {2} \ dagger_ {6} \ket {0} $ 會在化學程式庫中具現化，如下所示。
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
您也可以使用索引來為 wave 函數編制索引 `SpinOrbital` ，然後將這些索引轉換成整數，如下所示。
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Hartree 的最顯著功能– Fock 的理論是，它會產生 electrons 之間沒有會任何牽連的量子狀態。
這表示它通常會提供分子系統屬性的適當定性描述。 

Hartree-Fock 狀態也可以從重建， `FermionHamiltonian` 如下所示。
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

不過，若要取得精確的結果，特別是針對強式相互關聯的系統，則會有超越 Hartree – Fock 理論的量子狀態。
