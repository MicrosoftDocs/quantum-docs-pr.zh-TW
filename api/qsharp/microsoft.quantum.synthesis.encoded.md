---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 編碼函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701062"
---
# <a name="encoded-function"></a><span data-ttu-id="1f936-102">編碼函數</span><span class="sxs-lookup"><span data-stu-id="1f936-102">Encoded function</span></span>

<span data-ttu-id="1f936-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1f936-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1f936-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f936-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f936-105">編碼中的事實資料表編碼 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="1f936-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="1f936-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1f936-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="1f936-107">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1f936-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1f936-108">事實資料表作為真實值的陣列</span><span class="sxs-lookup"><span data-stu-id="1f936-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="1f936-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f936-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f936-110">事實資料表作為整數陣列 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="1f936-110">Truth table as array of {1,-1} integers</span></span>