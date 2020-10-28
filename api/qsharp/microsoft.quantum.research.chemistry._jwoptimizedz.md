---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700898"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="cc00a-102">_JWOptimizedZ 操作</span><span class="sxs-lookup"><span data-stu-id="cc00a-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="cc00a-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="cc00a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="cc00a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc00a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc00a-105">在階段估計中將 Rz 旋轉（具有 C-NOT 技巧）套用至雙階段。</span><span class="sxs-lookup"><span data-stu-id="cc00a-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cc00a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cc00a-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="cc00a-107">角度： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cc00a-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cc00a-108">Rz 旋轉的角度。</span><span class="sxs-lookup"><span data-stu-id="cc00a-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="cc00a-109">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cc00a-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cc00a-110">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="cc00a-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cc00a-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cc00a-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="cc00a-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc00a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

