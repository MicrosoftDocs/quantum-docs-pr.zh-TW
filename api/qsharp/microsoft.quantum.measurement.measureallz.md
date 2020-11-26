---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227075"
---
# <a name="measureallz-operation"></a><span data-ttu-id="ca9aa-102">MeasureAllZ 操作</span><span class="sxs-lookup"><span data-stu-id="ca9aa-102">MeasureAllZ operation</span></span>

<span data-ttu-id="ca9aa-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ca9aa-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ca9aa-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca9aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca9aa-105">以 Pauli Z 為單位共同測量量子位的暫存器。</span><span class="sxs-lookup"><span data-stu-id="ca9aa-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="ca9aa-106">描述</span><span class="sxs-lookup"><span data-stu-id="ca9aa-106">Description</span></span>

<span data-ttu-id="ca9aa-107">以 $Z \otimes Z \otimes \cdots \otimes Z $ 基礎測量量子位的暫存器，代表整個登錄的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="ca9aa-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="ca9aa-108">輸入</span><span class="sxs-lookup"><span data-stu-id="ca9aa-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="ca9aa-109">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ca9aa-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ca9aa-110">要測量的註冊。</span><span class="sxs-lookup"><span data-stu-id="ca9aa-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ca9aa-111">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ca9aa-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ca9aa-112">測量 $Z \otimes Z \otimes \cdots \otimes Z $ 的結果。</span><span class="sxs-lookup"><span data-stu-id="ca9aa-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>