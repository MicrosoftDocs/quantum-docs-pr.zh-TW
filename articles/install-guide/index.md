---
title: 了解如何安裝 Microsoft Quantum Development Kit (QDK)
description: 如何安裝適用於 C#、Python 和 Jupyter Notebook 環境的 Microsoft Quantum Development Kit。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680184"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安裝 Microsoft Quantum Development Kit (QDK)

了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。 QDK 是由下列各項所組成的：

- Q# 程式設計語言
- 可在 Q# 中抽象呈現複雜功能的一組程式庫
- 適用於 Python 和 .NET languages (C#、F#、VB.NET) 的 API，可執行以 Q# 撰寫的量子程式
- 用來協助您進行開發的工具

Q# 程式通常會搭配以 .NET 語言 (通常是 C#) 或 Python 撰寫的主機程式。 這可讓我們從傳統程式內呼叫量子作業。
除此之外，QDK 還提供具有 IQ# Jupyter 核心的 Jupyter Notebook 支援。

QDK 適用於多個開發環境。 從下列各節中選取您偏好的設定：

- [Q# 命令列應用程式：](xref:microsoft.quantum.install.standalone)如果您想要從命令列使用 Q #，請選擇此方法。 這不需要像下列選項的驅動程式或主機程式。
- [安裝 Q# for Jupyter Notebook：](xref:microsoft.quantum.install.jupyter)選擇此環境，以內嵌文字的儲存格執行 Q# 程式碼，或建立量子計算互動式教學課程。 
- [使用 Q# 和 Python 開發：](xref:microsoft.quantum.install.python)如果您想要結合 Python 和 Q# 來建立可呼叫 Q# 作業的 Python 主機程式。
- [使用 Q # 和 C# 或 F# 開發：](xref:microsoft.quantum.install.cs)如果您想要結合 C# 或 F# 和 Q # 以建立呼叫 Q # 作業的 .NET 主機程式。
