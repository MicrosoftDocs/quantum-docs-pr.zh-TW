---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 99439229e2c3d5a10073669cf1e742f6de3d7618
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699199"
---
# <a name="applytofirstqubit-operation"></a><span data-ttu-id="3e23a-102">ApplyToFirstQubit 操作</span><span class="sxs-lookup"><span data-stu-id="3e23a-102">ApplyToFirstQubit operation</span></span>

<span data-ttu-id="3e23a-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e23a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e23a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e23a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e23a-105">將作業套用至註冊中的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="3e23a-105">Applies an operation to the first qubit in the register.</span></span>

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3e23a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3e23a-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="3e23a-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e23a-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3e23a-108">要套用至第一個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="3e23a-108">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3e23a-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e23a-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e23a-110">量子位陣列至套用作業的第一個量子位</span><span class="sxs-lookup"><span data-stu-id="3e23a-110">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e23a-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e23a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3e23a-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3e23a-112">See Also</span></span>

- [<span data-ttu-id="3e23a-113">Canon. ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="3e23a-113">Microsoft.Quantum.Canon.ApplyToFirstQubitA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [<span data-ttu-id="3e23a-114">Canon. ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="3e23a-114">Microsoft.Quantum.Canon.ApplyToFirstQubitC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [<span data-ttu-id="3e23a-115">Canon. ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="3e23a-115">Microsoft.Quantum.Canon.ApplyToFirstQubitCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)