---
title: 從檔案載入 Hamiltonian |Microsoft Docs
description: 從檔案檔載入 Hamiltonian
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 9902e95b09d38323b4b91c29ab897a4f0124b6cd
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184180"
---
## <a name="loading-a-hamiltonian-from-file"></a>從檔案載入 Hamiltonian
先前，我們藉由在其中新增個別詞彙來建立 Hamiltonians。 雖然這適用于小型範例，但大規模的配量化學需要 Hamiltonians 數百萬或數十億個詞彙。 由化學套件（例如 NWChem）所產生的這類 Hamiltonians 太大，無法手動匯入。 在此範例中，我們會說明如何從[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)所代表的分子自動產生 `FermionHamiltonian` 實例。 如需參考，可以檢查提供的 `LithiumHydrideGUI` 範例或 `RunSimulation` 範例。 從[LIQUi | >](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)所使用的格式匯入，也可以使用有限的支援。

讓我們來看看 Nitrogen 分子的範例，這會在範例存放庫的 `IntegralData/YAML` 資料夾中提供。 載入 `Broombridge` 配置的方法很簡單。

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Broombridge 架構也包含要準備之初始狀態的建議。 檢查檔案可能會顯示這些狀態的標籤，例如 `"|G⟩"` 或 `"|E1⟩"`。 為了準備這些初始狀態，會取得與[上一節](xref:microsoft.quantum.chemistry.examples.energyestimate)類似的 Q # 量子演算法所使用的 `qSharpData`，但會有一個額外的參數選取所需的初始狀態。 例如，
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

上述所有步驟都可以使用提供的便利方法進行縮寫，如下所示。
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

我們也可以使用非常類似的語法，從 LIQUi | > 格式載入 Hamiltonian。 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

藉由在 Broombridge 的任何實例或任何中繼步驟中遵循此程式，可能會在指定的電子結構問題上執行配量階段評估之類的量子演算法。