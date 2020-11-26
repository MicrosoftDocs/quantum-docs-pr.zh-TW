---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218388"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="41428-102">ApplyMultiplyControlledAnd 操作</span><span class="sxs-lookup"><span data-stu-id="41428-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="41428-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41428-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41428-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41428-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41428-105">假設目標量子位已初始化為0，則會執行多個控制的 Toffoli 閘道。</span><span class="sxs-lookup"><span data-stu-id="41428-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="41428-106">Adjoint 作業會假設目標量子位將重設為0。</span><span class="sxs-lookup"><span data-stu-id="41428-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="41428-107">輸入</span><span class="sxs-lookup"><span data-stu-id="41428-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="41428-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="41428-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="41428-109">控制項量子位</span><span class="sxs-lookup"><span data-stu-id="41428-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="41428-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="41428-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="41428-111">目標量子位</span><span class="sxs-lookup"><span data-stu-id="41428-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="41428-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41428-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

