---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853680"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="aa1db-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="aa1db-102">DrawRandomBool operation</span></span>

<span data-ttu-id="aa1db-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="aa1db-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="aa1db-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="aa1db-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="aa1db-105">獲得成功機率之後，會傳回一則具有指定機率的單一利利實驗。</span><span class="sxs-lookup"><span data-stu-id="aa1db-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="aa1db-106">輸入</span><span class="sxs-lookup"><span data-stu-id="aa1db-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="aa1db-107">successProbability： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aa1db-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aa1db-108">應該傳回的機率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="aa1db-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="aa1db-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aa1db-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aa1db-110">`true` 具有機率 `successProbability` 和機率 `false` `1.0 - successProbability` 。</span><span class="sxs-lookup"><span data-stu-id="aa1db-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="aa1db-111">範例</span><span class="sxs-lookup"><span data-stu-id="aa1db-111">Example</span></span>

<span data-ttu-id="aa1db-112">下列 Q # 程式碼片段範例會從偏誤的硬幣中翻轉：</span><span class="sxs-lookup"><span data-stu-id="aa1db-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```