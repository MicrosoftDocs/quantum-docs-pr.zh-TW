---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698911"
---
# <a name="rall0-operation"></a><span data-ttu-id="17ddb-102">RAll0 操作</span><span class="sxs-lookup"><span data-stu-id="17ddb-102">RAll0 operation</span></span>

<span data-ttu-id="17ddb-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17ddb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17ddb-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17ddb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17ddb-105">執行階段移位操作。</span><span class="sxs-lookup"><span data-stu-id="17ddb-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="17ddb-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="17ddb-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="17ddb-107">輸入</span><span class="sxs-lookup"><span data-stu-id="17ddb-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="17ddb-108">階段： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17ddb-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17ddb-109">階段 $ \phi $ 已套用至 state $ \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="17ddb-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="17ddb-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="17ddb-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="17ddb-111">要 $R $ 旋轉其狀態的註冊。</span><span class="sxs-lookup"><span data-stu-id="17ddb-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17ddb-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17ddb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="17ddb-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17ddb-113">See Also</span></span>

- [<span data-ttu-id="17ddb-114">Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="17ddb-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)