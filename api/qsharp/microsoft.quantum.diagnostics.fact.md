---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事實函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698070"
---
# <a name="fact-function"></a>事實函數

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


宣告傳統條件為 true。

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="actual--bool"></a>實際： [Bool](xref:microsoft.quantum.lang-ref.bool)

要宣告的條件。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

當傳統條件為 false 時，要列印的失敗訊息字串。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Microsoft 量子。衝突](xref:Microsoft.Quantum.Diagnostics.Contradiction)