---
title: 量子機器學習套件簡介 | Microsoft Docs
description: 量子機器學習套件簡介
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 321901a7976e4633a672495827c27c5f1645ad30
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835684"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>量子機器學習程式庫簡介

量子機器學習程式庫是以 Q# 撰寫的 API，可讓您執行混合式量子/傳統機器學習實驗。 程式庫讓您能夠：

- 載入您自己的資料，並使用量子模擬器來分類

- 使用範例和教學課程來了解量子機器學習的領域

此效能可能比目前的傳統機器學習架構低 (請記住，所有項目都會在已耗用大量運算資源的模擬量子裝置上執行)。

本文件的目的是：

- 簡介適用於混合式量子/傳統學習的機器學習工具 (以 Q\# 撰寫)。
- 介紹機器學習概念，尤其是其如何運用在量子線路中心分類器 (也稱為量子循序分類器)。
- 提供一組基本概念教學課程，協助您開始使用程式庫所提供的工具。
- 討論這類分類器的訓練和驗證方法，以及其如何轉譯為程式庫所提供的特定 Q\# 作業。

此程式庫中所執行的模型是以[線路中心量子分類器](https://arxiv.org/abs/1804.00633)中所呈現的量子傳統訓練配置為基礎
