---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697202"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="cfc7b-102">ComplexPolar 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="cfc7b-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="cfc7b-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cfc7b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cfc7b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cfc7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cfc7b-105">以極座標形式表示複數。</span><span class="sxs-lookup"><span data-stu-id="cfc7b-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="cfc7b-106">複數的極座標表示為 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="cfc7b-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="cfc7b-107">命名專案</span><span class="sxs-lookup"><span data-stu-id="cfc7b-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="cfc7b-108">大小： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfc7b-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfc7b-109">絕對值 $r $c $ 的 \ge $0。</span><span class="sxs-lookup"><span data-stu-id="cfc7b-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="cfc7b-110">引數： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfc7b-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfc7b-111">階段 $t \in \mathbb R $ of $c $。</span><span class="sxs-lookup"><span data-stu-id="cfc7b-111">The phase $t \in \mathbb R$ of $c$.</span></span>