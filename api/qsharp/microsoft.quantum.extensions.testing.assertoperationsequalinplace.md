---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 64cc1e5c78af100b652ced24f00f3097c35ea5d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820229"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="aae62-102">AssertOperationsEqualInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="aae62-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="aae62-103">命名空間： [Microsoft. 副檔名. 測試](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="aae62-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="aae62-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="aae62-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="aae62-105">AssertOperationsEqualInPlace 已被取代。</span><span class="sxs-lookup"><span data-stu-id="aae62-105">AssertOperationsEqualInPlace has been deprecated.</span></span> <span data-ttu-id="aae62-106">請改用 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace>。</span><span class="sxs-lookup"><span data-stu-id="aae62-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.</span></span>
>
> <span data-ttu-id="aae62-107">請使用 @"microsoft.quantum.diagnostics.assertoperationsequalinplace"。</span><span class="sxs-lookup"><span data-stu-id="aae62-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span></span>
> <span data-ttu-id="aae62-108">請注意，此作業的引數順序已變更。</span><span class="sxs-lookup"><span data-stu-id="aae62-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="aae62-109">輸入</span><span class="sxs-lookup"><span data-stu-id="aae62-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="aae62-110">實際： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aae62-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="aae62-111">預期： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="aae62-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="aae62-112">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aae62-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="aae62-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aae62-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

