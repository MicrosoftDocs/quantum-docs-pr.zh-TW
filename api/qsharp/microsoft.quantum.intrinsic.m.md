---
uid: Microsoft.Quantum.Intrinsic.M
title: M 運算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699806"
---
# <a name="m-operation"></a><span data-ttu-id="1e7f4-102">M 運算</span><span class="sxs-lookup"><span data-stu-id="1e7f4-102">M operation</span></span>

<span data-ttu-id="1e7f4-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1e7f4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1e7f4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e7f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e7f4-105">以 Pauli $Z $ 基礎來測量單一量子位。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="1e7f4-106">輸出結果是由散發 \begin{align} \Pr ( \texttt{Zero} 所提供 |\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="1e7f4-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="1e7f4-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="1e7f4-108">輸入</span><span class="sxs-lookup"><span data-stu-id="1e7f4-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="1e7f4-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1e7f4-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1e7f4-110">要測量的量子位。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1e7f4-111">輸出： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1e7f4-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1e7f4-112">`Zero` 如果觀察到 $ + $1 eigenvalue，以及 `One` 是否觀察到 $-$1 eigenvalue。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e7f4-113">備註</span><span class="sxs-lookup"><span data-stu-id="1e7f4-113">Remarks</span></span>

<span data-ttu-id="1e7f4-114">相當於：</span><span class="sxs-lookup"><span data-stu-id="1e7f4-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```