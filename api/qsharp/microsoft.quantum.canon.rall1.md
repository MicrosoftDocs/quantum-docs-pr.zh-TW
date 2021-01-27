---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: f4159a6cc0e0b4f18f418a53a309b5ce527b2608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852253"
---
# <a name="rall1-operation"></a><span data-ttu-id="15c53-102">RAll1 操作</span><span class="sxs-lookup"><span data-stu-id="15c53-102">RAll1 operation</span></span>

<span data-ttu-id="15c53-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="15c53-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="15c53-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15c53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15c53-105">執行階段移位操作。</span><span class="sxs-lookup"><span data-stu-id="15c53-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="15c53-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="15c53-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="15c53-107">輸入</span><span class="sxs-lookup"><span data-stu-id="15c53-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="15c53-108">階段： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="15c53-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="15c53-109">階段 $ \phi $ 已套用至 state $ \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="15c53-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="15c53-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="15c53-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="15c53-111">要 $R $ 旋轉其狀態的註冊。</span><span class="sxs-lookup"><span data-stu-id="15c53-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15c53-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15c53-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

