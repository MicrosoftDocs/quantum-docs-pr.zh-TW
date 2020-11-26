---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192480"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="0b9c4-102">QuantumWalkByQubitization 函式</span><span class="sxs-lookup"><span data-stu-id="0b9c4-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="0b9c4-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0b9c4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0b9c4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b9c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b9c4-105">將區塊編碼反映轉換成量子逐步解說。</span><span class="sxs-lookup"><span data-stu-id="0b9c4-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="0b9c4-106">描述</span><span class="sxs-lookup"><span data-stu-id="0b9c4-106">Description</span></span>

<span data-ttu-id="0b9c4-107">假設有一個 `BlockEncodingReflection` 由單一 $U $ 將某些運算子編碼 $H $，則會將它轉換成量子逐步解說 $W $ 包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的範圍。</span><span class="sxs-lookup"><span data-stu-id="0b9c4-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="0b9c4-108">輸入</span><span class="sxs-lookup"><span data-stu-id="0b9c4-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="0b9c4-109">blockEncoding： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="0b9c4-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="0b9c4-110">`BlockEncodingReflection`單一 $U $，以轉換成量子引導。</span><span class="sxs-lookup"><span data-stu-id="0b9c4-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="0b9c4-111">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0b9c4-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0b9c4-112">量子逐步解說 $W $ 可共同處理暫存器 `a` ，並 `s` 將 $H $ 的區塊編碼，並包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的範圍。</span><span class="sxs-lookup"><span data-stu-id="0b9c4-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="0b9c4-113">參考</span><span class="sxs-lookup"><span data-stu-id="0b9c4-113">References</span></span>

- <span data-ttu-id="0b9c4-114">Hamiltonian 模擬，量子位化 Guang Hao Low，Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="0b9c4-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="0b9c4-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0b9c4-115">See Also</span></span>

- [<span data-ttu-id="0b9c4-116">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="0b9c4-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="0b9c4-117">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="0b9c4-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)