---
title: 使用其他連結 Q# 庫
description: 瞭解如何將額外的連結 Q# 庫新增至您的量子應用程式。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992134"
---
# <a name="using-additional-no-locq-libraries"></a>使用其他連結 Q# 庫

量子開發工具組透過可新增至專案的 _NuGet 套件_ ，提供額外的網域特定功能 Q# 。

| Q# 圖書館  | Nuget 套件 | 注意 |
|---------|---------|--------|
| [Q# 標準程式庫](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft 量子. 標準**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | 預設包含 |
| [量子化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [量子數值程式庫](xref:microsoft.quantum.numerics.intro) | [**Microsoft. 數值**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [量子機器學習程式庫](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

安裝量子開發工具組以搭配慣用的環境和主機語言使用之後，您就可以輕鬆地將程式庫新增至個別的 Q# 專案，而不需要進一步安裝。

> [!NOTE]
> 某些程式庫適用于可與 Q# 您的程式一起運作 Q# ，或是與您的主機應用程式整合的其他工具。
> 例如，化學連結[庫安裝指示](xref:microsoft.quantum.chemistry.concepts.installation)會說明如何搭配使用 NWChem [ **Microsoft.Quantum.Chemistry**計算化學平臺](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)和使用命令列工具，以及如何安裝 `qdk-chem` 命令列工具來處理量子化學資料。

## <a name="no-locq-applications-or-net-interopability"></a>[Q# 應用程式或 .NET interopability](#tab/tabid-csproj)

**命令提示字元或 Visual Studio Code：** 您可以使用命令提示字元，或從 Visual Studio Code 內使用命令提示字元， `dotnet` 將 NuGet 套件參考新增至您的專案。
例如，若要新增 [**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) 封裝，請執行下列命令：

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio：** 如果您使用 Visual Studio 2019 或更新版本，您可以 Q# 使用 NuGet 封裝管理員新增其他套件。
載入封裝： 
1. 在 Visual Studio 中開啟專案時，從 [**專案**] 功能表中選取 [**管理 NuGet 套件 ...** ]。

2. 按一下 **[流覽]**，選取 [ **包含發行** 前版本]，並搜尋套件名稱 "Microsoft。 這會列出可供下載的套件。

3. 將滑鼠暫留在 **Microsoft. 數值** 上方，然後按一下版本號碼右邊的向下箭號，即可安裝數值套件。

如需詳細資訊，請參閱 [封裝管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，您也可以使用封裝管理員主控台，透過命令列介面，將數值程式庫新增至您的專案。

![從命令提示字元使用封裝管理員主控台](~/media/vs2017-nuget-console-menu.png)

從封裝管理員主控台，執行下列步驟：

```
Install-Package Microsoft.Quantum.Numerics
```

如需詳細資訊，請參閱 [封裝管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

## <a name="ino-locq-notebooks"></a>[我的 Q# 筆記本](#tab/tabid-notebook)

您可以 Q# 使用[ `%package` 魔術命令](xref:microsoft.quantum.iqsharp.magic-ref.package)，讓其他套件可在我的筆記本中使用。
例如，若要新增要在我的筆記本中 [**使用的 node.js 套件**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) Q# ，請在筆記本資料格中執行下列命令：

```
%package Microsoft.Quantum.Numerics
```

在此命令之後，筆記本內的任何資料格都可以使用此套件。
若要讓封裝可從 Q# 目前工作區中的程式碼使用，請在新增套件之後重載工作區：

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python 互通性](#tab/tabid-python)


您可以使用方法，將其他套件提供給 Python 主機程式使用 [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) 。
例如，若要新增要在我的筆記本中 [**使用的 node.js 套件**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) Q# ，請執行下列 Python 程式碼：

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

在這個命令之後，封裝將可供使用所編譯的任何程式 Q# 代碼使用 `qsharp.compile` 。
若要讓封裝可從 Q# 目前工作區中的程式碼使用，請在新增套件之後重載工作區：

```python
qsharp.reload()
```

***
