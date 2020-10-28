---
uid: Microsoft.Quantum.Canon.CCNOTop
title: CCNOTop 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CCNOTop
qsharp.summary: The signature type of CCNOT gate.
ms.openlocfilehash: 026a368b753a1b3e74b8e4352cf65835546df4bc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699081"
---
# <a name="ccnotop-user-defined-type"></a><span data-ttu-id="a0511-102">CCNOTop 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="a0511-102">CCNOTop user defined type</span></span>

<span data-ttu-id="a0511-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a0511-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a0511-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0511-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0511-105">CCNOT 閘道的簽名類型。</span><span class="sxs-lookup"><span data-stu-id="a0511-105">The signature type of CCNOT gate.</span></span>

```qsharp

newtype CCNOTop = (Apply : ((Qubit, Qubit, Qubit) => Unit is Adj));
```



## <a name="named-items"></a><span data-ttu-id="a0511-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="a0511-106">Named Items</span></span>

### <a name="apply--qubitqubitqubit--unit-adj"></a><span data-ttu-id="a0511-107">Apply： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)、[量子位](xref:microsoft.quantum.lang-ref.qubit)) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="a0511-107">Apply : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

