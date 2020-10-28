---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700971"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="42de0-102">PrepareIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="42de0-102">PrepareIdentity operation</span></span>

<span data-ttu-id="42de0-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="42de0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="42de0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42de0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42de0-105">在指定暫存器的情況下，以充分混合狀態準備該註冊。</span><span class="sxs-lookup"><span data-stu-id="42de0-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="42de0-106">註冊會在 $ \boldone/2 ^ N $ 狀態中備妥，方法是將完整的 depolarizing 通道套用到每個量子位，其中 $N $ 是註冊的長度。</span><span class="sxs-lookup"><span data-stu-id="42de0-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="42de0-107">輸入</span><span class="sxs-lookup"><span data-stu-id="42de0-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="42de0-108">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="42de0-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="42de0-109">要以上述方式 depolarized 其狀態的註冊。</span><span class="sxs-lookup"><span data-stu-id="42de0-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42de0-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42de0-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="42de0-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42de0-111">See Also</span></span>

- [<span data-ttu-id="42de0-112">PrepareSingleQubitIdentity。</span><span class="sxs-lookup"><span data-stu-id="42de0-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)