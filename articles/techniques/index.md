---
title: Quantum 開發技術
description: 了解 Q# 程式開發的基本概念、使用作業、函式、變數和量子位元，以及建立簡單的量子程式。
keywords: 請勿在未諮詢 SEO 之前新增或編輯關鍵字。
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907710"
---
# <a name="quantum-development-techniques"></a>Quantum 開發技術

本文件的這個部分詳述所用的核心概念，讓您了解如何在 Q# 中建立量子程式以及從傳統應用程式與這些量子程式互動。
我們假設您對量子運算概念 (如[量子運算概念](xref:microsoft.quantum.concepts.intro)所述內容) 有*一些*了解，但您不需專精於量子運算，也能從這些章節獲益良多。

這個部分的內容如下。

- [Q# 程式概觀](xref:microsoft.quantum.techniques.file-structure)提供 Q# 程式設計語言的用途和功能概述。 
    文中特別闡明 Q# *不*只是用來模擬量子機制的語言，儘管我們的完整狀態模擬器確實有這個功能。 
    不如說 Q# 的設計是著眼於未來，其程式能描述傳統控制電腦如何與量子位元*互動*。 

- [作業和函數](xref:microsoft.quantum.techniques.opsandfunctions)詳細說明 Q# 語言的兩種可呼叫類型：*作業*含括量子位元和量子系統上的動作，*函數*則嚴格地處理傳統資訊。 
    如果沒有傳統和量子資訊同時運作，量子運算仍遙不可及。 
    本章節說明如何在 Q# 程式的控制流程中定義和使用這些可呼叫類型。

- [區域變數](xref:microsoft.quantum.techniques.local-variables)描述 Q# 程式中變數的角色，以及如何有效地運用。 
    特別是，您將瞭解不可變/可變變數之間的差異，以及如何指派/重新指派。

- [使用量子位元](xref:microsoft.quantum.techniques.qubits)說明可以用來處理個別量子位元和量子位元系統的 Q# 功能。 
    具體來說，這需要其配置、對其執行作業，最後對其測量。 
    此外，您還會學到一些實用的控制流程技術。

- 將其[全部放在一起](xref:microsoft.quantum.techniques.puttingittogether)，您將利用上述各章節中的技巧來建立程式，以執行**量子傳送**：使用兩個傳統位元來將量子位元的完整狀態「傳送」到另一個。

- [更進一步](xref:microsoft.quantum.techniques.going-further)介紹先進的技術，當您涉足更複雜的量子程式設計時，這會很有幫助。 
    特別是我們會討論在 Q# 中使用*類型參數化*的作業和函數，藉由保持與特定類型的輸入/輸出無關以及*借用*量子位元，達成更高順序的控制流程。 
    後者與基本量子位元配置不同之處在於，Q# 作業可以使用「已變更」的量子位元 --- 量子位元不一定會初始化為已知狀態 --- 來協助計算。

- [測試與偵錯](xref:microsoft.quantum.techniques.testing-and-debugging)詳細說明一些技術，用來確保您的程式碼會執行其作業。 
    由於量子資訊的一般不透明度，對量子程式進行偵錯可能需要特殊技術。 
    幸運的是，Q# 支援許多設計人員慣用的傳統偵錯技術，以及屬於量子特有的偵錯技術。 其中包括在 Q# 中建立/執行單元測試、在程式碼中的值和機率內嵌*判斷提示*，以及可輸出目標電腦狀態的 `Dump` 函數。 
    後者可與我們的完整狀態模擬器搭配使用，藉由迴避某些量子限制 (例如，不複製定理) 來偵錯計算的特定部分。


![Quantum](~/media/mobius_strip_preview.png)
