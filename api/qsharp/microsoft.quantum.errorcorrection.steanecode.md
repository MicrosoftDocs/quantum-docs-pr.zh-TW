---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200470"
---
# <a name="steanecode-function"></a>SteaneCode 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回代表⟦7、1、3⟧ Steane 程式碼編碼器的 CSS 值，以及具有就地發生症狀測量的解碼器。

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>輸出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

CSS 型別的物件，它會收集所有相關資料，以執行⟦7、1、3⟧ Steane 程式碼的編碼和錯誤修正。

## <a name="remarks"></a>備註

下列文章中找到此程式碼：

- A. Steane，「多個粒子干擾和量子錯誤修正」，處理器。 羅伊。 Soc. Lond。 A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.