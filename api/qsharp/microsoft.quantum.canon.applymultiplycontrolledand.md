---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844848"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="28472-102">ApplyMultiplyControlledAnd 操作</span><span class="sxs-lookup"><span data-stu-id="28472-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="28472-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28472-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28472-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28472-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28472-105">假設目標量子位已初始化為0，則會執行多個控制的 Toffoli 閘道。</span><span class="sxs-lookup"><span data-stu-id="28472-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="28472-106">Adjoint 作業會假設目標量子位將重設為0。</span><span class="sxs-lookup"><span data-stu-id="28472-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="28472-107">輸入</span><span class="sxs-lookup"><span data-stu-id="28472-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="28472-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="28472-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="28472-109">控制項量子位</span><span class="sxs-lookup"><span data-stu-id="28472-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="28472-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="28472-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="28472-111">目標量子位</span><span class="sxs-lookup"><span data-stu-id="28472-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="28472-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28472-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

