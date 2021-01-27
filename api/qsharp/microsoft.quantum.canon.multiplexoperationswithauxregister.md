---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: MultiplexOperationsWithAuxRegister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 91db22d6261709c1c3506c80ff600c904748575a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852468"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="b6279-102">MultiplexOperationsWithAuxRegister 操作</span><span class="sxs-lookup"><span data-stu-id="b6279-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="b6279-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b6279-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b6279-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6279-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6279-105">MultiplexOperations 的執行步驟。</span><span class="sxs-lookup"><span data-stu-id="b6279-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b6279-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b6279-106">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="b6279-107">unitaries： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="b6279-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="b6279-108">auxillaryRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6279-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="b6279-109">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6279-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="b6279-110">目標： t</span><span class="sxs-lookup"><span data-stu-id="b6279-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b6279-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6279-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b6279-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="b6279-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6279-113">不要</span><span class="sxs-lookup"><span data-stu-id="b6279-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="b6279-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b6279-114">See Also</span></span>

- [<span data-ttu-id="b6279-115">Canon. MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="b6279-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)