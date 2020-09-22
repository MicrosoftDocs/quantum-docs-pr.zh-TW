---
title: Microsoft Q# 標準程式庫簡介
description: 了解定義量子程式中所用作業、函式和資料類型的 Microsoft Q# 標準程式庫。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 63709015a12a7f972a676018970143ca163e92d0
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836007"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Q# 標準程式庫簡介

Q# 是由各種包含 Q# *標準程式庫*的不同實用作業、函式和使用者定義的類型提供支援。
在[安裝和驗證](xref:microsoft.quantum.install)期間安裝的 [`Microsoft.Quantum.Development.Kit` NuGet 套件](https://www.nuget.org/packages/microsoft.quantum.development.kit) 會提供 Q# 編譯器，以及由目標機器實作的標準程式庫組件。
此[`Microsoft.Quantum.Standard`套件](https://www.nuget.org/packages/microsoft.quantum.standard)可提供跨目標電腦的可攜式 Q# 標準程式庫部分。

在 [API 文件](xref:microsoft.quantum.apiref-intro)中，Q# 標準程式庫所定義的符號會有更完整、更詳盡的定義。

在下列各節中，我們將概述每部分標準程式庫的最重要功能，並提供有關如何實際使用每項功能的一些內容。
