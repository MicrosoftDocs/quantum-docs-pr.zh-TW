---
title: 安裝 Microsoft Quantum Development Kit (QDK)
description: 如何為不同環境安裝 Microsoft Quantum Development Kit。
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863718"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安裝 Microsoft Quantum Development Kit (QDK)

了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。 QDK 是由下列各項所組成的：

- Q#程式設計語言
- 可在 Q# 中抽象呈現複雜功能的一組程式庫
- 適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式
- 用來協助您進行開發的工具

Q# 程式可以使用 Visual Studio Code、Visual Studio 或透過具有 IQ# Jupyter 核心的 Jupyter Notebook，以獨立應用程式的形式執行。
也可以與以 .NET 語言 (通常是 C#) 或 Python 撰寫的主機程式配對，讓您可以從傳統程式內部呼叫量子作業。

在[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)中有這些設定的工作流程描述和比較。

若要繼續安裝 QDK 並建立 Q# 專案，請選取您偏好的設定：

[使用 Q# 應用程式](xref:microsoft.quantum.install.standalone)開發 - 選擇此方法以從命令提示字元使用 Q#。 這不需要像下列選項的驅動程式或主機程式。

[使用 Q# Jupyter Notebook](xref:microsoft.quantum.install.jupyter) 開發 - 選取此環境，以內嵌文字的儲存格執行 Q# 程式碼，或建立量子計算互動式教學課程。 

[使用 Q# 和 Python](xref:microsoft.quantum.install.python) 開發 - 讓您結合 Python 和 Q# 來建立可呼叫 Q# 作業的 Python 主機程式。

[使用 Q# 和 .NET ](xref:microsoft.quantum.install.cs)開發 - 將 C#、F# 或 VB.NET 與 Q# 結合，以建立呼叫 Q# 作業的 .NET 主機程式。
