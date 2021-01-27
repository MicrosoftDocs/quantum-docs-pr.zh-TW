---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853108"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="c13ea-102">KnillDistill 操作</span><span class="sxs-lookup"><span data-stu-id="c13ea-102">KnillDistill operation</span></span>

<span data-ttu-id="c13ea-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c13ea-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c13ea-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c13ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c13ea-105">實行 Knill 魔術 state 公司演算法。</span><span class="sxs-lookup"><span data-stu-id="c13ea-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="c13ea-106">描述</span><span class="sxs-lookup"><span data-stu-id="c13ea-106">Description</span></span>

<span data-ttu-id="c13ea-107">假設有15份魔術州 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket \end{align} 的複本 {1} ，$ $ 會產生一個較高品質的複本。</span><span class="sxs-lookup"><span data-stu-id="c13ea-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="c13ea-108">輸入</span><span class="sxs-lookup"><span data-stu-id="c13ea-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="c13ea-109">roughMagic： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c13ea-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c13ea-110">有十五個量子位的暫存器，其中包含魔術州的大約複本。</span><span class="sxs-lookup"><span data-stu-id="c13ea-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="c13ea-111">在此公司程式的應用程式中， `roughMagic[0]` 將會包含一個較高品質的複製，而且註冊程式的其餘部分將會重設為 $ \ket{00\cdots 0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="c13ea-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c13ea-112">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c13ea-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c13ea-113">如果為 `true` ，則程式會成功，且應接受較高品質的複製。</span><span class="sxs-lookup"><span data-stu-id="c13ea-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="c13ea-114">如果為 `false` ，則程式失敗，且暫存器的狀態應視為未定義。</span><span class="sxs-lookup"><span data-stu-id="c13ea-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="c13ea-115">備註</span><span class="sxs-lookup"><span data-stu-id="c13ea-115">Remarks</span></span>

<span data-ttu-id="c13ea-116">我們遵循 Knill 演算法。</span><span class="sxs-lookup"><span data-stu-id="c13ea-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="c13ea-117">不過，目前的執行方式不太理想，因為它使用太多量子位。</span><span class="sxs-lookup"><span data-stu-id="c13ea-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="c13ea-118">魔術狀態會插入此常式中，在此情況下會有更好的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="c13ea-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="c13ea-119">參考資料</span><span class="sxs-lookup"><span data-stu-id="c13ea-119">References</span></span>

- [<span data-ttu-id="c13ea-120">Knill</span><span class="sxs-lookup"><span data-stu-id="c13ea-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)