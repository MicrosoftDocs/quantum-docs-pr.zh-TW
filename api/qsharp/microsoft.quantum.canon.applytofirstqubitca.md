---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699195"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="c6162-102">ApplyToFirstQubitCA 操作</span><span class="sxs-lookup"><span data-stu-id="c6162-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="c6162-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6162-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6162-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6162-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6162-105">將作業操作套用至註冊中的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="c6162-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="c6162-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="c6162-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c6162-107">輸入</span><span class="sxs-lookup"><span data-stu-id="c6162-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="c6162-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c6162-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c6162-109">要套用至第一個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="c6162-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c6162-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c6162-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c6162-111">量子位陣列至套用作業的第一個量子位</span><span class="sxs-lookup"><span data-stu-id="c6162-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6162-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6162-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c6162-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6162-113">See Also</span></span>

- [<span data-ttu-id="c6162-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="c6162-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)