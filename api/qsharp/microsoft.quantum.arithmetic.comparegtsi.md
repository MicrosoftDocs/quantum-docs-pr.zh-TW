---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699919"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="56562-102">CompareGTSI 操作</span><span class="sxs-lookup"><span data-stu-id="56562-102">CompareGTSI operation</span></span>

<span data-ttu-id="56562-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="56562-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="56562-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56562-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56562-105">帶正負號整數比較的包裝函式： `result = xs > ys` 。</span><span class="sxs-lookup"><span data-stu-id="56562-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="56562-106">輸入</span><span class="sxs-lookup"><span data-stu-id="56562-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="56562-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="56562-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="56562-108">第一個 $n $ 位數位</span><span class="sxs-lookup"><span data-stu-id="56562-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="56562-109">y) ： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="56562-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="56562-110">第二 $n $ 位數位</span><span class="sxs-lookup"><span data-stu-id="56562-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="56562-111">結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56562-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56562-112">如果 $xs > y) $，將會翻轉</span><span class="sxs-lookup"><span data-stu-id="56562-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="56562-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56562-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

