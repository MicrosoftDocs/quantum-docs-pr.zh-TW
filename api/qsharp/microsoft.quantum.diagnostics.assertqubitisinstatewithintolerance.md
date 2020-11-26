---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202204"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="1c0e3-102">AssertQubitIsInStateWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="1c0e3-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="1c0e3-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1c0e3-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1c0e3-105">判斷提示量子位處於預期狀態。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="1c0e3-106">`expected` 表示複雜向量 $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="1c0e3-107">元組的第一個專案代表每一個 $a $，$b $ 是複數的實數部分，而第二個元素則是虛數部分。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="1c0e3-108">最後一個引數定義了判斷提示的容錯。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="1c0e3-109">輸入</span><span class="sxs-lookup"><span data-stu-id="1c0e3-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="1c0e3-110">預期： ([複雜](xref:Microsoft.Quantum.Math.Complex)、[複雜](xref:Microsoft.Quantum.Math.Complex) 的) </span><span class="sxs-lookup"><span data-stu-id="1c0e3-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="1c0e3-111">$ \Ket {0} $ 和 $ \ket $ 應分別有複雜的 amplitudes {1} 。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1c0e3-112">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1c0e3-113">要判斷其狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="1c0e3-114">請注意，此量子位假設為可與其他已配置的量子位，而非纏結。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1c0e3-115">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1c0e3-116">允許實際 amplitudes 偏離預期的加法容錯。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="1c0e3-117">如需詳細資訊，請參閱下面的備註。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c0e3-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c0e3-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1c0e3-119">備註</span><span class="sxs-lookup"><span data-stu-id="1c0e3-119">Remarks</span></span>

<span data-ttu-id="1c0e3-120">下列 Mathematica 程式碼可以用來驗證 mi、mx、my、mz 的運算式：</span><span class="sxs-lookup"><span data-stu-id="1c0e3-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="1c0e3-121">容錯是 \_ 3 維度實數向量 (x ₂的 $L {\infty} $ 距離。 x ₃、x ₄) 由 $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ 和實向量 (y ₂、y ₃、y ₄) 由ρ = Y ₁ I + y ₂ x + y ₃ y + y ₄ Z 定義，其中ρ是與暫存器狀態相對應的密度矩陣。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="1c0e3-122">只有當 Tr (ρ) 和 Tr (| ψ⟩⟨ψ |) 都是 1 (例如 x ₁ = 1/2、y ₁ = 1/2) 。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="1c0e3-123">如果不是這種情況，則函式會判斷 (x ₂-x ₁、x ₃-x ₁、x ₄-x ₁、x ₄ + x ₁) 和 (y ₂-y ₁、y ₃、y ₁ + y ₄) 小於容錯參數的 l ∞距離。</span><span class="sxs-lookup"><span data-stu-id="1c0e3-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>