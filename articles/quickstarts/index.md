---
title: 設定 Microsoft Quantum 開發套件 (QDK)
description: 了解如何為不同環境設定 Microsoft Quantum 開發套件。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: f0c3df1998f9b64ff6544867b83a7afe52b6f46d
ms.sourcegitcommit: fd57a845d013ae4578715d04b1ed1edc1c8ff6b4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "94870777"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>設定 Microsoft Quantum 開發套件 (QDK)

了解如何設定您環境的 Microsoft Quantum 開發套件 (QDK)，以便開始進行量子程式設計。 QDK 是由下列各項所組成的：

- Q#程式設計語言
- 可在 Q# 中抽象呈現複雜功能的一組程式庫
- 適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式
- 用來協助您進行開發的工具

Q# 程式可以使用 Visual Studio Code、Visual Studio，透過具有 IQ# Jupyter 核心的 Jupyter Notebook，或以 Python 或.NET language (C#, F#).撰寫的主機程式配對，並以獨立應用程式的形式執行。 您也可以使用 [Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/) 或 [Docker](#use-the-qdk-with-docker)，在線上執行 Q# 程式。 

## <a name="options-for-setting-up-the-qdk"></a>設定 QDK 的選項

您可以透過三種方式來使用 QDK：

- [在本機安裝 QDK](#install-the-qdk-locally)
- [線上使用 QDK](#use-the-qdk-online)
- [使用 QDK Docker 映像](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>在本機安裝 QDK

您可以在大部分的 [我的最愛] IDE 中開發 Q# 程式碼，以及將 Q# 與其他語言，例如 Python 和 .NET (C#, F#) 進行整合。

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS 程式碼<br>(2019 或更新版本)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="VS Studio" width="50"/><br><b>VS Studio<br>(2019 或更新版本)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter Notebook</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>命令列</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>OS 支援：</b></td>
        <td align="center">Windows、macOS、Linux</td>
        <td align="center">僅限 Windows</td>
        <td align="center">Windows、macOS、Linux</td>
        <td align="center">Windows、macOS、Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# 獨立</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">安裝</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# 和 Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安裝</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# 和 .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">安裝</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">安裝</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">安裝</a></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a>線上使用 QDK

您也可以使用下列選項來開發 Q# 程式碼，而不需要在本機上安裝任何東西：

|資源|優點|限制|
|---|---|---|
|[**Visual Studio 程式碼空間**](xref:microsoft.quantum.install.standalone)|豐富的線上開發環境  |需要 Azure 訂用帳戶和方案 |
|[**Binder**](xref:microsoft.quantum.install.binder) | 免費的線上筆記本體驗 |無持續性 |

## <a name="use-the-qdk-with-docker"></a>使用 QDK 搭配 Docker

您可以透過任何支援 Docker 映像的服務 (例如 ACI)，在本機 Docker 安裝或雲端中使用我們的 QDK Docker 映像。

您可以從 https://github.com/microsoft/iqsharp/#using-iq-as-a-container 下載 IQ# Docker 映像。 

您也可以使用 Docker 搭配 Visual Studio Code 遠端開發容器，以快速定義開發環境。 如需 VS Code 開發容器的詳細資訊，請參閱 https://github.com/microsoft/Quantum/tree/master/.devcontainer 。

## <a name="next-steps"></a>後續步驟

在[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)中有這些設定的工作流程描述和比較。
