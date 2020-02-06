---
title: 數值程式庫安裝和驗證 |Microsoft Docs
description: 數值程式庫安裝和驗證
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: c41bb73ea484271689eea2ca1b59ce6639dc15a7
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036452"
---
# <a name="numerics-library-installation-and-validation"></a>數值程式庫安裝和驗證

量子開發工具組透過[`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet 套件提供數值功能的支援。

**Visual Studio > = 2019：** 如果您使用 Visual Studio 2019 或更新版本，您可以使用 NuGet 套件管理員新增數值套件。
若要這麼做，請選取 [管理 NuGet 套件 ...]從 Visual Studio 中的 [專案] 功能表項目。

從 [流覽] 索引標籤中，搜尋封裝名稱 "Microsoft. 量子. 數值"

> [!NOTE]
> 請務必勾選「包含發行前版本」

這會列出可供下載的套件。
將滑鼠暫留在 "Microsoft. 量子" 上會向右箭號顯示版本號碼的右方。
按一下箭號以安裝數值套件。

如需詳細資訊，請參閱[套件管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，您可以使用套件管理員主控台，透過命令列介面將數值程式庫新增至您的專案。

![](../../media/vs2017-nuget-console-menu.png)

從 [套件管理員主控台] 執行下列步驟：

```
Install-Package Microsoft.Quantum.Numerics
```

如需詳細資訊，請參閱[套件管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

**命令列或 Visual Studio Code：** 單獨使用命令列或從 Visual Studio Code 內，您可以使用 `dotnet` 命令，將 NuGet 套件參考新增至您的專案：

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>正在驗證您的安裝

就像其他的量子開發工具組一樣，數值程式庫隨附的範例可協助您儘快開始使用。
若要使用這些範例來測試您的安裝，請複製[主要的範例存放庫](https://github.com/Microsoft/Quantum)，然後執行其中一個範例。

若要執行[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd)範例：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
