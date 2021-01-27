---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854679"
---
# <a name="measureallz-operation"></a><span data-ttu-id="03c66-102">MeasureAllZ 操作</span><span class="sxs-lookup"><span data-stu-id="03c66-102">MeasureAllZ operation</span></span>

<span data-ttu-id="03c66-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="03c66-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="03c66-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03c66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03c66-105">以 Pauli Z 為單位共同測量量子位的暫存器。</span><span class="sxs-lookup"><span data-stu-id="03c66-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="03c66-106">描述</span><span class="sxs-lookup"><span data-stu-id="03c66-106">Description</span></span>

<span data-ttu-id="03c66-107">以 $Z \otimes Z \otimes \cdots \otimes Z $ 基礎測量量子位的暫存器，代表整個登錄的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="03c66-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="03c66-108">輸入</span><span class="sxs-lookup"><span data-stu-id="03c66-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="03c66-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="03c66-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="03c66-110">要測量的註冊。</span><span class="sxs-lookup"><span data-stu-id="03c66-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="03c66-111">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="03c66-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="03c66-112">測量 $Z \otimes Z \otimes \cdots \otimes Z $ 的結果。</span><span class="sxs-lookup"><span data-stu-id="03c66-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>