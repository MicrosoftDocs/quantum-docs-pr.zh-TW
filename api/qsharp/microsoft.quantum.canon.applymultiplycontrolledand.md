---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699275"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="eb716-102">ApplyMultiplyControlledAnd 操作</span><span class="sxs-lookup"><span data-stu-id="eb716-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="eb716-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb716-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb716-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb716-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb716-105">假設目標量子位已初始化為0，則會執行多個控制的 Toffoli 閘道。</span><span class="sxs-lookup"><span data-stu-id="eb716-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="eb716-106">Adjoint 作業會假設目標量子位將重設為0。</span><span class="sxs-lookup"><span data-stu-id="eb716-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="eb716-107">輸入</span><span class="sxs-lookup"><span data-stu-id="eb716-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="eb716-108">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eb716-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eb716-109">控制項量子位</span><span class="sxs-lookup"><span data-stu-id="eb716-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="eb716-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb716-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb716-111">目標量子位</span><span class="sxs-lookup"><span data-stu-id="eb716-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb716-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb716-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

