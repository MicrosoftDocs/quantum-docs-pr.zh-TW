---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: PrepareChoiStateC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: b23b22fa4bf21ca48076ccda0db62b313f887aa9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700974"
---
# <a name="preparechoistatec-operation"></a><span data-ttu-id="013b5-102">PrepareChoiStateC 操作</span><span class="sxs-lookup"><span data-stu-id="013b5-102">PrepareChoiStateC operation</span></span>

<span data-ttu-id="013b5-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="013b5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="013b5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="013b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="013b5-105">使用受控制的變異數，針對指定的參考和目標暫存器，準備 Choi 對於– Jamiłkowski 狀態。</span><span class="sxs-lookup"><span data-stu-id="013b5-105">Prepares the Choi–Jamiłkowski state for a given operation with a controlled variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="013b5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="013b5-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="013b5-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="013b5-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="013b5-108">參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="013b5-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="013b5-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="013b5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="013b5-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="013b5-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="013b5-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="013b5-111">See Also</span></span>

- [<span data-ttu-id="013b5-112">PrepareChoiState。</span><span class="sxs-lookup"><span data-stu-id="013b5-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)