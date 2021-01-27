---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852333"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="b4435-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="b4435-102">PermuteQubits operation</span></span>

<span data-ttu-id="b4435-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b4435-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b4435-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4435-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4435-105">使用交換操作來 Permutes 量子位。</span><span class="sxs-lookup"><span data-stu-id="b4435-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b4435-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b4435-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="b4435-107">順序： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b4435-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b4435-108">描述量子位的新順序，其中量子位 at index 現在會依序為 [i]。</span><span class="sxs-lookup"><span data-stu-id="b4435-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b4435-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b4435-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b4435-110">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="b4435-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4435-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4435-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="b4435-112">範例</span><span class="sxs-lookup"><span data-stu-id="b4435-112">Example</span></span>

<span data-ttu-id="b4435-113">給定順序 = [2，1，0]，並註冊 $ \ket{\ Alpha_0} \ket{\ Alpha_1} \ket{\ Alpha_2} $，PermuteQubits 將註冊變更為 $ \ket{\ Alpha_2} \ket{\ Alpha_1} \ket{\ Alpha_0} $</span><span class="sxs-lookup"><span data-stu-id="b4435-113">Given ordering = [2, 1, 0] and register $\ket{\alpha_0} \ket{\alpha_1} \ket{\alpha_2}$, PermuteQubits changes the register into $\ket{\alpha_2} \ket{\alpha_1} \ket{\alpha_0}$</span></span>

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```