---
title: 量子化學程式庫簡介
description: 了解 Microsoft 量子化學程式庫，以及如何使用該程式庫來模擬量子電腦上的電子結構問題。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907319"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>量子化學程式庫簡介

實體系統的模擬在量子運算的領域一直扮演著重要角色。  這是因為一般普遍認為量子力學難以在量子電腦上進行模擬，這意味著，模擬系統的複雜度會隨著量子系統的大小呈指數增長。  模擬化學和教材科學的問題，可能仍是最令人印象深刻的量子運算應用，且讓我們能夠探索至今仍沒有能力測量或模擬的化學反應機制。  這也讓我們得以模擬相互關聯的電子資料，例如高溫超導體。 這個領域的應用範圍很廣。

本文件的目的是要簡扼介紹如何在量子電腦上模擬電子結構問題，以協助讀者了解 Hamiltonian 模擬程式庫的多種層面在此領域中扮演的角色。  首先我們會簡單介紹量子機制，然後討論如何據以進行電子系統的模型化。  接著，我們將討論如何使用量子電腦來模擬這類量子力學。  然後，我們將討論兩種用來將量子力學編譯為基本閘道序列的方法：Trotter-Suzuki 分解和量子位元化。
