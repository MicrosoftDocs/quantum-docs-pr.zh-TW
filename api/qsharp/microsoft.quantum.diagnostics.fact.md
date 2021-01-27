---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事實函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853312"
---
# <a name="fact-function"></a>事實函數

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>範例

下列 Q # 程式碼片段將會失敗：

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>另請參閱

- [Microsoft 量子。衝突](xref:Microsoft.Quantum.Diagnostics.Contradiction)