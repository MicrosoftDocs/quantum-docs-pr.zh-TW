---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699551"
---
# <a name="reversedople-function"></a><span data-ttu-id="cb786-102">ReversedOpLE 函式</span><span class="sxs-lookup"><span data-stu-id="cb786-102">ReversedOpLE function</span></span>

<span data-ttu-id="cb786-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cb786-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cb786-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb786-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb786-105">假設有一個作業採用位元組由小到大的輸入，則會傳回採用位元組由大到小的輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="cb786-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="cb786-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cb786-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="cb786-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb786-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cb786-108">要反轉其輸入的作業。</span><span class="sxs-lookup"><span data-stu-id="cb786-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="cb786-109">輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb786-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cb786-110">以位元組由大到小的暫存器形式接受其輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="cb786-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb786-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cb786-111">See Also</span></span>

- [<span data-ttu-id="cb786-112">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="cb786-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="cb786-113">ReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="cb786-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="cb786-114">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="cb786-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="cb786-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="cb786-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)