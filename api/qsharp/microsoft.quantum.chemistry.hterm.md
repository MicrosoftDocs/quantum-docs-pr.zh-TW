---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204125"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="1e5eb-102">HTerm 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="1e5eb-102">HTerm user defined type</span></span>

<span data-ttu-id="1e5eb-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1e5eb-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="1e5eb-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1e5eb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1e5eb-105">從 c # 傳遞至 Q # 的資料格式，以代表 Hamiltonian 的詞彙。</span><span class="sxs-lookup"><span data-stu-id="1e5eb-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="1e5eb-106">所表示資料的意義是由接收它的演算法所決定。</span><span class="sxs-lookup"><span data-stu-id="1e5eb-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

