---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698022"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="81210-102">ApplyBitFlipEncoder 操作</span><span class="sxs-lookup"><span data-stu-id="81210-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="81210-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="81210-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="81210-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81210-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81210-105">私用作業，用來同時執行位翻轉編碼器和解碼器。</span><span class="sxs-lookup"><span data-stu-id="81210-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="81210-106">請注意，此編碼器可利用就地連貫的復原，在這種情況下，它會「造成」的初始狀態所描述的錯誤 `auxQubits` 。</span><span class="sxs-lookup"><span data-stu-id="81210-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="81210-107">尤其是，如果 `auxQubits` 最初是在 state $ \ket {10} $ 中，這會導致在編碼的量子位上 $X _1 $ error。</span><span class="sxs-lookup"><span data-stu-id="81210-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="81210-108">輸入</span><span class="sxs-lookup"><span data-stu-id="81210-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="81210-109">coherentRecovery： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81210-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="81210-110">data： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81210-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="81210-111">臨時： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81210-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="81210-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81210-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="81210-113">參考</span><span class="sxs-lookup"><span data-stu-id="81210-113">References</span></span>

- <span data-ttu-id="81210-114">doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="81210-114">doi:10.1103/PhysRevA.85.044302</span></span>