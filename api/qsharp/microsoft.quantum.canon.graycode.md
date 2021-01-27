---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840505"
---
# <a name="graycode-function"></a><span data-ttu-id="28bc1-102">GrayCode 函式</span><span class="sxs-lookup"><span data-stu-id="28bc1-102">GrayCode function</span></span>

<span data-ttu-id="28bc1-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28bc1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28bc1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28bc1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28bc1-105">建立灰色的程式碼序列</span><span class="sxs-lookup"><span data-stu-id="28bc1-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="28bc1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="28bc1-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="28bc1-107">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28bc1-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28bc1-108">位數</span><span class="sxs-lookup"><span data-stu-id="28bc1-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="28bc1-109">輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="28bc1-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="28bc1-110">元組的陣列。</span><span class="sxs-lookup"><span data-stu-id="28bc1-110">Array of tuples.</span></span> <span data-ttu-id="28bc1-111">元組中的第一個值是元組中 GrayCode 序列第二個值的值，是目前值中要變更的位置，以取得下一個值。</span><span class="sxs-lookup"><span data-stu-id="28bc1-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="28bc1-112">範例</span><span class="sxs-lookup"><span data-stu-id="28bc1-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```