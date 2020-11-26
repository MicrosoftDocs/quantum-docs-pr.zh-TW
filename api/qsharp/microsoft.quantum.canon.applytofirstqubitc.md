---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2659c3a97baa68cb4c1d7781381f89742902594d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217504"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="cf2bc-102">ApplyToFirstQubitC 操作</span><span class="sxs-lookup"><span data-stu-id="cf2bc-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="cf2bc-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf2bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf2bc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf2bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cf2bc-105">將作業操作套用至註冊中的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="cf2bc-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="cf2bc-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="cf2bc-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="cf2bc-107">輸入</span><span class="sxs-lookup"><span data-stu-id="cf2bc-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="cf2bc-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="cf2bc-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cf2bc-109">要套用至第一個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="cf2bc-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="cf2bc-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cf2bc-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cf2bc-111">量子位陣列至套用作業的第一個量子位</span><span class="sxs-lookup"><span data-stu-id="cf2bc-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf2bc-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf2bc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cf2bc-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf2bc-113">See Also</span></span>

- [<span data-ttu-id="cf2bc-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="cf2bc-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)