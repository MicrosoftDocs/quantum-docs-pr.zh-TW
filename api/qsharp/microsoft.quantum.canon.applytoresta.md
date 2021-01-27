---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841255"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="20bce-102">ApplyToRestA 操作</span><span class="sxs-lookup"><span data-stu-id="20bce-102">ApplyToRestA operation</span></span>

<span data-ttu-id="20bce-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20bce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20bce-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20bce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20bce-105">將作業套用至陣列的第一個元素以外的所有專案。</span><span class="sxs-lookup"><span data-stu-id="20bce-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="20bce-106">描述</span><span class="sxs-lookup"><span data-stu-id="20bce-106">Description</span></span>

<span data-ttu-id="20bce-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="20bce-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="20bce-108">輸入</span><span class="sxs-lookup"><span data-stu-id="20bce-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="20bce-109">op： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="20bce-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="20bce-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="20bce-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="20bce-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="20bce-111">targets : 'T[]</span></span>

<span data-ttu-id="20bce-112">目標的陣列，其中全部都將套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="20bce-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20bce-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20bce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="20bce-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="20bce-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20bce-115">不要</span><span class="sxs-lookup"><span data-stu-id="20bce-115">'T</span></span>

<span data-ttu-id="20bce-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="20bce-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="20bce-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="20bce-117">See Also</span></span>

- [<span data-ttu-id="20bce-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="20bce-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="20bce-119">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="20bce-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="20bce-120">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="20bce-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)