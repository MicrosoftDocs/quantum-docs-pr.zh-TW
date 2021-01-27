---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855880"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="aa58d-102">PrepareIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="aa58d-102">PrepareIdentity operation</span></span>

<span data-ttu-id="aa58d-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="aa58d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="aa58d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa58d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa58d-105">在指定暫存器的情況下，以充分混合狀態準備該註冊。</span><span class="sxs-lookup"><span data-stu-id="aa58d-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="aa58d-106">註冊會在 $ \boldone/2 ^ N $ 狀態中備妥，方法是將完整的 depolarizing 通道套用到每個量子位，其中 $N $ 是註冊的長度。</span><span class="sxs-lookup"><span data-stu-id="aa58d-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="aa58d-107">輸入</span><span class="sxs-lookup"><span data-stu-id="aa58d-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="aa58d-108">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa58d-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa58d-109">要以上述方式 depolarized 其狀態的註冊。</span><span class="sxs-lookup"><span data-stu-id="aa58d-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa58d-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa58d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="aa58d-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aa58d-111">See Also</span></span>

- [<span data-ttu-id="aa58d-112">PrepareSingleQubitIdentity。</span><span class="sxs-lookup"><span data-stu-id="aa58d-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)