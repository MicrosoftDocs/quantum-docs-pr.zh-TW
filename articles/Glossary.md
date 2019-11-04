---
title: 詞彙 |Microsoft Docs
description: 量子詞彙詞彙
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: bfa275b3330ea2c2a541b08f137893b63b6213aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183619"
---
|條款|定義|
|-------------|----------|
|Adjoint|運算的複雜共軛轉置。 若為執行單一運算子的作業，則 adjoint 是運算的反向。|
|多次|作業和函數統稱為*callables*。|
|Standard|在 Q # 中針對序言中定義的邏輯所定義的作業和函數。 標準程式庫的執行與目的電腦無關。|
|Clifford 群組|佔用 Bloch 球體 octants 的一組作業。 其中包括： `X`、`Y`、`Z`、`H` 和 `S`|
|管理|接受一或多個 qubits 做為目標作業的啟用程式的量子作業。|
|Dirac 標記法|量子狀態的簡短標記法。 如需詳細資訊，請參閱[Dirac 標記法](xref:microsoft.quantum.concepts.dirac)一節。|
|特徵值和特徵向量|如需詳細資訊，請參閱[Advanced Matrix 一節](xref:microsoft.quantum.concepts.matrix-advanced)。|
|EPR 配對|也稱為「[鈴」狀態](https://en.wikipedia.org/wiki/Bell_state)|
|改革|狀態如何隨著時間變更。 如需範例，請參閱 <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> 的一節。 |
|函式|問 # 語言中純傳統的常式|
| <a id="global-phase"></a>全域階段 | $E ^ {i\phi} $ 的兩個狀態與複數的倍數相同，其最多隻會與全域階段不同。 不同于本機階段，全域階段無法透過任何測量來觀察。 如需詳細資訊，請參閱[Pauli 度量](xref:microsoft.quantum.concepts.pauli)。 |
|測量|從 qubit （或 qubits 集）取得古典位。 如需詳細資訊，請參閱[Qubit 概念](xref:microsoft.quantum.concepts.qubit)一節。|
|可變動|其值在建立之後可能會變更的變數。|
|命名空間|相關名稱集合的標籤（通常是作業、函數和類型）。 例如，命名空間[`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation)將標準程式庫中定義的所有符號加上標籤，以協助準備初始狀態。|
|作業|Q # 中的基本量子執行單位。 它大致上等同於 C、C++ 或 Python 中的函式，或是 C# 或 Java 中的靜態方法。|
|操作員應用程式|執行量子作業。 這通常會將單一矩陣套用至目前的狀態向量。 如需詳細資訊，請參閱[量子概念簡介](xref:microsoft.quantum.concepts.intro)。|
|Oracle|副程式，在執行時間提供資料相依的資訊給量子演算法。 一般來說，其目標是要提供對應于重迭中輸入的輸出重迭。   |
|部分應用程式|呼叫沒有所有必要參數的函式或作業。 會傳回新的可呼叫，其只需要在未來應用程式期間提供的遺漏參數。|
|Pauli 運算子|`X`、`Y` 和 `Z` 量子閘道。|
|序言|每個個別目的電腦所定義的一組基本和傳統作業和函式，而不是在 Q # 層級。|
|量子線路|適用于量子電腦的程式標記法。 如需詳細資訊，請參閱 <xref:microsoft.quantum.concepts.circuits> 一節。|
|量子狀態|系統中 qubits 的標記法。 這通常表示為複雜的資料行向量。 如需詳細資訊，請參閱 <xref:microsoft.quantum.concepts.vectors>。 |
|qubit|量子儲存體的單位。 如需詳細資訊，請參閱 <xref:microsoft.quantum.concepts.qubit> 一節。|
|重複直到-成功|機率成功的量子演算法。 失敗時，常式會重新嘗試直到成功為止（或已達到限制）。 |
|軟體堆疊|一組完整的傳統和量子軟體，以及操作量子電腦所需的編譯器、模擬器和執行時間。 如需詳細資訊，請參閱 <xref:microsoft.quantum.concepts.software-stack> 一節。 |
|目的電腦|將抽象的量副程式降低到硬體或模擬的編譯目標。 這通常包括重新寫入的許多用途，包括閘道更換、錯誤更正的編碼、幾何版面配置等等。|
|構成|以逗號分隔的類型會透過括弧分組在一起。 |
|使用者定義型別|內建或先前定義之類型的集合，可能稱為單一單位。|

