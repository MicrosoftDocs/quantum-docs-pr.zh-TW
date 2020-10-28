---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698363"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="6d84c-102">ExpandedCoefficients 函式</span><span class="sxs-lookup"><span data-stu-id="6d84c-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="6d84c-103">命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="6d84c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="6d84c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d84c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d84c-105">展開 Jordan-Wigner 係數的 compact 標記法，以便取得這些詞彙與 Pauli 詞彙之間的一對一對應。</span><span class="sxs-lookup"><span data-stu-id="6d84c-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="6d84c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6d84c-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="6d84c-107">coeff： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6d84c-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6d84c-108">係數的陣列，做為從 Jordan-Wigner Hamiltonian 資料結構讀取的係數。</span><span class="sxs-lookup"><span data-stu-id="6d84c-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="6d84c-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d84c-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d84c-110">Jordan-Wigner 詞彙的型別。</span><span class="sxs-lookup"><span data-stu-id="6d84c-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="6d84c-111">輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6d84c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6d84c-112">展開的係數陣列，每個 Pauli 詞彙一個。</span><span class="sxs-lookup"><span data-stu-id="6d84c-112">Expanded arrays of coefficients, one per Pauli term.</span></span>