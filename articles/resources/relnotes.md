---
title: Quantum 開發套件版本資訊
description: 深入了解 Microsoft Quantum Development Kit 預覽版的最新更新。
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5036b4d401bb775a7fee2252ca26e7725bc19004
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834137"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Microsoft Quantum Development Kit 版本資訊

本文包含各個 Quantum Development Kit 版本的相關資訊。

如需安裝指示，請參閱[安裝指南](xref:microsoft.quantum.install)。

如需更新指示，請參閱[更新指南](xref:microsoft.quantum.update)。

## <a name="version-01220082513"></a>版本0.12.20082513

*發行日期：2020年8月25日*

此版本包含下列項目：

- 新的 [Microsoft 量子命名空間](xref:microsoft.quantum.random)，提供更方便的方式，從程式內取樣隨機值 Q# 。  ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311)， [qsharp-runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328)) 
- 改進了[具有新作業的 `DumpOperation` ](xref:microsoft.quantum.diagnostics.dumpoperation) [Microsoft 量子. 診斷命名空間](xref:microsoft.quantum.diagnostics)，以及限制量子位配置和 oracle 呼叫的新作業。  ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302)) 
- Python 中的新[ `%project` 魔術命令](xref:microsoft.quantum.iqsharp.magic-ref.project) Q# 和 Python 中的[ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) ，可支援對 Q# 目前工作區資料夾以外專案的參考。 如需這項功能目前的限制，請參閱 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 。 
- 支援自動載入 `.csproj` /Python 主機的檔案 Q# ，可讓您在初始化時載入外部專案或封裝參考。 如需詳細資訊，請參閱使用[ Q# Python 和 Jupyter 筆記本](xref:microsoft.quantum.guide.host-programs)的指南。
- 新增了 ErrorCorrection 的症狀範例。
- 已將可調式的結合新增至 SimpleIsing。
- 已更新 HiddenShift 範例。
- 已新增使用格羅弗的演算法來解決 Sudoku 的範例 (外部投稿) 
- 一般錯誤修正。

請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。  

## <a name="version-01220072031"></a>版本0.12.20072031

*發行日期：2020年7月21日*

此版本包含下列項目：

- 在筆記本中開啟的命名空間 Q# 現在適用于未來所有的資料格計算。 例如，您可以在筆記本頂端的資料格中開啟一次命名空間，而不需要在每個程式碼資料格中開啟相關的命名空間。 新的 `%lsopen` 魔術命令會顯示目前開啟的命名空間清單。

請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。  

## <a name="version-01220070124"></a>版本0.12.20070124

*發行日期：2020年7月2日*

此版本包含下列項目：

- `qdk-chem`用於轉換舊版電子結構問題序列化格式的新工具 (例如： FCIDUMP) 至[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)
- 命名空間中的新函 [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) 式和作業時使用轉換和分解型合成演算法來套用傳統 oracle。
- 我 Q# 現在允許 `%simulate` 、 `%estimate` 和其他魔術命令的引數。 如需詳細資訊，請參閱[ `%simulate` 魔術命令參考](xref:microsoft.quantum.iqsharp.magic-ref.simulate)。
- I 中的新階段顯示選項 Q# 。如需詳細資訊，請參閱[ `%config` 魔術命令參考](xref:microsoft.quantum.iqsharp.magic-ref.config)。
- 我 Q# 和 `qsharp` python 套件現在透過 conda 套件提供 ([qsharp](https://anaconda.org/quantum-engineering/qsharp) 和 [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) ，以簡化 Q# conda 環境中 Jupyter 和 Python 功能的本機安裝。 如需詳細資訊，請參閱[ Q# Jupyter 筆記本](xref:microsoft.quantum.install.jupyter)和[ Q# Python](xref:microsoft.quantum.install.python)安裝指南。
- 使用模擬器時，量子位在發行時不再需要處於 | 0 ⟩狀態，但如果在釋放前立即測量，則可以自動重設。
- 更新可讓使用者更輕鬆地取用 Q# 具有不同 QDK 版本的程式庫套件，但只需要符合主要 & 次要版本號碼，而不是完全相同的版本
- 已移除被取代的 `Microsoft.Quantum.Primitive.*` 命名空間
- 移動的作業：
  - `Microsoft.Quantum.Intrinsic.Assert` 現在為 `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` 現在為 `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- 錯誤修正 

請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。  

## <a name="version-0112006403"></a>版本 0.11.2006.403

*發行日期：2020 年 6 月 4 日*

此版本修正了影響專案編譯的 bug Q# 。

## <a name="version-0112006207"></a>版本 0.11.2006.207

*發行日期：2020 年 6 月 3 日*

此版本包含下列項目：

- Q#當進入點出現時，筆記本和 Python 主機程式將不再失敗 Q#
- 更新[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)以使用存取修飾詞
- 編譯器現在允許在內建重寫步驟之間進行重寫步驟的外掛程式
- 已遵循我們的 [API 原則](xref:microsoft.quantum.contributing.api-design)中所述的排程，移除數個已遭取代的函式和作業。 Q# 在版本0.11.2004.2825 中建立沒有警告的程式和程式庫將繼續以未修改的方式運作。

請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。  

> [!NOTE]
> 此版本包含影響專案編譯的錯誤（bug） Q# 。 我們建議您升級至較新的版本。

## <a name="version-01120042825"></a>0\.11.2004.2825 版

*發行日期：2020 年 4 月 30 日*

此版本包含下列項目：

- 新的 Q# 應用程式支援，不再需要 c # 或 Python 主機檔案。 如需開始使用應用程式的詳細資訊 Q# ，請參閱 [這裡](xref:microsoft.quantum.install.standalone)。
- 已更新的量子隨機數字產生器快速入門，不再需要 C# 或 Python 主機檔案。 請參閱更新的[快速入門](xref:microsoft.quantum.quickstarts.qrng)
- Docker 映射的效能改進 Q#

> [!NOTE]
> Q#[`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint)目前無法從 Python 或 .net 主機程式呼叫使用新屬性的應用程式。
> 如需詳細資訊，請參閱 [Python](xref:microsoft.quantum.install.python) 和 [.NET 互通性](xref:microsoft.quantum.install.cs) 指南。

## <a name="version-01120033107"></a>0\.11.2003.3107 版

*發行日期：2020 年 3 月 31 日*

此版本包含版本 0.11.2003.2506 的次要錯誤修正。

## <a name="version-01120032506"></a>0\.11.2003.2506 版

*發行日期：2020 年 3 月 26 日*

此版本包含下列項目：

- 的新支援存取修飾詞 Q# ，如需詳細資訊，請參閱檔案 [結構](xref:microsoft.quantum.guide.filestructure)
- 已更新為 .NET Core SDK 3.1

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

## <a name="version-01020022610"></a>0\.10.2002.2610 版

*發行日期：2020 年 2 月 27 日*

此版本包含下列項目：

- 新的量子機器學習程式庫。如需詳細資訊，請移至我們的 [QML 文件頁面](xref:microsoft.quantum.machine-learning.concepts.intro)
- 我的 Q# bug 修正，在載入 NuGet 套件時，最多可提升 10 20 倍的效能

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

## <a name="version-01020012831"></a>0\.10.2001.2831 版

*發行日期：2020 年 1 月 29 日*

此版本包含下列項目：

- 新的 Microsoft.Quantum.SDK NuGet 套件，將在建立新專案時取代 Microsoft.Quantum.Development.Kit NuGet 套件。 現有專案將會繼續支援 Microsoft.Quantum.Development.Kit NuGet 套件。 
- 支援 Q# 編譯器擴充功能（由新的套件 NuGet 提供）。如需詳細資訊，請參閱[Github 上的檔](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler)、[編譯器延伸模組範例](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions)和[ Q# 開發人員 Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)
- 新增 .NET Core 3.1 支援，強烈建議您安裝 3.1.100 版，因為使用舊版 .NET Core SDK 版本可能會造成問題
- 在 Microsoft.Quantum.QsCompiler.Experimental 下提供新的編譯器轉換
- 以 HTML 格式公開輸出狀態向量的新功能Q#
- 已將 EstimateFrequencyA 支援新增至適用於 Hadamard 和 SWAP 測試的 Microsoft.Quantum.Characterization
- AmplitudeAmplification 命名空間現在使用 Q# 樣式指南

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

## <a name="version-01019120501"></a>版本 0.10.1912.0501

*發行日期：2019 年 12 月 5 日*

此版本包含下列項目：

- 單元測試的新測試屬性 Q# ，請參閱[此處的](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)更新 API 檔和更新的測試[here](xref:microsoft.quantum.guide.testingdebugging) & 偵錯工具指南
- 在程式執行錯誤的情況下新增堆疊追蹤 Q#
- 由於 [OmniSharp C# Visual Studio Code 延伸模組](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)更新，支援在 Visual Studio Code 中的中斷點

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

## <a name="version-01019111607"></a>版本 0.10.1911.1607

*發行日期：2019 年 11 月 17 日*

此版本包含下列項目：

- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) 和 Jupyter 筆記本的效能修正

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  


## <a name="version-0101911307"></a>版本 0.10.1911.307

*發行日期：2019 年 11 月 1 日*

此版本包含下列項目：

- Visual Studio Code & Visual Studio 擴充功能的更新，可將語言伺服器部署為獨立的可執行檔，以消除 .NET Core SDK 版本相依性  
- 移轉到 .NET Core 3.0
- 重大更新 - Microsoft.Quantum.Simulation.Core.IOperationFactory 引進新的 `Fail` 方法 此方法只會影響未擴充 SimulatorBase 的自訂模擬器。 如需詳細資料，請[檢閱 GitHub 中的提取要求](https://github.com/microsoft/qsharp-runtime/pull/59)。
- 受取代屬性的新增支援

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

## <a name="version-0919093002"></a>0\.9.1909.3002 版

*發行日期：2019 年 9 月 30 日*

此版本包含下列項目：

- Q#Visual Studio 2019 (16.3 版中的程式碼自動完成的新支援 &) & Visual Studio Code
- 量子 adder 的新 [Quantum Kata](https://github.com/Microsoft/QuantumKatas)

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

## <a name="version-09-packagereference-0919082902"></a>0\.9 版 (*PackageReference 0.9.1908.2902*)

*發行日期：2019 年 8 月 29 日*

此版本包含下列項目：

- 中 [結合語句](xref:microsoft.quantum.guide.operationsfunctions#conjugations) 的新支援 Q#
- 編譯器中的新程式碼動作 (例如：「取代為」、「新增文件」)，以及簡單的陣列項目更新
- 在 Visual Studio Code 延伸模組中新增了安裝範本和新的專案命令
- 新增了 ApplyIf 結合器的新變體，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- 有額外的 [Quantum Katas](https://github.com/Microsoft/QuantumKatas) 可轉換為 Jupyter Notebook
- Visual Studio 延伸模組現在需要 Visual Studio 2019

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。  

此處會摘要說明這些變更，以及升級現有程式的指示。  深入瞭解[ Q# 開發人員 blog](https://devblogs.microsoft.com/qsharp)上的這些變更。

## <a name="version-08-packagereference-0819071701"></a>0\.8 版 (*PackageReference 0.8.1907.1701*)

*發行日期：2019 年 7 月 12 日*

此版本包含下列項目：

- 切割陣列的新索引位置；請[參閱語言參考](xref:microsoft.quantum.guide.expressions#array-slices)以取得詳細資訊。
- 已新增 [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry)上裝載的 Dockerfile，如需詳細資訊，請參閱 [I 存放 Q# 庫。](https://github.com/microsoft/iqsharp/blob/main/README.md)
- [追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的重大變更、組態設定的更新、名稱變更；請參閱 [.NET API 瀏覽器以了解更新的名稱](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)。

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。  

## <a name="version-07-packagereference-0719053109"></a>0\.7 版 (*PackageReference 0.7.1905.3109*)

*發行日期：2019 年 5 月 31 日*

此版本包含下列項目：
- 語言的新增專案 Q# 
- 化學程式庫的更新， 
- 新的數值程式庫。

請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。  

此處會摘要說明這些變更，以及升級現有程式的指示。  深入瞭解[ Q# 開發人員 blog](https://devblogs.microsoft.com/qsharp)上的這些變更。

### <a name="no-locq-language-syntax"></a>Q# 語言語法
此版本新增了 Q# 語言語法：
* 新增[使用者自訂類型](xref:microsoft.quantum.guide.types#user-defined-types)的具名項目。  
* 使用者定義類型建構函式現在可以當作函式使用。
* 在使用者定義類型中新增 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 和 [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) 的支援。
* [重複直到成功](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)迴圈的修復區塊現在是選擇性的。
* 我們現在支援函式中 (而非作業中) 的 While 迴圈。

### <a name="library"></a>程式庫 

此版本新增了數值程式庫：請深入了解如何[使用新的數值程式庫](xref:microsoft.quantum.numerics.usage)，並試用[新範例](https://github.com/microsoft/quantum/tree/main/Numerics)。  [PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。  

此版本重組、擴充並更新了化學程式庫：
* 改善元件的模組化、擴充性、一般程式碼清除功能。  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。
* 新增[多重參考波函數](xref:microsoft.quantum.chemistry.concepts.multireference)的支援，包括疏鬆多重參考波函數和單一結合叢集。  [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。
* (謝謝！)[1QBit](https://1qbit.com) 參與者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用變分 ansatz 的能量評估。 [PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。
* 將 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 結構描述更新為新的 [0.2 版](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，並新增單一結合叢集規格。 [問題 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。
* 將 Python 互通性新增至化學程式庫函式。 試著使用此[範例](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration)。 [問題 #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。

## <a name="version-061905"></a>0\.6.1905 版

*發行日期：2019 年 5 月 3 日*

此版本包含下列項目：
- 對語言進行變更 Q# ， 
- 重新建構 Quantum Development Kit 程式庫， 
- 新增範例，以及 
- 修正 Bug。  [程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的數個已關閉的 PR。  

此處會摘要說明這些變更，以及升級現有程式的指示。  您可以在 devblogs.microsoft.com/qsharp 上深入了解這些變更。

### <a name="no-locq-language-syntax"></a>Q# 語言語法
此版本新增了 Q# 語言語法：
* 使用 `+` 運算子新增[用來表示量子作業特製化 (控制和伴隨) 的快速方法](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。  舊語法已被取代。  使用舊語法的程式 (例如 `: adjoint`) 將可繼續運作，但會產生編譯時間警告。  
* 新增 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 的運算子 `w/`，可用來將陣列的建立表示為現有陣列的修改。
* 新增一般 [apply-and-update 陳述式](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols)，例如 `+=`、`w/=`。
* 新增為[開放式指示詞](xref:microsoft.quantum.guide.filestructure#open-directives)中的命名空間指定簡短名稱的方法。

在此版本中，我們不再允許在 set 陳述式的左側指定陣列元素。  這是因為該語法意味著陣列是可變動的，然而事實上，作業的結果一律是經由修改建立新陣列。  系統將會產生編譯器錯誤，並建議使用新的 copy-and-update 運算子 `w/` 達到相同的結果。  

### <a name="library-restructuring"></a>程式庫重建
此版本重組了程式庫，使其能以一致的方式擴展：
* 將 Microsoft.Quantum.Primitive 命名空間重新命名為 Microsoft.Quantum.Intrinsic。  這些作業會由目標電腦實作。  Microsoft.Quantum.Primitive 命名空間已被取代。  當程式使用已被取代的名稱呼叫作業和函式時，會有執行階段警告提出建議。

* 將 Microsoft.Quantum.Canon 套件重新命名為 Microsoft.Quantum.Standard。  此套件包含大部分程式通用的命名空間 Q# 。  這包括：  
    - 一般作業的 Microsoft.Quantum.Canon
    - 一般用途算術運算的 Microsoft.Quantum.Arithmetic
    - 作業用來準備量子位元狀態的 Microsoft.Quantum.Preparation
    - 模擬功能的 Microsoft.Quantum.Simulation

經過這項變更後，如果程式包含用於命名空間 Microsoft.Quatum.Canon 的單一 "open" 陳述式，且其參考的作業已移至其他三個新的命名空間，則可能會發生建置錯誤。  為這三個新的命名空間新增額外的 open 陳述式，可直接了當地解決此問題。  

* 有數個命名空間已被取代，因為其中的作業已重組至其他命名空間。 使用這些命名空間的程式將可繼續運作，但會有編譯時間警告指出作業定義所在的命名空間。  

* Microsoft.Quantum.Arithmetic 命名空間已正規化為使用 <xref:microsoft.quantum.arithmetic.littleendian> 使用者定義類型。 需要轉換為 Little Endian 時，請使用函式 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。  

* 數個 callables (函式和作業) 的名稱已變更為符合[ Q# 樣式指南](xref:microsoft.quantum.contributing.style)。  舊的可呼叫名稱已被取代。  使用舊有可呼叫項目的程式將可繼續運作，但會出現編譯時間警告。 

### <a name="new-samples"></a>新範例

我們新增了搭配 [ Q# F # 驅動程式使用的範例](https://github.com/Microsoft/Quantum/pull/164)。  

**感謝** 下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。 這些貢獻會大幅增加至豐富的程式 Q# 代碼範例：

* Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函式合成。 [PR #135](https://github.com/Microsoft/Quantum/pull/135)。

### <a name="migrating-existing-projects-to-061905"></a>將現有的專案移轉至 0.6.1905。

若要更新 QDK，請參閱[安裝指南](xref:microsoft.quantum.install)。
  
如果您有 Q# 來自量子開發工具組0.5 版的現有專案，以下是將這些專案遷移至最新版本的步驟。

1. 專案必須依序升級。  如果您的解決方案有多個專案，請依照每個專案的參考順序加以更新。
2. 從命令提示字元執行， `dotnet clean` 以移除所有現有的二進位檔和中繼檔案。
3. 在文字編輯器中編輯 .csproj 檔案，將所有 "Microsoft.Quantum" `PackageReference` 的版本變更為 0.6.1904 版，並將 "Microsoft.Quantum.Canon" 套件名稱變更為 "Microsoft.Quantum.Standard"，例如：

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. 從命令提示字元中，執行此命令： `dotnet msbuild`  
5. 執行此命令後，您可能仍需手動解決因上述變更所造成的錯誤。  在許多情況下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 也會報告這些錯誤。
    - 在 Visual Studio 2019 或 Visual Studio Code 中開啟專案或其所屬解決方案的根資料夾。
    - 在編輯器中開啟 qs 檔案之後，您應該會 Q# 在 [輸出] 視窗中看到語言延伸模組的輸出。
    - 成功載入專案後 (會在輸出視窗中指出)，請開啟每個檔案，並手動解決其餘的所有問題。

> [!NOTE]
> * 對於 0.6 版本，隨附於 Quantum Development Kit 的語言伺服器不支援多個工作區。
> * 若要在 Visual Studio Code 中使用專案，請開啟包含專案本身和所有參考專案的根資料夾。   
> * 若要在 Visual Studio 中使用解決方案，解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。  
> * 在專案間移轉至 0.6 和更新版本的參考，以及使用舊版套件的專案，均**不**受支援。

## <a name="version-051904"></a>0\.5.1904 版

*發行日期：2019 年 4 月 15 日*

此版本包含 Bug 修正。


## <a name="version-051903"></a>0\.5.1903 版

*發行日期：2019 年 3 月 27 日*

此版本包含下列項目：

- 新增 Jupyter Notebook 的支援，提供絕佳的學習方式 Q# 。  請[查看新的 Jupyter Notebook 範例，並了解如何撰寫您自己的 Notebook](xref:microsoft.quantum.install)。 

- 將整數 adder 演算法新增至 Quantum Canon 程式庫。  另請參閱[說明如何使用新的整數 adder](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb) 的 Jupyter Notebook。

- 社群回報的 DumpRegister 問題 ([#148](https://github.com/Microsoft/Quantum/issues/148)) 的 Bug 修正。

- 新增了從 [Using 陳述式](xref:microsoft.quantum.guide.qubits#allocating-qubits)傳回的功能。

- 全新設計的[使用者入門指南](xref:microsoft.quantum.install)。


## <a name="version-051902"></a>0\.5.1902 版

*發行日期：2019 年 2 月 27 日*

此版本包含下列項目：

- 新增跨平台 Python 主機的支援。  `qsharp`適用于 python 的套件可讓您輕鬆地 Q# 從 Python 內模擬作業和函式。 深入了解 [Python 互通性](xref:microsoft.quantum.install)。 

- Visual Studio 和 Visual Studio Code 延伸模組現已支援符號 (例如函式和作業) 的重新命名。

- Visual Studio 延伸模組現已可安裝在 Visual Studio 2019 上。

## <a name="version-041901"></a>0\.4.1901 版

*發行日期：2019 年 1 月 30 日*

此版本包含下列項目：

- 新增新的基本類型 BigInt 的支援，此類型代表任意大小帶正負號的整數。  深入了解 [BigInt 類型](xref:microsoft.quantum.guide.types)。
- 新增 Toffoli 模擬器，這是一種特殊用途的快速模擬器，可模擬具有大量量子位元的 X、CNOT 和多重受控 X 量子作業。  深入了解 [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)。
- 新增簡單的資源估算器，以估計在量子電腦上執行特定實例作業所需的資源 Q# 。  深入了解[資源估算器](xref:microsoft.quantum.machines.resources-estimator)。


## <a name="version-0318112802"></a>0\.3.1811.2802 版

*發行日期：2018 年 11 月 28 日*

此版本已在與 `event-stream` NPM 套件相關的[延伸模組清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)期間加上旗標，並從 Marketplace 中移除，但我們的 VS Code 延伸模組並未加以使用。 此版本移除了所有可能致使延伸模組觸發任何紅色旗標的執行階段相依性。

如果您先前已安裝此延伸模組，您必須造訪 Visual Studio Marketplace 上的 [Visual Studio Code 延伸模組的 Microsoft Quantum Development Kit](vscode:extension/quantum.quantum-devkit-vscode)，並且按 [安裝] 重新加以安裝。 很抱歉造成您的不便。


## <a name="version-0318111511"></a>0\.3.1811.1511 版

*發行日期：2018 年 11 月 20 日*

此版本修正了導致某些使用者無法成功載入 Visual Studio 延伸模組的 Bug。

## <a name="version-031811203"></a>0\.3.1811.203 版

*發行日期：2018 年 11 月 2 日*

此版本包含一些 Bug 修正，包括：

* 在特定情況下，叫用 `DumpMachine` 可能會變更模擬器的狀態。
* 移除了在使用 2.1.403 之前的 .NET Core 版本建置專案時所產生的編譯警告。
* 清除了文件，特別是在 VS Code 或 Visual Studio 中暫留滑鼠時所顯示的工具提示。

## <a name="version-0318102508"></a>0\.3.1810.2508 版

*發行日期：2018 年 10 月 29 日*

此版本包含新的語言功能和改良的開發人員體驗：

* 此版本包含的語言伺服器 Q# ，以及 Visual Studio 和 Visual Studio Code 的用戶端整合。 這會啟用一組新的 IntelliSense 功能，以及以波狀底線的形式輸入錯誤和警告的即時反饋。 
* 整體而言，這項更新可讓您輕鬆瀏覽至精確的診斷範圍，並且在顯示的暫留資訊中提供其他詳細資料，而大幅改善了診斷訊息。
* Q#這種語言的延伸方法，是讓開發人員可以進行一般作業的方式，以及語言功能的新增強功能，來強大且快速的量子計算。  這一版的語言有一些重大變更 Q# 。   

此版本也包含新的量子化學程式庫：

* 化學程式庫包含新的 Hamiltonian 模擬功能，包括：
    - Trotter – 任意偶次的 Suzuki 整合器，用以改善模擬正確性。
    - 採用化學專用最佳化的量子位元化模擬技術，用以降低 $T$ 閘道複雜度。
* 導入了新的開放原始碼結構描述，名為 Broombridge 結構描述 (得名自被譽為 Hamiltonian 發源地的[地標](https://en.wikipedia.org/wiki/Broom_Bridge))，用以匯入分子的表示法及加以模擬。
* 提供多個使用 Broombridge 結構描述定義的化學標記法。  這些模型由 [NWChem](http://www.nwchem-sw.org/) (一種開放原始碼高效能運算化學工具) 所產生。
* 教學課程和範例會說明如何使用化學程式庫和 Broombridge 資料模型來：
    - 使用化學程式庫建構簡單的 Hamiltonian
    - 使用階段估算呈現氫化鋰的基態能量和激發態能量。
    - 執行量子化學模擬的資源估算。
    - 對 Broombridge 結構描述所代表的分子估算能階。
* 檔說明如何使用 NWChem 來產生其他化學模型，以使用進行量子模擬 Q# 。

深入了解 [Quantum Development Kit 化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)。

透過新的化學程式庫，我們將程式庫劃分到新的 GitHub 存放庫 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) 中。  範例仍保留在存放庫 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 中。  歡迎大家參與對這兩個存放庫的建構！

此版本包含針對社群回報的問題而提供的 Bug 修正和功能：

* Intellisense 適用于 Q# ？ ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。
* .qs 檔案 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。
* 改善 If 陳述式中的大括弧節略時的錯誤訊息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。
* 支援可變動 (重新) 繫結上的元組解構 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。
* 執行提供的 BitFlipCode 時發生的錯誤 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。
* H2SimulationGUI 有時會顯示大型尖峰 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。

### <a name="community-contributions"></a>社群貢獻

**感謝** 下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。 這些貢獻會大幅增加至豐富的程式 Q# 代碼範例：

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)) ：藉 Q# 由建立 QASM 至翻譯工具來改善 QASM/開發人員的體驗 Q# 。 [PR #58](https://github.com/Microsoft/Quantum/pull/58)。

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了實作 CHSH 賽局的範例；這是與非定域性相關的量子賽局。  [PR #84](https://github.com/Microsoft/Quantum/pull/84)。

同時感謝 Rohit Gupta ([@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90))、Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) 和 Lee James O'Riordan ([@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)) 為了改善我們所有人的內容，在文件、拼字和校對方面的努力付出！ 

## <a name="version-021809701"></a>0\.2.1809.701 版

*發行日期：2018 年 9 月 10 日*

此版本包含對社群回報的問題所做的 Bug 修正。 其中包括：

* 無法使用移位運算子 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。
* 在列印到主控台，`QCTraceSimulator` 上的 `DumpMachine` / `DumpRegister` 會失敗 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。
* 允許配置 0 個量子位元 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。
* `AssertQubitState` 需要明確的 Complex() 呼叫 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。
* macOS 上的 `Measure` 作業一律會傳回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。

感謝您！ 

## <a name="version-0218063001"></a>0\.2.1806.3001 版

*發行日期：2018 年 6 月 30 日*

此版本只是 [在 GitHub 上回報的問題 #48](https://github.com/Microsoft/Quantum/issues/48) 的快速修正（ Q# 如果使用者名稱包含空白空間) ，就 (編譯失敗）。 使用對應的新版本 (`0.2.1806.3001-preview`) 時，請遵循與 `0.2.1806.1503` 相同的更新指示。

## <a name="version-0218061503"></a>0\.2.1806.1503 版

*發行日期：2018 年 6 月 22 日*

此版本包含幾項社群貢獻，以及有所改善的偵錯體驗和增進的效能。  具體來說：

* QuantumSimulator 目標電腦的小型和大型模擬的效能改進。
* 改良的偵錯功能。
* 社群在 Bug 修正、新的 Helper 函式、作業和新範例等方面的貢獻。

### <a name="performance-improvements"></a>效能改善

這項更新包括所有目標電腦的大量和少量量子位元模擬皆有顯著的效能改善。  經由在 Quantum Development Kit 中作為標準範例的 H<sub>2</sub> 模擬，可發現改善的幅度顯而易見。

### <a name="improved-debugging-functionality"></a>改良的偵錯功能

此更新新增了偵錯功能：
* 新增了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 兩個新作業，可輸出目標量子電腦在某個時間點的波形函式相關資訊。  
* 在 Visual Studio 中，對單一量子位元測量 $\ket{1}$ 的機率現在會自動顯示在 QuantumSimulator 目標電腦的偵錯視窗中。
* 在 Visual Studio 中，變數屬性在 [自動變數] 和 [區域變數] 偵錯視窗中的顯示已有所改善。 

深入了解[測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)。

### <a name="community-contributions"></a>社群貢獻

Q#編碼員社區正在成長，我們會很高興以查看第一個使用者參與的程式庫，以及提交給開放程式碼基底的範例 http://github.com/Microsoft/quantum 。  **非常感謝** 下列參與者：
* Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一個範例，定義以轉換為基礎的邏輯合成方法，以建構用來實作指定排列的 Toffoli 網路。 程式碼完全以函式 Q# 和作業撰寫。  [PR #41](https://github.com/Microsoft/Quantum/pull/41)。
* RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)) ： Microsoft MVP Rolf Huisman 所提供的範例會從程式碼產生一般 QASM 程式碼，該 Q# 程式碼適用于沒有傳統控制流程和受限式量子作業的有限類別程式碼。 [PR #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：藉由提交受控作業適用的程式庫函式，協助我們改善程式碼基底。 [PR #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修正 @"microsoft.quantum.canon.quantumphaseestimation" 並建立了新的單元測試。  [PR #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：藉由確定 QuantumSimulator 執行個體已處置，清除了遙傳範例。 [PR #20](https://github.com/Microsoft/Quantum/pull/20)

同時也**非常感謝** 參與商業工程服務小組的 Microsoft 軟體工程師，他們在參加黑客松期間時對我們的文件做出了重要的變更。  他們的變更我們所有人大幅提升了定義的明確性和上線體驗：
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>更新現有的專案

此版本具完整的回溯相容性。 只要將專案中的 nuget 套件更新為 `0.2.1806.1503-preview` 版，並執行**完整重建**，即可確定所有中繼檔案都會重新產生。

在 Visual Studio 中，依照關於[更新套件](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的一般指示操作。

若要更新命令列的專案範本，請執行下列命令：
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

執行此命令後，任何使用 `dotnet new <project-type> -lang Q#` 建立的新專案都會自動使用此版本的 Quantum Development Kit。

若要更新現有的專案以使用最新版本，請從各個專案的目錄中執行下列命令：

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

如果現有的專案也使用 XUnit 整合進行單元測試，則也可以使用類似的命令來更新該套件：
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

根據您的測試專案所使用的 XUnit 版本，您可能也需要將 XUnit 更新為 2.3.1：
```
dotnet add package xunit -v "2.3.1" 
```

更新之後，請務必執行下列動作，以移除舊版所產生的所有暫存檔案：
```
dotnet clean 
```

### <a name="known-issues"></a>已知問題

沒有其他已知問題需要報告。


## <a name="version-0218022202"></a>0\.2.1802.2202 版

*發行日期：2018 年 2 月 26 日*

此版本提供在更多平台上進行開發的支援、語言互通性，和效能的強化。 具體來說：

- 支援以 macOS 和 Linux 為基礎的開發。 
- .NET Core 相容性，包括對 Visual Studio Code 的跨平台支援。
- Quantum Development Kit 程式庫的完整開放原始碼授權。
- 針對需要 20 個或更多量子位元的專案改善了模擬器效能。
- 與 Python 語言的互通性 (在 Windows 上可使用預覽版本)。

### <a name="net-editions"></a>.NET 版本

.NET 平台有兩種不同的版本可供使用：隨附於 Windows 的 .NET Framework，以及 Windows、macOS 和 Linux 上提供的開放原始碼 .NET Core。
在此版本中，Quantum Development Kit 大部分的組件均以 .NET Standard 程式庫的形式提供，這是 Framework 和 Core 通用的一組類別。
這些程式庫因而可與最新版本的 .NET Framework 或 .NET Core 相容。

因此，為了確保使用 Quantum Development Kit 撰寫的專案能有最高的可攜性，我們建議，使用 Quantum Development Kit 撰寫的程式庫專案應以 .NET Standard 為目標，而主控台應用程式則以 .NET Core 為目標。
由於舊版的 Quantum Development Kit 僅支援 .NET Framework，因此您可能需要移轉現有的專案；如需如何執行此作業的詳細資訊，請參閱下文。

### <a name="project-migration"></a>專案移轉

使用舊版 Quantum Development Kit 建立的專案仍可運作，只要您未更新其中使用的 NuGet 套件即可。 若要將現有的程式碼移轉至新版本，請執行下列步驟：
1. 使用正確類型的專案範本來建立新的 .NET Core 專案 Q# (應用程式、程式庫或測試專案) 。
2. 將舊專案中現有的 .qs 和 .cs/.fs 檔案複製到新專案 (使用 [新增] > [現有項目])。 請勿複製 AssemblyInfo.cs 檔案。
3. 建置並執行新的專案。

請注意，命名空間 Microsoft.Quantum.Canon 中的作業 RandomWalkPhaseEstimation 已移至 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存放庫的命名空間 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 中。

### <a name="known-issues"></a>已知問題

- 的 `--filter` 選項 `dotnet test` 無法針對以撰寫的測試正確運作 Q# 。
  因此，無法在 Visual Studio Code 中執行個別單元測試;建議您 `dotnet test` 在命令提示字元中使用，以重新執行所有測試。

## <a name="version-0118011707"></a>0\.1.1801.1707 版

*發行日期：2018 年 1 月 18 日*

此版本修正了社群回報的某些問題。 分別是：

- 模擬器現已可與早期不具 AVX 功能的 CPU 搭配運作。
- 區域小數設定不會導致剖析器 Q# 失敗。
- `SignD` 基本作業現在會傳回 `Int`，而不是 `Double`。


## <a name="version-011712901"></a>0\.1.1712.901 版

*發行日期：2017 年 12 月 11 日*

### <a name="known-issues"></a>已知問題

#### <a name="hardware-and-software-requirements"></a>硬體和軟體需求

- Quantum Development Kit 隨附的模擬器需要 Microsoft Windows 的 64 位元安裝才能執行。
- 與 Quantum Development Kit 一起安裝的 Microsoft 量子模擬器會使用 Advance Vector Extensions (AVX)，且需要具有 AVX 功能的 CPU。 2011 年第 1 季推出的 Intel 處理器 (Sandy Bridge) 或更新版本可支援 AVX。 我們正在評估對舊型 CPU 的支援，後續可能會發佈相關詳情。

#### <a name="project-creation"></a>專案建立

- 當您建立將使用的方案 ( .sln) 時 Q# ，方案必須高於方案中的每個專案 ( .csproj) 的一個目錄。 在建立新的解決方案時，只要確實核取 [新增專案] 對話方塊上的 [建立解決方案的目錄] 核取方塊，即可符合此條件。 若未執行此動作，則必須手動安裝 Quantum Development Kit NuGet 套件。

#### Q#

- Intellisense 不會顯示適當的程式 Q# 代碼錯誤。 請確定您在 Visual Studio 錯誤清單中顯示組建錯誤，以查看正確的 Q# 錯誤。 另請注意，在 Q# 您完成組建之前，不會顯示錯誤。
- 在部分應用程式中使用可變動陣列可能會導致非預期的行為。
- 將不可變陣列繫結至可變動陣列 (讓 a = b，其中 b 是可變動陣列)，可能會導致非預期的行為。
- 程式碼剖析、程式碼涵蓋範圍和其他 VS 外掛程式不一定會 Q# 正確地計算行數和區塊數。
- Q#編譯器不會驗證內插字串。 您可以藉由拼錯變數名稱或在內插字串中使用運算式，來建立 c # 編譯錯誤 Q# 。

#### <a name="simulation"></a>模擬

- 量子模擬器會使用 OpenMP 來平行處理所需的線性代數。 根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位元的程式常會執行緩慢，因為所需的協調會阻礙實際的工作。 將環境變數 OMP_NUM_THREADS 設定為較小的數值，即可修正此問題。 一個非常粗略的經驗法則是，1 個執行緒最多可用於 4 個量子位元，而其後的每個量子位元則應使用一個額外的執行緒，但這主要取決於您的演算法。

#### <a name="debugging"></a>偵錯

- ) 中的 F11 (步驟無法在程式碼中運作 Q# 。
- 在 Q# 程式碼中以中斷點或單一步驟暫停的程式碼反白顯示，有時會是不正確的。 醒目提示的程式碼行是正確的，但有時候，醒目提示的開頭和結尾會位於行中不正確的資料行上。

#### <a name="testing"></a>測試

- 測試必須在64位模式下執行。 如果您的測試失敗並出現 BadImageFormatException，請移至 [測試] 功能表，然後選取 [測試設定] > [預設處理器架構] > [X64]。
- 有些測試的執行會非常耗時 (最多可能需要 5 分鐘，視您的電腦而定)。 這是正常的，因為有些測試會使用超過 20 個量子位元；我們最大的測試目前以 23 個量子位元執行。

#### <a name="samples"></a>範例

- 在某些電腦上，某些小型樣本可能會執行緩慢，除非環境變數 OMP_NUM_THREADS 設定為 "1"。 另請參閱「模擬」下的版本資訊。

#### <a name="libraries"></a>程式庫

- 既有的隱含假設是，傳至作業中不同引數的量子位元是相異的。 例如，所有的程式庫作業 (以及所有模擬器) 都會假設傳至受控 NOT 的兩個量子位元是不同的。 若違反此假設，可能會導致無法預期的錯誤。 您可以使用量子電腦追蹤模擬器來測試這種情況。
- Microsoft.Quantum.Bind 函式不一定在各種情況下都會如預期運作。
- 在 Microsoft.Quantum.Extensions.Math 命名空間中，SignD 函式會傳回雙精度浮點數 (而非整數)，但基礎 System.Math.Sign 函式則一律會傳回整數。 您可以將結果與 1.0、-1.0 和 0.0 進行比較，因為這些雙精度浮點數具有相同的二進位表示法。
