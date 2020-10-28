---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700778"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="5a6c0-102">ReflectionOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="5a6c0-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="5a6c0-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5a6c0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5a6c0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a6c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a6c0-105">表示反映 oracle。</span><span class="sxs-lookup"><span data-stu-id="5a6c0-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="5a6c0-106">反映 oracle （$O $）有輸入：</span><span class="sxs-lookup"><span data-stu-id="5a6c0-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="5a6c0-107">用來旋轉反映子空間的階段 $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="5a6c0-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="5a6c0-108">要在其上執行給定反映的量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="5a6c0-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="5a6c0-109">命名專案</span><span class="sxs-lookup"><span data-stu-id="5a6c0-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="5a6c0-110">ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5a6c0-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="5a6c0-111">備註</span><span class="sxs-lookup"><span data-stu-id="5a6c0-111">Remarks</span></span>

<span data-ttu-id="5a6c0-112">此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 會透過階段 $ \phi $ 來執行部分反映，大約是單一的純狀態 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="5a6c0-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>