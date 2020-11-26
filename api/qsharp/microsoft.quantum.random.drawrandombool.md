---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192956"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="0f32f-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="0f32f-102">DrawRandomBool operation</span></span>

<span data-ttu-id="0f32f-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0f32f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0f32f-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0f32f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0f32f-105">獲得成功機率之後，會傳回一則具有指定機率的單一利利實驗。</span><span class="sxs-lookup"><span data-stu-id="0f32f-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0f32f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0f32f-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="0f32f-107">successProbability： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f32f-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f32f-108">應該傳回的機率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="0f32f-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0f32f-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0f32f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0f32f-110">`true` 具有機率 `successProbability` 和機率 `false` `1.0 - successProbability` 。</span><span class="sxs-lookup"><span data-stu-id="0f32f-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>