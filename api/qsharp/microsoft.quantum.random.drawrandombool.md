---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699656"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="3cfe8-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="3cfe8-102">DrawRandomBool operation</span></span>

<span data-ttu-id="3cfe8-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3cfe8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3cfe8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3cfe8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3cfe8-105">獲得成功機率之後，會傳回一則具有指定機率的單一利利實驗。</span><span class="sxs-lookup"><span data-stu-id="3cfe8-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3cfe8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3cfe8-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="3cfe8-107">successProbability： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3cfe8-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3cfe8-108">應該傳回的機率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3cfe8-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3cfe8-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3cfe8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3cfe8-110">`true` 具有機率 `successProbability` 和機率 `false` `1.0 - successProbability` 。</span><span class="sxs-lookup"><span data-stu-id="3cfe8-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>