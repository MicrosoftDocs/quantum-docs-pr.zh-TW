---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219357"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="2cedc-102">ApplyAndChain 操作</span><span class="sxs-lookup"><span data-stu-id="2cedc-102">ApplyAndChain operation</span></span>

<span data-ttu-id="2cedc-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2cedc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2cedc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cedc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cedc-105">計算一鏈和閘道</span><span class="sxs-lookup"><span data-stu-id="2cedc-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="2cedc-106">描述</span><span class="sxs-lookup"><span data-stu-id="2cedc-106">Description</span></span>

<span data-ttu-id="2cedc-107">要計算暫存結果的輔助量子位必須明確指定。</span><span class="sxs-lookup"><span data-stu-id="2cedc-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="2cedc-108">`Length(ctrlRegister) - 2`如果至少有兩個控制項，則該註冊的長度為，否則長度為0。</span><span class="sxs-lookup"><span data-stu-id="2cedc-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="2cedc-109">輸入</span><span class="sxs-lookup"><span data-stu-id="2cedc-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="2cedc-110">auxRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2cedc-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="2cedc-111">ctrlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2cedc-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="2cedc-112">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2cedc-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="2cedc-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cedc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
