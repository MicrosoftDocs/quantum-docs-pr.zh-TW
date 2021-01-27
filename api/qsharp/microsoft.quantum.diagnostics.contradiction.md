---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 矛盾函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829356"
---
# <a name="contradiction-function"></a>矛盾函數

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>範例

下列 Q # 程式碼會列印 "Hello，world"：

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>另請參閱

- [Microsoft.. 診斷事實](xref:Microsoft.Quantum.Diagnostics.Fact)