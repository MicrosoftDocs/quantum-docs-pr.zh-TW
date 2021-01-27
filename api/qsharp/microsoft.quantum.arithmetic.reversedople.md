---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846402"
---
# <a name="reversedople-function"></a><span data-ttu-id="3fa0a-102">ReversedOpLE 函式</span><span class="sxs-lookup"><span data-stu-id="3fa0a-102">ReversedOpLE function</span></span>

<span data-ttu-id="3fa0a-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3fa0a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3fa0a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fa0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fa0a-105">假設有一個作業採用位元組由小到大的輸入，則會傳回採用位元組由大到小的輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="3fa0a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3fa0a-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="3fa0a-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fa0a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3fa0a-108">要反轉其輸入的作業。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="3fa0a-109">輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fa0a-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3fa0a-110">以位元組由大到小的暫存器形式接受其輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fa0a-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3fa0a-111">See Also</span></span>

- [<span data-ttu-id="3fa0a-112">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="3fa0a-113">ReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="3fa0a-114">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="3fa0a-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="3fa0a-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)