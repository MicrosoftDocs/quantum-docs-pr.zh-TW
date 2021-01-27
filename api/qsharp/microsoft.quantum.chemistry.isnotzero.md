---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839589"
---
# <a name="isnotzero-function"></a><span data-ttu-id="b3362-102">IsNotZero 函式</span><span class="sxs-lookup"><span data-stu-id="b3362-102">IsNotZero function</span></span>

<span data-ttu-id="b3362-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b3362-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="b3362-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b3362-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b3362-105">檢查某個 `Double` 數位是否大約為零。</span><span class="sxs-lookup"><span data-stu-id="b3362-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b3362-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b3362-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="b3362-107">數位： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3362-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3362-108">要檢查的數位</span><span class="sxs-lookup"><span data-stu-id="b3362-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="b3362-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3362-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3362-110">如果的 `number` 絕對值大於，則傳回 true `1e-15` 。</span><span class="sxs-lookup"><span data-stu-id="b3362-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>