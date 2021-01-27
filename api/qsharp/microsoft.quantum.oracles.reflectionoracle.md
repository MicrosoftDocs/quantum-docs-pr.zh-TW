---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854480"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="a15b6-102">ReflectionOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="a15b6-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="a15b6-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a15b6-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a15b6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a15b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a15b6-105">表示反映 oracle。</span><span class="sxs-lookup"><span data-stu-id="a15b6-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="a15b6-106">反映 oracle （$O $）有輸入：</span><span class="sxs-lookup"><span data-stu-id="a15b6-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="a15b6-107">用來旋轉反映子空間的階段 $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="a15b6-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="a15b6-108">要在其上執行給定反映的量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="a15b6-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="a15b6-109">命名專案</span><span class="sxs-lookup"><span data-stu-id="a15b6-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="a15b6-110">ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a15b6-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="a15b6-111">備註</span><span class="sxs-lookup"><span data-stu-id="a15b6-111">Remarks</span></span>

<span data-ttu-id="a15b6-112">此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 會透過階段 $ \phi $ 來執行部分反映，大約是單一的純狀態 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="a15b6-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>