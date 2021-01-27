---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a36d20e03ebed82435d1d4136f4ce777eb468926
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850705"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="867ab-102">ApplyToFirstQubitC 操作</span><span class="sxs-lookup"><span data-stu-id="867ab-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="867ab-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="867ab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="867ab-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="867ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="867ab-105">將作業操作套用至註冊中的第一個量子位。</span><span class="sxs-lookup"><span data-stu-id="867ab-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="867ab-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="867ab-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="867ab-107">輸入</span><span class="sxs-lookup"><span data-stu-id="867ab-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="867ab-108">op： [量子位](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="867ab-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="867ab-109">要套用至第一個量子位的作業</span><span class="sxs-lookup"><span data-stu-id="867ab-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="867ab-110">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="867ab-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="867ab-111">量子位陣列至套用作業的第一個量子位</span><span class="sxs-lookup"><span data-stu-id="867ab-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="867ab-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="867ab-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="867ab-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="867ab-113">See Also</span></span>

- [<span data-ttu-id="867ab-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="867ab-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)