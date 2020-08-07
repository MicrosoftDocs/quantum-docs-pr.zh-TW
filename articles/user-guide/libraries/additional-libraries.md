---
title: 使用其他連結 Q# 庫
description: 瞭解如何將其他連結 Q# 庫新增至您的量子應用程式。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869574"
---
# <a name="using-additional-no-locq-libraries"></a>使用其他連結 Q# 庫

量子開發工具組透過可新增至專案的_NuGet 套件_，提供額外的網域特定功能 Q# 。

| Q#機庫  | Nuget 套件 | 注意 |
|---------|---------|--------|
| [Q#標準程式庫](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft 量子標準**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | 預設包含 |
| [量子化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [量子數值程式庫](xref:microsoft.quantum.numerics.intro) | [**Microsoft 量子. 數值**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [量子機器學習程式庫](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

安裝配量開發工具組以搭配慣用的環境和主機語言使用之後，您就可以輕鬆地將程式庫新增至個別 Q# 專案，而不需要進行任何進一步的安裝。

> [!NOTE]
> 某些連結 Q# 庫可能適用于與您的程式一起運作 Q# ，或與您的主機應用程式整合的其他工具。
> 例如，化學連結[庫安裝指示](xref:microsoft.quantum.chemistry.concepts.installation)說明如何搭配 NWChem 計算化學平臺使用[ **Microsoft 量子**套件](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)，以及如何安裝 `qdk-chem` 命令列工具來處理量子化學資料。

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[Q#命令列應用程式或 .NET interopability](#tab/tabid-csproj)

**命令列或 Visual Studio Code：** 單獨使用命令列或從 Visual Studio Code 中，您可以使用 `dotnet` 命令，將 NuGet 套件參考新增至您的專案。
例如，若要新增[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)封裝，請執行下列命令：

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio：** 如果您使用 Visual Studio 2019 或更新版本，您可以 Q# 使用 NuGet 套件管理員新增其他套件。
若要載入封裝： 
1. 在 Visual Studio 中開啟專案時，從 [**專案**] 功能表選取 [**管理 NuGet 套件 ...** ]。

2. 按一下 **[流覽]**，選取 [**包含發行**前版本]，並搜尋封裝名稱 "Microsoft. 量子. 數值"。 這會列出可供下載的套件。

3. 將滑鼠游標暫留在 [**數值**] 上，然後按一下版本號碼右邊的向下箭號，即可安裝數值套件。

如需詳細資訊，請參閱[套件管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，您可以使用套件管理員主控台，透過命令列介面將數值程式庫新增至您的專案。

![從命令列使用套件管理員主控台](~/media/vs2017-nuget-console-menu.png)

從 [套件管理員主控台] 執行下列步驟：

```
Install-Package Microsoft.Quantum.Numerics
```

如需詳細資訊，請參閱[套件管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

## <a name="ino-locq-notebooks"></a>[我的 Q# 筆記本](#tab/tabid-notebook)

您可以 Q# 使用[ `%package` 魔術命令](xref:microsoft.quantum.iqsharp.magic-ref.package)，讓其他套件可在我的筆記本中使用。
例如，若要新增用於我筆記本的[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)封裝 Q# ，請在筆記本資料格中執行下列命令：

```
%package Microsoft.Quantum.Numerics
```

在此命令之後，筆記本中的任何資料格都可以使用此套件。
若要從 Q# 目前工作區中的程式碼提供封裝，請在新增封裝之後重載工作區：

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python 互通性](#tab/tabid-python)


您可以使用方法，讓其他套件可在 Python 主機程式中使用 [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) 。
例如，若要新增要在我的筆記本中使用的 [[**量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)] 套件 Q# ，請執行下列 Python 程式碼：

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

在此命令之後，會將封裝提供給使用編譯的任何程式 Q# 代碼 `qsharp.compile` 。
若要從 Q# 目前工作區中的程式碼提供封裝，請在新增封裝之後重載工作區：

```python
qsharp.reload()
```

***
