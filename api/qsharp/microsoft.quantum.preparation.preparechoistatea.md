---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateA
title: PrepareChoiStateA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with an adjoint variant onto given reference and target registers.
ms.openlocfilehash: 58edf63c541cf21961c40e484a89c0e4d584d6af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856909"
---
# <a name="preparechoistatea-operation"></a><span data-ttu-id="c3a3f-102">PrepareChoiStateA 操作</span><span class="sxs-lookup"><span data-stu-id="c3a3f-102">PrepareChoiStateA operation</span></span>

<span data-ttu-id="c3a3f-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c3a3f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c3a3f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3a3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3a3f-105">針對給定的參考和目標暫存器上具有 adjoint 變異的指定作業，準備 Choi 對於– Jamiołkowski 狀態。</span><span class="sxs-lookup"><span data-stu-id="c3a3f-105">Prepares the Choi–Jamiołkowski state for a given operation with an adjoint variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateA (op : (Qubit[] => Unit is Adj), reference : Qubit[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c3a3f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c3a3f-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="c3a3f-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="c3a3f-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="c3a3f-108">參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3a3f-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="c3a3f-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3a3f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="c3a3f-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3a3f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c3a3f-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3a3f-111">See Also</span></span>

- [<span data-ttu-id="c3a3f-112">PrepareChoiState。</span><span class="sxs-lookup"><span data-stu-id="c3a3f-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)