---
uid: Microsoft.Quantum.Synthesis.Extended
title: 擴充函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855480"
---
# <a name="extended-function"></a><span data-ttu-id="534c1-102">擴充函數</span><span class="sxs-lookup"><span data-stu-id="534c1-102">Extended function</span></span>

<span data-ttu-id="534c1-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="534c1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="534c1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="534c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="534c1-105">以反轉係數擴充頻譜</span><span class="sxs-lookup"><span data-stu-id="534c1-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="534c1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="534c1-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="534c1-107">頻譜： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="534c1-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="534c1-108">光譜系數</span><span class="sxs-lookup"><span data-stu-id="534c1-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="534c1-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="534c1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="534c1-110">後面接著反向複製的係數</span><span class="sxs-lookup"><span data-stu-id="534c1-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="534c1-111">範例</span><span class="sxs-lookup"><span data-stu-id="534c1-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```