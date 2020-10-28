---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700514"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="d0e84-102">FeatureRegisterSize 函式</span><span class="sxs-lookup"><span data-stu-id="d0e84-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="d0e84-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d0e84-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d0e84-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0e84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0e84-105">傳回編碼特定功能向量所需的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="d0e84-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="d0e84-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d0e84-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="d0e84-107">範例： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d0e84-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d0e84-108">要編碼成量子位註冊的範例功能向量。</span><span class="sxs-lookup"><span data-stu-id="d0e84-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="d0e84-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0e84-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0e84-110">編碼為量子位暫存器所需的大小 `sample` ，以量子位數表示。</span><span class="sxs-lookup"><span data-stu-id="d0e84-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>