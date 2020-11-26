---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: PrepareChoiStateC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: 7d9e53b1dd8ec08c0d0b200cc51562ca6330b06e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210534"
---
# <a name="preparechoistatec-operation"></a><span data-ttu-id="de6c4-102">PrepareChoiStateC 操作</span><span class="sxs-lookup"><span data-stu-id="de6c4-102">PrepareChoiStateC operation</span></span>

<span data-ttu-id="de6c4-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="de6c4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="de6c4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de6c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de6c4-105">使用受控制的變異數，針對指定的參考和目標暫存器，準備 Choi 對於– Jamiołkowski 狀態。</span><span class="sxs-lookup"><span data-stu-id="de6c4-105">Prepares the Choi–Jamiołkowski state for a given operation with a controlled variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="de6c4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="de6c4-106">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="de6c4-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="de6c4-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="de6c4-108">參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="de6c4-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="de6c4-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="de6c4-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="de6c4-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de6c4-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="de6c4-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="de6c4-111">See Also</span></span>

- [<span data-ttu-id="de6c4-112">PrepareChoiState。</span><span class="sxs-lookup"><span data-stu-id="de6c4-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)