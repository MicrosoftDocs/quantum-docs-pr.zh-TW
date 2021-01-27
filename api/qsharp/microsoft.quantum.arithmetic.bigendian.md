---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843385"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="ca5db-102">BigEndian 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="ca5db-102">BigEndian user defined type</span></span>

<span data-ttu-id="ca5db-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ca5db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ca5db-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca5db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca5db-105">以位元組由大到小的順序註冊，將不帶正負號的整數編碼。</span><span class="sxs-lookup"><span data-stu-id="ca5db-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="ca5db-106">具有索引的量子位會 `0` 將不帶正負號整數的最高位編碼。</span><span class="sxs-lookup"><span data-stu-id="ca5db-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="ca5db-107">備註</span><span class="sxs-lookup"><span data-stu-id="ca5db-107">Remarks</span></span>

<span data-ttu-id="ca5db-108">我們 `BigEndian` `BE` 將在檔中縮寫。</span><span class="sxs-lookup"><span data-stu-id="ca5db-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>