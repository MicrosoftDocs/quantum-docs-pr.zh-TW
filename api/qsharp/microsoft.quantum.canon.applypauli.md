---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844745"
---
# <a name="applypauli-operation"></a><span data-ttu-id="b72b0-102">ApplyPauli 操作</span><span class="sxs-lookup"><span data-stu-id="b72b0-102">ApplyPauli operation</span></span>

<span data-ttu-id="b72b0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b72b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b72b0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b72b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b72b0-105">假設有多量子位 Pauli 運算子，請將對應的作業套用至暫存器。</span><span class="sxs-lookup"><span data-stu-id="b72b0-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b72b0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b72b0-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="b72b0-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b72b0-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="b72b0-108">多量子位的 Pauli 運算子，以單一量子位 Pauli 運算子的陣列表示。</span><span class="sxs-lookup"><span data-stu-id="b72b0-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b72b0-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b72b0-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b72b0-110">註冊以在上套用指定的 Pauli 作業。</span><span class="sxs-lookup"><span data-stu-id="b72b0-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b72b0-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b72b0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="b72b0-112">範例</span><span class="sxs-lookup"><span data-stu-id="b72b0-112">Example</span></span>

<span data-ttu-id="b72b0-113">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="b72b0-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="b72b0-114">及</span><span class="sxs-lookup"><span data-stu-id="b72b0-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```