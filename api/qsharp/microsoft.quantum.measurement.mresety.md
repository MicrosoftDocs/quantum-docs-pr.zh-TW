---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701006"
---
# <a name="mresety-operation"></a><span data-ttu-id="feece-102">MResetY 操作</span><span class="sxs-lookup"><span data-stu-id="feece-102">MResetY operation</span></span>

<span data-ttu-id="feece-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="feece-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="feece-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="feece-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="feece-105">以 Y 為單位測量單一量子位，並將它重設為遵循測量的固定初始狀態。</span><span class="sxs-lookup"><span data-stu-id="feece-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="feece-106">描述</span><span class="sxs-lookup"><span data-stu-id="feece-106">Description</span></span>

<span data-ttu-id="feece-107">以 $Y $ 基礎執行單一量子位量測，並確保量子位會在測量之後傳回 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="feece-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="feece-108">輸入</span><span class="sxs-lookup"><span data-stu-id="feece-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="feece-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="feece-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="feece-110">要測量的單一量子位。</span><span class="sxs-lookup"><span data-stu-id="feece-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="feece-111">輸出： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="feece-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="feece-112">`target`以 Pauli $Y $ 基礎測量的結果。</span><span class="sxs-lookup"><span data-stu-id="feece-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>