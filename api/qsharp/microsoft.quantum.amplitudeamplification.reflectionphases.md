---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700094"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="d27ec-102">ReflectionPhases 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="d27ec-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="d27ec-103">命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d27ec-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d27ec-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d27ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d27ec-105">以振幅放大的部分反射順序的階段。</span><span class="sxs-lookup"><span data-stu-id="d27ec-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="d27ec-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="d27ec-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="d27ec-107">AboutStart： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d27ec-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d27ec-108">關於開始狀態之反映的階段陣列。</span><span class="sxs-lookup"><span data-stu-id="d27ec-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="d27ec-109">AboutTarget： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d27ec-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d27ec-110">有關目標狀態之反映的階段陣列。</span><span class="sxs-lookup"><span data-stu-id="d27ec-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="d27ec-111">備註</span><span class="sxs-lookup"><span data-stu-id="d27ec-111">Remarks</span></span>

<span data-ttu-id="d27ec-112">這兩個數組的長度必須相等。</span><span class="sxs-lookup"><span data-stu-id="d27ec-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="d27ec-113">請注意，在許多情況下，有關目標狀態的開始狀態和最後一個階段的第一個階段會引進全域階段轉移，而且可以設定為 $0 $。</span><span class="sxs-lookup"><span data-stu-id="d27ec-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>