---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854881"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="bfef9-102">StateGenerator 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="bfef9-102">StateGenerator user defined type</span></span>

<span data-ttu-id="bfef9-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bfef9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bfef9-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bfef9-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="bfef9-105">描述準備指定輸入至連續分類器的作業。</span><span class="sxs-lookup"><span data-stu-id="bfef9-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="bfef9-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="bfef9-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="bfef9-107">NQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bfef9-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bfef9-108">已定義編碼輸入的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="bfef9-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="bfef9-109">準備： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bfef9-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bfef9-110">這項作業會在量子位的位元組由小到大登錄上準備編碼的輸入 `NQubits` 。</span><span class="sxs-lookup"><span data-stu-id="bfef9-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>