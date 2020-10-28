---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697603"
---
# <a name="mresetz-operation"></a><span data-ttu-id="9f974-102">MResetZ 操作</span><span class="sxs-lookup"><span data-stu-id="9f974-102">MResetZ operation</span></span>

<span data-ttu-id="9f974-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9f974-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9f974-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f974-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f974-105">以 Z 為單位測量單一量子位，並將它重設為遵循測量的固定初始狀態。</span><span class="sxs-lookup"><span data-stu-id="9f974-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="9f974-106">描述</span><span class="sxs-lookup"><span data-stu-id="9f974-106">Description</span></span>

<span data-ttu-id="9f974-107">以 $Z $ 基礎執行單一量子位量測，並確保量子位會在測量之後傳回 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="9f974-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="9f974-108">輸入</span><span class="sxs-lookup"><span data-stu-id="9f974-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="9f974-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9f974-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9f974-110">要測量的單一量子位。</span><span class="sxs-lookup"><span data-stu-id="9f974-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9f974-111">輸出： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9f974-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9f974-112">`target`以 Pauli $Z $ 基礎測量的結果。</span><span class="sxs-lookup"><span data-stu-id="9f974-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>