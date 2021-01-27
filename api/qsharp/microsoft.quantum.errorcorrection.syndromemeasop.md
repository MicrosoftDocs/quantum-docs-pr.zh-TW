---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850043"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="7c421-102">SyndromeMeasOp 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="7c421-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="7c421-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7c421-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7c421-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c421-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c421-105">表示用來測量錯誤修正程式碼區塊之症狀的作業。</span><span class="sxs-lookup"><span data-stu-id="7c421-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="7c421-106">範例</span><span class="sxs-lookup"><span data-stu-id="7c421-106">Example</span></span>

<span data-ttu-id="7c421-107">Syndromes = \langle ZZI，IZZ \rangle $ 以非容錯方式使用臨時量子位的「位-翻轉」程式 $S 代碼的測量：</span><span class="sxs-lookup"><span data-stu-id="7c421-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="7c421-108">備註</span><span class="sxs-lookup"><span data-stu-id="7c421-108">Remarks</span></span>

<span data-ttu-id="7c421-109">簽章 `(LogicalRegister => Syndrome)` 代表一項作業，該作業會共同在的量子位上運作 `LogicalRegister` ，而有些輔助量子位則接著輔助量子位的度量，以將 `Syndrome` 代表 `Result[]` 這些測量之的值解壓縮。</span><span class="sxs-lookup"><span data-stu-id="7c421-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c421-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7c421-110">See Also</span></span>

- [<span data-ttu-id="7c421-111">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="7c421-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="7c421-112">ErrorCorrection 的症狀</span><span class="sxs-lookup"><span data-stu-id="7c421-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)