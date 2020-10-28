---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: JordanWignerEncodingData 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 62988eefa57d8a9e4ed9dcfbdbc6c3b630c6faa2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698459"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a><span data-ttu-id="1f887-102">JordanWignerEncodingData 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="1f887-102">JordanWignerEncodingData user defined type</span></span>

<span data-ttu-id="1f887-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1f887-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1f887-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f887-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f887-105">從 c # 傳遞至 Q # 的資料格式，以代表 Hamiltonian 模擬的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="1f887-105">Format of data passed from C# to Q# to represent all information for Hamiltonian simulation.</span></span>
<span data-ttu-id="1f887-106">所表示資料的意義是由接收它的演算法所決定。</span><span class="sxs-lookup"><span data-stu-id="1f887-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

