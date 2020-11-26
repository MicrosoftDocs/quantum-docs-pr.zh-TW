---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 9b17bac9d95baf5a542604892c64130bf35d7f69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202425"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="393a8-102">AssertOperationsEqualInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="393a8-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="393a8-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="393a8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="393a8-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="393a8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="393a8-105">假設有兩個作業，請判斷它們對所有輸入狀態的作用都相同。</span><span class="sxs-lookup"><span data-stu-id="393a8-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="393a8-106">此判斷提示是藉由檢查所有狀態的作業動作（$V _0 \otimes ... \otimes V_ {n-1} $）來執行，其中 $V _k $ 是其中一個狀態 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $ 和 $ \ket{i} $ (+ 1 Eigenstate Of Pauli Y 運算子) 。</span><span class="sxs-lookup"><span data-stu-id="393a8-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="393a8-107">此判斷提示會使用 $n $ 量子位，而且需要比較多個呼叫作業。</span><span class="sxs-lookup"><span data-stu-id="393a8-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="393a8-108">輸入</span><span class="sxs-lookup"><span data-stu-id="393a8-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="393a8-109">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="393a8-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="393a8-110">作業和操作的量子位 $n $ 數目 `givenU` `expectedU` 。</span><span class="sxs-lookup"><span data-stu-id="393a8-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="393a8-111">givenU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="393a8-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="393a8-112">要檢查 $n $ 量子位上的作業。</span><span class="sxs-lookup"><span data-stu-id="393a8-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="393a8-113">expectedU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="393a8-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="393a8-114">要與之比較 $n $ 量子位上的參考作業 `givenU` 。</span><span class="sxs-lookup"><span data-stu-id="393a8-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="393a8-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="393a8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="393a8-116">參考</span><span class="sxs-lookup"><span data-stu-id="393a8-116">References</span></span>

<span data-ttu-id="393a8-117">狀態 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $ 和 $ \ket{i} $ 的基礎是 Chuang-Nielsen 基礎，如、Chuang [ *、Nielsen*](https://arxiv.org/abs/quant-ph/9610001)。</span><span class="sxs-lookup"><span data-stu-id="393a8-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="393a8-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="393a8-118">See Also</span></span>

- [<span data-ttu-id="393a8-119">AssertOperationsEqualReferenced。</span><span class="sxs-lookup"><span data-stu-id="393a8-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)