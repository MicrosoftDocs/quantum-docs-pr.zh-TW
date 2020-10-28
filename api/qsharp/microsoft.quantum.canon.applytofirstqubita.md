---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699196"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="7938e-102">ApplyToFirstQubitA 操作</span><span class="sxs-lookup"><span data-stu-id="7938e-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="7938e-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7938e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7938e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7938e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7938e-105">將作業套用至註冊中的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="7938e-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="7938e-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="7938e-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7938e-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7938e-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="7938e-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="7938e-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7938e-109">要套用至第一個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="7938e-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="7938e-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7938e-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7938e-111">量子位陣列至套用作業的第一個量子位</span><span class="sxs-lookup"><span data-stu-id="7938e-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="7938e-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7938e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7938e-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7938e-113">See Also</span></span>

- [<span data-ttu-id="7938e-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="7938e-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)