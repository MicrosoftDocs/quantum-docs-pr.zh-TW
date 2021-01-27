---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842990"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="e684b-102">PhaseLittleEndian 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="e684b-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="e684b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e684b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e684b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e684b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e684b-105">以 QFT 為基礎的位元組由小到大不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="e684b-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="e684b-106">例如，如果 $ \ket{x} $ 是整數 $x $ 的位元組由大到小編碼，則 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 基礎中 $x $ 的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="e684b-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="e684b-107">備註</span><span class="sxs-lookup"><span data-stu-id="e684b-107">Remarks</span></span>

<span data-ttu-id="e684b-108">我們 `PhaseLittleEndian` `PhaseLE` 將在檔中縮寫。</span><span class="sxs-lookup"><span data-stu-id="e684b-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="e684b-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e684b-109">See Also</span></span>

- [<span data-ttu-id="e684b-110">Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="e684b-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="e684b-111">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="e684b-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)