---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827700"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="99ba4-102">ApplyBitFlipEncoder 操作</span><span class="sxs-lookup"><span data-stu-id="99ba4-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="99ba4-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="99ba4-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="99ba4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99ba4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99ba4-105">私用作業，用來同時執行位翻轉編碼器和解碼器。</span><span class="sxs-lookup"><span data-stu-id="99ba4-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="99ba4-106">請注意，此編碼器可利用就地連貫的復原，在這種情況下，它會「造成」的初始狀態所描述的錯誤 `auxQubits` 。</span><span class="sxs-lookup"><span data-stu-id="99ba4-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="99ba4-107">尤其是，如果 `auxQubits` 最初是在 state $ \ket {10} $ 中，這會導致在編碼的量子位上 $X _1 $ error。</span><span class="sxs-lookup"><span data-stu-id="99ba4-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="99ba4-108">輸入</span><span class="sxs-lookup"><span data-stu-id="99ba4-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="99ba4-109">coherentRecovery： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="99ba4-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="99ba4-110">data： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="99ba4-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="99ba4-111">臨時： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="99ba4-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="99ba4-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99ba4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="99ba4-113">參考資料</span><span class="sxs-lookup"><span data-stu-id="99ba4-113">References</span></span>

- <span data-ttu-id="99ba4-114">doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="99ba4-114">doi:10.1103/PhysRevA.85.044302</span></span>