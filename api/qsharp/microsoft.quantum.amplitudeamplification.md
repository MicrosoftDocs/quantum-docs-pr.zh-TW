---
uid: Microsoft.Quantum.AmplitudeAmplification
title: AmplitudeAmplification 命名空間
ms.date: 1/23/2021 12:00:00 AM
ms.topic: managed-reference
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: a014f923de62c5e660c1c0fc839fbe60e80f8ba9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845839"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>AmplitudeAmplification 命名空間

此命名空間包含用來執行振幅放大的函式和作業。



## <a name="description"></a>描述

使用部分反射的無警示幅度放大是在此處實作為的最常見振幅放大形式。

這是透過 operation AmpAmpObliviousByReflectionPhases 呼叫。

這有兩個暫存器： `ancillaRegister` 和 `systemRegister` 。

這會針對這些類型的反射接受兩個 oracle，而這種類型的反映 `ReflectionOracle` 只會在註冊上作用 `ancillaRegister` 。

這會接受 oracle 特殊的無警示振幅類型，這兩種類型的動作會 `ObliviousOracle` 同時在這兩個註冊上共同運作。

的輸入狀態 `ancillaRegister` 會假設為第一個反映運算子的唯一 $-$1 eigenstate，$I-2 \ ket {s} \ bra {s} $。

關於目標量子狀態的反映通常是藉由假設存取 oracle 來執行，此狀態是從計算基礎 $ \ket{0\cdots 0} $ 準備該狀態。

我們對這些 oracle 的慣例需要兩個暫存器：單一量子位的 `flagQubit` 註冊，以及 ancillaRegister 註冊上其他所有專案的註冊。

類型的 oracle 會 `StateOracle` 在這兩個暫存器上共同運作，以建立以 $ \ket $ 標示的目標狀態， {1} `flagQubit` 並在註冊中使用某些真實的波幅。

`ReflectionOracle`此旗標狀態的反映是由作業產生 `TargetStateReflectionOracle` 。

`ReflectionOracle`有關輸入狀態的反映 `ancillaRegister` 是由反轉 StateOracle 產生，然後以 ReflectionStart ( # A1 來反映 $ \ket{0\cdots 0} $。

型別的 oracle `DeterministicStateOracle` 作用於暫存器 `qubitState` ，以建立完全不含旗標的目標狀態。

`AmpAmpObliviousByOraclePhases` 是無警示振幅放大的版本，可接受 oracle `StateOracle` 而 `ObliviousOracle` 不是反射。

請注意，振幅放大是無警示幅度放大的特殊案例 `ObliviousOracle` ，其中是身分識別運算子，而且沒有任何系統量子位，也就是 `systemRegister` 空的。

這是透過作業和來 `AmpAmByReflectionPhases` 呼叫 `AmpAmpByOraclePhases` 。

格羅弗搜尋標準案例中部分反射的階段是由函數 AmpAmpPhasesStandard 提供。

舉例來說，我們有下列相依性： AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases。