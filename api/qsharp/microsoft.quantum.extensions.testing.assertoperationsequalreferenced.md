---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualReferenced has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 1f4d98006677dc532d45ffb797fe0a8e05496640
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820098"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="3c369-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="3c369-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="3c369-103">命名空間： [Microsoft. 副檔名. 測試](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="3c369-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="3c369-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3c369-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="3c369-105">AssertOperationsEqualReferenced 已被取代。</span><span class="sxs-lookup"><span data-stu-id="3c369-105">AssertOperationsEqualReferenced has been deprecated.</span></span> <span data-ttu-id="3c369-106">請改用 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>。</span><span class="sxs-lookup"><span data-stu-id="3c369-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> instead.</span></span>
>
> <span data-ttu-id="3c369-107">請使用 @"microsoft.quantum.diagnostics.assertoperationsequalreferenced"。</span><span class="sxs-lookup"><span data-stu-id="3c369-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalreferenced".</span></span>
> <span data-ttu-id="3c369-108">請注意，此作業的引數順序已變更。</span><span class="sxs-lookup"><span data-stu-id="3c369-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualReferenced (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="3c369-109">輸入</span><span class="sxs-lookup"><span data-stu-id="3c369-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="3c369-110">實際： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c369-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="3c369-111">預期： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="3c369-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="3c369-112">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c369-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="3c369-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c369-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

