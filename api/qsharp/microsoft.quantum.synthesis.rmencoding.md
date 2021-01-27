---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855335"
---
# <a name="rmencoding-function"></a><span data-ttu-id="e072b-102">RMEncoding 函式</span><span class="sxs-lookup"><span data-stu-id="e072b-102">RMEncoding function</span></span>

<span data-ttu-id="e072b-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e072b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e072b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e072b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e072b-105">{-1,1} 布林值真值的編碼</span><span class="sxs-lookup"><span data-stu-id="e072b-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="e072b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e072b-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="e072b-107">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e072b-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e072b-108">布林值</span><span class="sxs-lookup"><span data-stu-id="e072b-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="e072b-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e072b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e072b-110">如果 `b` 為 false，則為1，否則為-1</span><span class="sxs-lookup"><span data-stu-id="e072b-110">1, if `b` is false, otherwise -1</span></span>