---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: 8a57c60ac1df8f6e94b58acf7183c47f395d291a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700331"
---
# <a name="s-operation"></a><span data-ttu-id="c0ac6-102">S 操作</span><span class="sxs-lookup"><span data-stu-id="c0ac6-102">S operation</span></span>

<span data-ttu-id="c0ac6-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c0ac6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c0ac6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0ac6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0ac6-105">將 S 閘道套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="c0ac6-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="c0ac6-106">描述</span><span class="sxs-lookup"><span data-stu-id="c0ac6-106">Description</span></span>

<span data-ttu-id="c0ac6-107">這項作業可由單一矩陣 \begin{align} S \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="c0ac6-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="c0ac6-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c0ac6-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="c0ac6-109">輸入</span><span class="sxs-lookup"><span data-stu-id="c0ac6-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="c0ac6-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0ac6-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c0ac6-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="c0ac6-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0ac6-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0ac6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

