---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701139"
---
# <a name="rmencoding-function"></a><span data-ttu-id="939ca-102">RMEncoding 函式</span><span class="sxs-lookup"><span data-stu-id="939ca-102">RMEncoding function</span></span>

<span data-ttu-id="939ca-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="939ca-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="939ca-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="939ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="939ca-105">{-1,1} 布林值真值的編碼</span><span class="sxs-lookup"><span data-stu-id="939ca-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="939ca-106">輸入</span><span class="sxs-lookup"><span data-stu-id="939ca-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="939ca-107">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="939ca-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="939ca-108">布林值</span><span class="sxs-lookup"><span data-stu-id="939ca-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="939ca-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="939ca-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="939ca-110">如果 `b` 為 false，則為1，否則為-1</span><span class="sxs-lookup"><span data-stu-id="939ca-110">1, if `b` is false, otherwise -1</span></span>