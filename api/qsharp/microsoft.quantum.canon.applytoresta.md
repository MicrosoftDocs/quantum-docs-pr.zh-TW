---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699150"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="1c3a0-102">ApplyToRestA 操作</span><span class="sxs-lookup"><span data-stu-id="1c3a0-102">ApplyToRestA operation</span></span>

<span data-ttu-id="1c3a0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1c3a0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1c3a0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c3a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c3a0-105">將作業套用至陣列的第一個元素以外的所有專案。</span><span class="sxs-lookup"><span data-stu-id="1c3a0-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="1c3a0-106">描述</span><span class="sxs-lookup"><span data-stu-id="1c3a0-106">Description</span></span>

<span data-ttu-id="1c3a0-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="1c3a0-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1c3a0-108">輸入</span><span class="sxs-lookup"><span data-stu-id="1c3a0-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="1c3a0-109">op： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="1c3a0-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1c3a0-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="1c3a0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1c3a0-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="1c3a0-111">targets : 'T[]</span></span>

<span data-ttu-id="1c3a0-112">目標的陣列，其中全部都將套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="1c3a0-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c3a0-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c3a0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1c3a0-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="1c3a0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1c3a0-115">不要</span><span class="sxs-lookup"><span data-stu-id="1c3a0-115">'T</span></span>

<span data-ttu-id="1c3a0-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="1c3a0-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c3a0-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1c3a0-117">See Also</span></span>

- [<span data-ttu-id="1c3a0-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="1c3a0-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="1c3a0-119">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="1c3a0-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="1c3a0-120">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="1c3a0-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)