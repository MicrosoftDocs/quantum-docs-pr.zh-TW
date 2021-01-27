---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 878b0fae8a803b3136d1537309c945c052e1052c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846473"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="228b6-102">ReversedOpBE 函式</span><span class="sxs-lookup"><span data-stu-id="228b6-102">ReversedOpBE function</span></span>

<span data-ttu-id="228b6-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="228b6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="228b6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="228b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="228b6-105">假設有一個使用位元組由大到小的輸入，則會傳回採用位元組由小到大輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="228b6-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="228b6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="228b6-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="228b6-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="228b6-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="228b6-108">要反轉其輸入的作業。</span><span class="sxs-lookup"><span data-stu-id="228b6-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="228b6-109">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="228b6-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="228b6-110">以位元組由大到小的暫存器形式接受其輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="228b6-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="228b6-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="228b6-111">See Also</span></span>

- [<span data-ttu-id="228b6-112">ApplyReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="228b6-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="228b6-113">ReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="228b6-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="228b6-114">ReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="228b6-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="228b6-115">ReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="228b6-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)