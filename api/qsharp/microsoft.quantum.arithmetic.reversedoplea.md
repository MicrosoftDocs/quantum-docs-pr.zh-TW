---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699550"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="558d1-102">ReversedOpLEA 函式</span><span class="sxs-lookup"><span data-stu-id="558d1-102">ReversedOpLEA function</span></span>

<span data-ttu-id="558d1-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="558d1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="558d1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="558d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="558d1-105">假設有一個作業採用位元組由小到大的輸入，則會傳回採用位元組由大到小的輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="558d1-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="558d1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="558d1-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="558d1-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="558d1-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="558d1-108">要反轉其輸入的作業。</span><span class="sxs-lookup"><span data-stu-id="558d1-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="558d1-109">輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="558d1-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="558d1-110">以位元組由大到小的暫存器形式接受其輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="558d1-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="558d1-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="558d1-111">See Also</span></span>

- [<span data-ttu-id="558d1-112">ApplyReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="558d1-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="558d1-113">ReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="558d1-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="558d1-114">ReversedOpLEC。</span><span class="sxs-lookup"><span data-stu-id="558d1-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="558d1-115">ReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="558d1-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)