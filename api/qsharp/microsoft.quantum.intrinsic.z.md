---
uid: Microsoft.Quantum.Intrinsic.Z
title: Z 運算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Z
qsharp.summary: >-
  Applies the Pauli $Z$ gate.

  \begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 02c7cb4dfd13fb5be12e81188b4f388b70fb3241
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817303"
---
# <a name="z-operation"></a><span data-ttu-id="8dbd8-102">Z 運算</span><span class="sxs-lookup"><span data-stu-id="8dbd8-102">Z operation</span></span>

<span data-ttu-id="8dbd8-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8dbd8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8dbd8-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8dbd8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8dbd8-105">套用 Pauli $Z $ 閘道。</span><span class="sxs-lookup"><span data-stu-id="8dbd8-105">Applies the Pauli $Z$ gate.</span></span>

<span data-ttu-id="8dbd8-106">\begin{align} \ sigma_z \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="8dbd8-106">\begin{align} \sigma_z \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="8dbd8-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8dbd8-107">\end{align}</span></span>

```qsharp
operation Z (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8dbd8-108">輸入</span><span class="sxs-lookup"><span data-stu-id="8dbd8-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="8dbd8-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8dbd8-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8dbd8-110">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="8dbd8-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8dbd8-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8dbd8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

