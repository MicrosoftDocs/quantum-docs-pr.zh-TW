---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204108"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="5e976-102">HTermsToGenSys 函式</span><span class="sxs-lookup"><span data-stu-id="5e976-102">HTermsToGenSys function</span></span>

<span data-ttu-id="5e976-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5e976-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="5e976-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5e976-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5e976-105">將資料格式的 Hamiltonian 轉換 `HTerm[]` 為 GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="5e976-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="5e976-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5e976-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="5e976-107">data： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="5e976-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="5e976-108">以格式輸入資料 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="5e976-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="5e976-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5e976-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5e976-110">新增至 GeneratorIndex 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="5e976-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="5e976-111">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="5e976-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="5e976-112">代表輸入所代表之 Hamiltonian 的 GeneratorSystem `data` 。</span><span class="sxs-lookup"><span data-stu-id="5e976-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>