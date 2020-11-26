---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: MultiplexOperationsWithAuxRegister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 530e78ba0c5ce6e0627177527daf2ccc56f537eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205978"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="456ce-102">MultiplexOperationsWithAuxRegister 操作</span><span class="sxs-lookup"><span data-stu-id="456ce-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="456ce-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="456ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="456ce-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="456ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="456ce-105">MultiplexOperations 的執行步驟。</span><span class="sxs-lookup"><span data-stu-id="456ce-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="456ce-106">輸入</span><span class="sxs-lookup"><span data-stu-id="456ce-106">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="456ce-107">unitaries： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="456ce-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="456ce-108">auxillaryRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="456ce-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="456ce-109">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="456ce-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="456ce-110">目標： t</span><span class="sxs-lookup"><span data-stu-id="456ce-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="456ce-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="456ce-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="456ce-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="456ce-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="456ce-113">不要</span><span class="sxs-lookup"><span data-stu-id="456ce-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="456ce-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="456ce-114">See Also</span></span>

- [<span data-ttu-id="456ce-115">Canon. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="456ce-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)