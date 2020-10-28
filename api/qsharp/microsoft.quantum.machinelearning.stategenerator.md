---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700259"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="bfa4c-102">StateGenerator 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="bfa4c-102">StateGenerator user defined type</span></span>

<span data-ttu-id="bfa4c-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bfa4c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bfa4c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bfa4c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bfa4c-105">描述準備指定輸入至連續分類器的作業。</span><span class="sxs-lookup"><span data-stu-id="bfa4c-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="bfa4c-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="bfa4c-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="bfa4c-107">NQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bfa4c-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bfa4c-108">已定義編碼輸入的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="bfa4c-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="bfa4c-109">準備： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bfa4c-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bfa4c-110">這項作業會在量子位的位元組由小到大登錄上準備編碼的輸入 `NQubits` 。</span><span class="sxs-lookup"><span data-stu-id="bfa4c-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>