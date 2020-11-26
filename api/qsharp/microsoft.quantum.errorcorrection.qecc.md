---
uid: Microsoft.Quantum.ErrorCorrection.QECC
title: QECC 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: QECC
qsharp.summary: Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.
ms.openlocfilehash: c0c20fa82988aad661579c6498fec47e77f0726a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200606"
---
# <a name="qecc-user-defined-type"></a><span data-ttu-id="2eadb-102">QECC 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="2eadb-102">QECC user defined type</span></span>

<span data-ttu-id="2eadb-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2eadb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2eadb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2eadb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2eadb-105">代表錯誤更正程式碼，如其編碼器、解碼器和症狀度量程式所定義。</span><span class="sxs-lookup"><span data-stu-id="2eadb-105">Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.</span></span>

```qsharp

newtype QECC = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

