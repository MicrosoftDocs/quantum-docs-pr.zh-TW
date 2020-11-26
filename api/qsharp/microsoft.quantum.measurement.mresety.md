---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227024"
---
# <a name="mresety-operation"></a><span data-ttu-id="518af-102">MResetY 操作</span><span class="sxs-lookup"><span data-stu-id="518af-102">MResetY operation</span></span>

<span data-ttu-id="518af-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="518af-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="518af-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="518af-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="518af-105">以 Y 為單位測量單一量子位，並將它重設為遵循測量的固定初始狀態。</span><span class="sxs-lookup"><span data-stu-id="518af-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="518af-106">描述</span><span class="sxs-lookup"><span data-stu-id="518af-106">Description</span></span>

<span data-ttu-id="518af-107">以 $Y $ 基礎執行單一量子位量測，並確保量子位會在測量之後傳回 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="518af-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="518af-108">輸入</span><span class="sxs-lookup"><span data-stu-id="518af-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="518af-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="518af-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="518af-110">要測量的單一量子位。</span><span class="sxs-lookup"><span data-stu-id="518af-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="518af-111">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="518af-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="518af-112">`target`以 Pauli $Y $ 基礎測量的結果。</span><span class="sxs-lookup"><span data-stu-id="518af-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>