---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210432"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="6cced-102">PrepareIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="6cced-102">PrepareIdentity operation</span></span>

<span data-ttu-id="6cced-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6cced-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6cced-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6cced-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6cced-105">在指定暫存器的情況下，以充分混合狀態準備該註冊。</span><span class="sxs-lookup"><span data-stu-id="6cced-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="6cced-106">註冊會在 $ \boldone/2 ^ N $ 狀態中備妥，方法是將完整的 depolarizing 通道套用到每個量子位，其中 $N $ 是註冊的長度。</span><span class="sxs-lookup"><span data-stu-id="6cced-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6cced-107">輸入</span><span class="sxs-lookup"><span data-stu-id="6cced-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="6cced-108">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6cced-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6cced-109">要以上述方式 depolarized 其狀態的註冊。</span><span class="sxs-lookup"><span data-stu-id="6cced-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6cced-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cced-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6cced-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6cced-111">See Also</span></span>

- [<span data-ttu-id="6cced-112">PrepareSingleQubitIdentity。</span><span class="sxs-lookup"><span data-stu-id="6cced-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)