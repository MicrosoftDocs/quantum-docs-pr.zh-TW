---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223658"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="39640-102">BigEndian 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="39640-102">BigEndian user defined type</span></span>

<span data-ttu-id="39640-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="39640-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="39640-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39640-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39640-105">以位元組由大到小的順序註冊，將不帶正負號的整數編碼。</span><span class="sxs-lookup"><span data-stu-id="39640-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="39640-106">具有索引的量子位會 `0` 將不帶正負號整數的最高位編碼。</span><span class="sxs-lookup"><span data-stu-id="39640-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="39640-107">備註</span><span class="sxs-lookup"><span data-stu-id="39640-107">Remarks</span></span>

<span data-ttu-id="39640-108">我們 `BigEndian` `BE` 將在檔中縮寫。</span><span class="sxs-lookup"><span data-stu-id="39640-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>