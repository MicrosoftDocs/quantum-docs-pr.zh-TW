---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226650"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="d6658-102">ReflectionOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="d6658-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="d6658-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d6658-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d6658-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6658-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6658-105">表示反映 oracle。</span><span class="sxs-lookup"><span data-stu-id="d6658-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="d6658-106">反映 oracle （$O $）有輸入：</span><span class="sxs-lookup"><span data-stu-id="d6658-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="d6658-107">用來旋轉反映子空間的階段 $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="d6658-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="d6658-108">要在其上執行給定反映的量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="d6658-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="d6658-109">命名專案</span><span class="sxs-lookup"><span data-stu-id="d6658-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="d6658-110">ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d6658-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="d6658-111">備註</span><span class="sxs-lookup"><span data-stu-id="d6658-111">Remarks</span></span>

<span data-ttu-id="d6658-112">此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 會透過階段 $ \phi $ 來執行部分反映，大約是單一的純狀態 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="d6658-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>