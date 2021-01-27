---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840746"
---
# <a name="cx-operation"></a><span data-ttu-id="150ba-102">CX 操作</span><span class="sxs-lookup"><span data-stu-id="150ba-102">CX operation</span></span>

<span data-ttu-id="150ba-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="150ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="150ba-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="150ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="150ba-105">將受控制 X (CX) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="150ba-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="150ba-106">$ $ \begin{align} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}，$ $，其中資料列和資料行的組織方式與量子概念指南中的組織方式相同。</span><span class="sxs-lookup"><span data-stu-id="150ba-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="150ba-107">輸入</span><span class="sxs-lookup"><span data-stu-id="150ba-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="150ba-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="150ba-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="150ba-109">適用于 CX 閘道的控制量子位。</span><span class="sxs-lookup"><span data-stu-id="150ba-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="150ba-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="150ba-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="150ba-111">CX 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="150ba-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="150ba-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="150ba-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="150ba-113">備註</span><span class="sxs-lookup"><span data-stu-id="150ba-113">Remarks</span></span>

<span data-ttu-id="150ba-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="150ba-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="150ba-115">以及：</span><span class="sxs-lookup"><span data-stu-id="150ba-115">and to:</span></span>

```qsharp
CNOT(control, target);
```