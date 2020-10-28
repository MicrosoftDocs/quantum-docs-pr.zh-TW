---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 矛盾函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698122"
---
# <a name="contradiction-function"></a>矛盾函數

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


宣告傳統條件為 false。

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--bool"></a>實際： [Bool](xref:microsoft.quantum.lang-ref.bool)

要宣告的條件。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

當傳統條件為真時，所要列印的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Microsoft.. 診斷事實](xref:Microsoft.Quantum.Diagnostics.Fact)