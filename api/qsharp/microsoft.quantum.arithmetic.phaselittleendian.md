---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699565"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="1c8f5-102">PhaseLittleEndian 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="1c8f5-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="1c8f5-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1c8f5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1c8f5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c8f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c8f5-105">以 QFT 為基礎的位元組由小到大不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="1c8f5-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="1c8f5-106">例如，如果 $ \ket{x} $ 是整數 $x $ 的位元組由大到小編碼，則 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 基礎中 $x $ 的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="1c8f5-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="1c8f5-107">備註</span><span class="sxs-lookup"><span data-stu-id="1c8f5-107">Remarks</span></span>

<span data-ttu-id="1c8f5-108">我們 `PhaseLittleEndian` `PhaseLE` 將在檔中縮寫。</span><span class="sxs-lookup"><span data-stu-id="1c8f5-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c8f5-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1c8f5-109">See Also</span></span>

- [<span data-ttu-id="1c8f5-110">Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="1c8f5-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="1c8f5-111">Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="1c8f5-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)