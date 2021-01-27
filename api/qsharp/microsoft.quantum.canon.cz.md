---
uid: Microsoft.Quantum.Canon.CZ
title: CZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840694"
---
# <a name="cz-operation"></a><span data-ttu-id="f5672-102">CZ 操作</span><span class="sxs-lookup"><span data-stu-id="f5672-102">CZ operation</span></span>

<span data-ttu-id="f5672-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f5672-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f5672-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5672-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5672-105">將控制的 Z (CZ) 閘道套用至一對量子位。</span><span class="sxs-lookup"><span data-stu-id="f5672-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="f5672-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}，$ $，其中資料列和資料行的組織方式如量子概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="f5672-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f5672-107">輸入</span><span class="sxs-lookup"><span data-stu-id="f5672-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="f5672-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f5672-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f5672-109">CZ 閘道的控制項量子位。</span><span class="sxs-lookup"><span data-stu-id="f5672-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f5672-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f5672-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f5672-111">CZ 閘道的目標量子位。</span><span class="sxs-lookup"><span data-stu-id="f5672-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5672-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5672-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f5672-113">備註</span><span class="sxs-lookup"><span data-stu-id="f5672-113">Remarks</span></span>

<span data-ttu-id="f5672-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="f5672-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```