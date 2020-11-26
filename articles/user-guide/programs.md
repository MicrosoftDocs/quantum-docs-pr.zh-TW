---
title: 'Q # Introdution'
description: Q 中的量副程式快速簡介#
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233235"
---
# <a name="q-quantum-programming-language"></a>Q # 量副程式設計語言

Q # [語言指南](xref:microsoft.quantum.qsharp.index)中詳細說明 q # 程式設計語言的所有須知。 就像其他任何東西一樣，我們的 [語言設計](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) 程式是開放原始碼，我們歡迎您提供貢獻。
如需有關 Q # 背後之基礎和動機的詳細背景，請參閱 [為什麼我們需要 q #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。  
Q # 隨附于量子開發工具組中 (QDK) 若要快速流覽，請查看 [何謂 QDK？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什麼是量副程式？

量副程式可以視為一組特定的傳統副程式，在呼叫時，會與量子系統互動來執行計算;以 Q # 撰寫的程式不會直接建立量子狀態的模型，而是描述傳統控制電腦與量子位互動的方式。
如此一來，我們就完全 *不* 知道每一部目的電腦上的量子狀態為何，這可能會根據電腦而有不同的解釋。 

其中一個很重要的結果，是 Q # 無法直接 introspect 至量子位的狀態或量子機制的其他屬性，以確保可以在量子電腦上實際執行 Q # 程式。
相反地，程式可以呼叫作業，例如 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 從量子位中解壓縮傳統資訊。

配置之後，就可以將量子位傳遞給作業和函式，也稱為 *callables*。 在某些方面，Q # 程式可以使用量子位來完成;量子位狀態的任何直接動作 *都是由* 內建 callables （例如和）定義，也就是 [`X`](xref:Microsoft.Quantum.Intrinsic.X) [`H`](xref:Microsoft.Quantum.Intrinsic.H) 未在 Q # 中定義，而是由目的電腦定義的 callables。 這些作業實際 *執行* 的動作，只是我們用來執行特定 Q # 程式的目的電腦。

例如，如果在我們的 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器會對模擬的量子系統執行對應的數學運算。
但在未來，當目的電腦是真實量子電腦時，在 Q # 中呼叫這類作業會將量子電腦導向 *實際* 量子 (系統上的 *實際* 操作，例如精確地計時的雷射脈衝) 。

Q # 程式會 recombines 目的電腦所定義的這些作業，以建立新的較高層級作業來表示量子計算。
如此一來，Q # 可讓您輕鬆地表達基礎量子和混合式量子（傳統演算法）的邏輯，同時也會與目的電腦或模擬器的結構大致相關。

下列程式是一個簡單的範例，它會配置 $ \ket $ 狀態中的一個量子位 {0} ，然後將 Hadamard 作業套用 `H` 至該程式，並以基礎測量結果 `PauliZ` 。

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

我們的 [量子 Katas](https://github.com/microsoft/QuantumKatas#introduction) 提供 [量子運算概念](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) 的簡介，例如常見的量子作業，以及如何操作量子位。 您也可以在 [內部作業和](xref:microsoft.quantum.libraries.standard.prelude)函式中找到更多範例。



