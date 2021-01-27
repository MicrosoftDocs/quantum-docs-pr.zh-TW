---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841322"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="09ef7-102">ApplyToMostCA 操作</span><span class="sxs-lookup"><span data-stu-id="09ef7-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="09ef7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09ef7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09ef7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09ef7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09ef7-105">將作業套用至陣列的最後一個元素以外的所有專案。</span><span class="sxs-lookup"><span data-stu-id="09ef7-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="09ef7-106">描述</span><span class="sxs-lookup"><span data-stu-id="09ef7-106">Description</span></span>

<span data-ttu-id="09ef7-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="09ef7-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="09ef7-108">輸入</span><span class="sxs-lookup"><span data-stu-id="09ef7-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="09ef7-109">op： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="09ef7-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="09ef7-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="09ef7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="09ef7-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="09ef7-111">targets : 'T[]</span></span>

<span data-ttu-id="09ef7-112">目標的陣列，其中最後一個只會套用到最後一個 `op` 。</span><span class="sxs-lookup"><span data-stu-id="09ef7-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09ef7-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09ef7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="09ef7-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="09ef7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09ef7-115">不要</span><span class="sxs-lookup"><span data-stu-id="09ef7-115">'T</span></span>

<span data-ttu-id="09ef7-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="09ef7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="09ef7-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09ef7-117">See Also</span></span>

- [<span data-ttu-id="09ef7-118">Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="09ef7-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="09ef7-119">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="09ef7-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="09ef7-120">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="09ef7-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)