---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: MultiplexerBruteForceFromGenerator 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: d3606ff4f45765fd3aaf1e6a3078288b214349d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852558"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a><span data-ttu-id="4a6d7-102">MultiplexerBruteForceFromGenerator 函式</span><span class="sxs-lookup"><span data-stu-id="4a6d7-102">MultiplexerBruteForceFromGenerator function</span></span>

<span data-ttu-id="4a6d7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a6d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a6d7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a6d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a6d7-105">傳回 $U $ 的乘法控制項單一作業，此作業會在由 n-量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="4a6d7-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="4a6d7-106">$U = \sum ^ {2 ^ n-1-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="4a6d7-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4a6d7-107">輸入</span><span class="sxs-lookup"><span data-stu-id="4a6d7-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a><span data-ttu-id="4a6d7-108">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="4a6d7-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="4a6d7-109">元組，其中第一個專案 `Int` 是 unitaries $N $ 的數目，而第二個元素 `(Int -> ('T => () is Adj + Ctl))` 是採用整數 $j $ in $ [0，n-1] $ 的函式，並輸出單一作業 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="4a6d7-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="4a6d7-110">Output： ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4a6d7-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4a6d7-111">$U $ 的乘法受控制的單一作業，套用所描述的 unitaries `unitaryGenerator` 。</span><span class="sxs-lookup"><span data-stu-id="4a6d7-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a6d7-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4a6d7-112">See Also</span></span>

- [<span data-ttu-id="4a6d7-113">Canon. MultiplexerBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="4a6d7-113">Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)