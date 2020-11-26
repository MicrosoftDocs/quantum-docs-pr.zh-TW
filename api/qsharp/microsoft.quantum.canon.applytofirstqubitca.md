---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bc2b1275b4258b9cc2db45c9e5cfe14f7eee0c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208800"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="3898b-102">ApplyToFirstQubitCA 操作</span><span class="sxs-lookup"><span data-stu-id="3898b-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="3898b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3898b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3898b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3898b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3898b-105">將作業操作套用至註冊中的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="3898b-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="3898b-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="3898b-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3898b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="3898b-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="3898b-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="3898b-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3898b-109">要套用至第一個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="3898b-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3898b-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3898b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3898b-111">量子位陣列至套用作業的第一個量子位</span><span class="sxs-lookup"><span data-stu-id="3898b-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3898b-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3898b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3898b-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3898b-113">See Also</span></span>

- [<span data-ttu-id="3898b-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="3898b-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)