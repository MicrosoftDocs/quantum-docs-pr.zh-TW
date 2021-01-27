---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847171"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="32302-102">ReflectionPhases 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="32302-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="32302-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="32302-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="32302-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32302-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32302-105">以振幅放大的部分反射順序的階段。</span><span class="sxs-lookup"><span data-stu-id="32302-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="32302-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="32302-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="32302-107">AboutStart： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="32302-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="32302-108">關於開始狀態之反映的階段陣列。</span><span class="sxs-lookup"><span data-stu-id="32302-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="32302-109">AboutTarget： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="32302-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="32302-110">有關目標狀態之反映的階段陣列。</span><span class="sxs-lookup"><span data-stu-id="32302-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="32302-111">備註</span><span class="sxs-lookup"><span data-stu-id="32302-111">Remarks</span></span>

<span data-ttu-id="32302-112">這兩個數組的長度必須相等。</span><span class="sxs-lookup"><span data-stu-id="32302-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="32302-113">請注意，在許多情況下，有關目標狀態的開始狀態和最後一個階段的第一個階段會引進全域階段轉移，而且可以設定為 $0 $。</span><span class="sxs-lookup"><span data-stu-id="32302-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>