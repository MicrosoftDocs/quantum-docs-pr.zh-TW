---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698682"
---
# <a name="isnotzero-function"></a><span data-ttu-id="83b60-102">IsNotZero 函式</span><span class="sxs-lookup"><span data-stu-id="83b60-102">IsNotZero function</span></span>

<span data-ttu-id="83b60-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="83b60-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="83b60-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83b60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83b60-105">檢查某個 `Double` 數位是否大約為零。</span><span class="sxs-lookup"><span data-stu-id="83b60-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="83b60-106">輸入</span><span class="sxs-lookup"><span data-stu-id="83b60-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="83b60-107">數位： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83b60-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83b60-108">要檢查的數位</span><span class="sxs-lookup"><span data-stu-id="83b60-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="83b60-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="83b60-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="83b60-110">如果的 `number` 絕對值大於，則傳回 true `1e-15` 。</span><span class="sxs-lookup"><span data-stu-id="83b60-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>