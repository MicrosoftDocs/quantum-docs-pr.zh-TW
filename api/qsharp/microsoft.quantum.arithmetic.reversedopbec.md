---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699556"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="de433-102">ReversedOpBEC 函式</span><span class="sxs-lookup"><span data-stu-id="de433-102">ReversedOpBEC function</span></span>

<span data-ttu-id="de433-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="de433-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="de433-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de433-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de433-105">假設有一個使用位元組由大到小的輸入，則會傳回採用位元組由小到大輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="de433-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="de433-106">輸入</span><span class="sxs-lookup"><span data-stu-id="de433-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="de433-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="de433-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="de433-108">要反轉其輸入的作業。</span><span class="sxs-lookup"><span data-stu-id="de433-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-ctl"></a><span data-ttu-id="de433-109">輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="de433-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="de433-110">以位元組由大到小的暫存器形式接受其輸入的新作業。</span><span class="sxs-lookup"><span data-stu-id="de433-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="de433-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="de433-111">See Also</span></span>

- [<span data-ttu-id="de433-112">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="de433-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="de433-113">ReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="de433-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="de433-114">ReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="de433-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="de433-115">ReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="de433-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)