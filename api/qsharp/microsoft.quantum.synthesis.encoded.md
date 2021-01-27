---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 編碼函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855489"
---
# <a name="encoded-function"></a>編碼函數

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


編碼中的事實資料表編碼 {1,-1}

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>輸入

### <a name="table--bool"></a>table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

事實資料表作為真實值的陣列



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

事實資料表作為整數陣列 {1,-1}

## <a name="example"></a>範例

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```