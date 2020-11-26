---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204057"
---
# <a name="isnotzero-function"></a><span data-ttu-id="46142-102">IsNotZero 函式</span><span class="sxs-lookup"><span data-stu-id="46142-102">IsNotZero function</span></span>

<span data-ttu-id="46142-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="46142-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="46142-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="46142-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="46142-105">檢查某個 `Double` 數位是否大約為零。</span><span class="sxs-lookup"><span data-stu-id="46142-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="46142-106">輸入</span><span class="sxs-lookup"><span data-stu-id="46142-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="46142-107">數位： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="46142-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="46142-108">要檢查的數位</span><span class="sxs-lookup"><span data-stu-id="46142-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="46142-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="46142-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="46142-110">如果的 `number` 絕對值大於，則傳回 true `1e-15` 。</span><span class="sxs-lookup"><span data-stu-id="46142-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>