---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222774"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="f992e-102">LittleEndian 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="f992e-102">LittleEndian user defined type</span></span>

<span data-ttu-id="f992e-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f992e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f992e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f992e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f992e-105">以位元組由小到大的順序註冊，將不帶正負號的整數編碼。</span><span class="sxs-lookup"><span data-stu-id="f992e-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="f992e-106">具有索引的量子位會 `0` 將不帶正負號整數的最低位編碼。</span><span class="sxs-lookup"><span data-stu-id="f992e-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="f992e-107">備註</span><span class="sxs-lookup"><span data-stu-id="f992e-107">Remarks</span></span>

<span data-ttu-id="f992e-108">我們 `LittleEndian` `LE` 將在檔中縮寫。</span><span class="sxs-lookup"><span data-stu-id="f992e-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>