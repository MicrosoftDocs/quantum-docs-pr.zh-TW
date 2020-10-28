---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 6d2ead95a60ed3cc8ee95fb7f91e1aa49d366a48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697782"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="e79ce-102">AssertOperationsEqualInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="e79ce-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="e79ce-103">命名空間： [Microsoft. 副檔名. 測試](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="e79ce-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="e79ce-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e79ce-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="e79ce-105">AssertOperationsEqualInPlace 已被取代。</span><span class="sxs-lookup"><span data-stu-id="e79ce-105">AssertOperationsEqualInPlace has been deprecated.</span></span> <span data-ttu-id="e79ce-106">請改用 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace>。</span><span class="sxs-lookup"><span data-stu-id="e79ce-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.</span></span>
>
> <span data-ttu-id="e79ce-107">請使用 @"microsoft.quantum.diagnostics.assertoperationsequalinplace"。</span><span class="sxs-lookup"><span data-stu-id="e79ce-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span></span>
> <span data-ttu-id="e79ce-108">請注意，此作業的引數順序已變更。</span><span class="sxs-lookup"><span data-stu-id="e79ce-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="e79ce-109">輸入</span><span class="sxs-lookup"><span data-stu-id="e79ce-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="e79ce-110">實際： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e79ce-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="e79ce-111">預期： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="e79ce-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="e79ce-112">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e79ce-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e79ce-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e79ce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

