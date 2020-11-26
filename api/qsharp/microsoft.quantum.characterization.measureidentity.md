---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216110"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="1fd1f-102">MeasureIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="1fd1f-102">MeasureIdentity operation</span></span>

<span data-ttu-id="1fd1f-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1fd1f-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1fd1f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fd1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fd1f-105">測量量子位註冊上的身分識別運算子。</span><span class="sxs-lookup"><span data-stu-id="1fd1f-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="1fd1f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1fd1f-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="1fd1f-107">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1fd1f-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1fd1f-108">要測量的註冊。</span><span class="sxs-lookup"><span data-stu-id="1fd1f-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1fd1f-109">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1fd1f-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1fd1f-110">結果值 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="1fd1f-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fd1f-111">備註</span><span class="sxs-lookup"><span data-stu-id="1fd1f-111">Remarks</span></span>

<span data-ttu-id="1fd1f-112">由於 $ \boldone $ 只有 eigenvalue $1 $，而且沒有負 eigenvalue，因此此作業一律 `Zero` 會傳回，對應至 eigenvalue $ + 1 = (-1) ^ $0，而不會造成的狀態折迭 `register` 。</span><span class="sxs-lookup"><span data-stu-id="1fd1f-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="1fd1f-113">這項作業本身本身並沒有用，但在流程 tomography 的內容中很有用，因為它提供了量子進程的追蹤保留相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fd1f-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="1fd1f-114">尤其是具有失真測量的目的電腦，應該將此作業取代為實際的 $ \boldone $ 度量。</span><span class="sxs-lookup"><span data-stu-id="1fd1f-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>