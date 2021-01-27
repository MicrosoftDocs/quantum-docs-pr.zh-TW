---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 660e6633df6750747963d41a6ff28a4fd4b02d4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840267"
---
# <a name="rall0-operation"></a><span data-ttu-id="39abe-102">RAll0 操作</span><span class="sxs-lookup"><span data-stu-id="39abe-102">RAll0 operation</span></span>

<span data-ttu-id="39abe-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39abe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39abe-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39abe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39abe-105">執行階段移位操作。</span><span class="sxs-lookup"><span data-stu-id="39abe-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="39abe-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="39abe-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="39abe-107">輸入</span><span class="sxs-lookup"><span data-stu-id="39abe-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="39abe-108">階段： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="39abe-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="39abe-109">階段 $ \phi $ 已套用至 state $ \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="39abe-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="39abe-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39abe-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39abe-111">要 $R $ 旋轉其狀態的註冊。</span><span class="sxs-lookup"><span data-stu-id="39abe-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39abe-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39abe-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="39abe-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39abe-113">See Also</span></span>

- [<span data-ttu-id="39abe-114">Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="39abe-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)