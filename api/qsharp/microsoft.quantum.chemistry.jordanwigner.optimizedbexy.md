---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 28a7c7877a3d48fd5ba50384d7996017e7cdb14f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837254"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="492ed-102">OptimizedBEXY 操作</span><span class="sxs-lookup"><span data-stu-id="492ed-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="492ed-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="492ed-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="492ed-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="492ed-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="492ed-105">單一 $U $，其會將 Pauli 字串套用至 $ (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1} .。。Z_0 $ on 量子位 $ 0. p $ 條件的索引 $z \in \{ 0、1 \} $ 和 $p $。</span><span class="sxs-lookup"><span data-stu-id="492ed-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="492ed-106">亦即 $ $ \begin{align} U\ket {z} \ ket {p} \ ket {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1} .。。Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="492ed-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="492ed-107">輸入</span><span class="sxs-lookup"><span data-stu-id="492ed-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="492ed-108">pauliBasis： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="492ed-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="492ed-109">當此量子位處於狀態 $ \ket {0} $ 時，就會套用 $X $。</span><span class="sxs-lookup"><span data-stu-id="492ed-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="492ed-110">當其處於狀態 $ \ket {1} $ 時，就會套用 $Y $。</span><span class="sxs-lookup"><span data-stu-id="492ed-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="492ed-111">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="492ed-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="492ed-112">此註冊的狀態 $ \ket{p} $ 會決定套用 $X $ 或 $Y $ 的量子位。</span><span class="sxs-lookup"><span data-stu-id="492ed-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="492ed-113">targetRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="492ed-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="492ed-114">註冊已套用 Pauli 運算子的量子位。</span><span class="sxs-lookup"><span data-stu-id="492ed-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="492ed-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="492ed-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="492ed-116">參考資料</span><span class="sxs-lookup"><span data-stu-id="492ed-116">References</span></span>

- <span data-ttu-id="492ed-117">使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="492ed-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>