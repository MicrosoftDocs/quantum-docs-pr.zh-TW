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
# <a name="encoded-function"></a><span data-ttu-id="650ef-102">編碼函數</span><span class="sxs-lookup"><span data-stu-id="650ef-102">Encoded function</span></span>

<span data-ttu-id="650ef-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="650ef-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="650ef-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="650ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="650ef-105">編碼中的事實資料表編碼 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="650ef-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="650ef-106">輸入</span><span class="sxs-lookup"><span data-stu-id="650ef-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="650ef-107">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="650ef-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="650ef-108">事實資料表作為真實值的陣列</span><span class="sxs-lookup"><span data-stu-id="650ef-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="650ef-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="650ef-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="650ef-110">事實資料表作為整數陣列 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="650ef-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="650ef-111">範例</span><span class="sxs-lookup"><span data-stu-id="650ef-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```