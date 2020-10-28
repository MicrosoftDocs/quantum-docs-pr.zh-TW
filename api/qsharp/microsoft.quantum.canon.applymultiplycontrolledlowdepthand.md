---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699274"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="9a98c-102">ApplyMultiplyControlledLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="9a98c-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="9a98c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a98c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a98c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a98c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a98c-105">假設目標量子位已初始化為0，則會執行多個控制的 Toffoli 閘道。</span><span class="sxs-lookup"><span data-stu-id="9a98c-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="9a98c-106">Adjoint 作業會假設目標量子位將重設為0。</span><span class="sxs-lookup"><span data-stu-id="9a98c-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="9a98c-107">需要 Rz 深度為1，而協助程式量子位的數目是量子位數目的指數。</span><span class="sxs-lookup"><span data-stu-id="9a98c-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9a98c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="9a98c-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="9a98c-109">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9a98c-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9a98c-110">控制項量子位</span><span class="sxs-lookup"><span data-stu-id="9a98c-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9a98c-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9a98c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9a98c-112">目標量子位</span><span class="sxs-lookup"><span data-stu-id="9a98c-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a98c-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a98c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

