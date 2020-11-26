---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207236"
---
# <a name="cx-operation"></a><span data-ttu-id="c6903-102">CX 操作</span><span class="sxs-lookup"><span data-stu-id="c6903-102">CX operation</span></span>

<span data-ttu-id="c6903-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6903-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6903-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6903-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6903-105">將受控制 X (CX) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="c6903-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="c6903-106">$ $ \begin{align} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}，$ $，其中資料列和資料行的組織方式與量子概念指南中的組織方式相同。</span><span class="sxs-lookup"><span data-stu-id="c6903-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c6903-107">輸入</span><span class="sxs-lookup"><span data-stu-id="c6903-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="c6903-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6903-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6903-109">適用于 CX 閘道的控制量子位。</span><span class="sxs-lookup"><span data-stu-id="c6903-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c6903-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6903-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6903-111">CX 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="c6903-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6903-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6903-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c6903-113">備註</span><span class="sxs-lookup"><span data-stu-id="c6903-113">Remarks</span></span>

<span data-ttu-id="c6903-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="c6903-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="c6903-115">以及：</span><span class="sxs-lookup"><span data-stu-id="c6903-115">and to:</span></span>

```qsharp
CNOT(control, target);
```