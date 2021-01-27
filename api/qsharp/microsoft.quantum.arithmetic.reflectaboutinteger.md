---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842985"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="92a56-102">ReflectAboutInteger 操作</span><span class="sxs-lookup"><span data-stu-id="92a56-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="92a56-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="92a56-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="92a56-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92a56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92a56-105">反映指定之傳統整數的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="92a56-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="92a56-106">描述</span><span class="sxs-lookup"><span data-stu-id="92a56-106">Description</span></span>

<span data-ttu-id="92a56-107">如果一開始是以 $ \ sum_i \ Alpha_i \ket{i} $ 表示的量子暫存器，其中每個 $ \ket{i} $ 是代表整數 $i $ 的基礎狀態，則會反映有關指定整數 $ \ket{j} $，$ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ Alpha_i \ket{i} $ $ 的基礎狀態的註冊狀態</span><span class="sxs-lookup"><span data-stu-id="92a56-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="92a56-108">輸入</span><span class="sxs-lookup"><span data-stu-id="92a56-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="92a56-109">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92a56-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92a56-110">針對要反映之基礎狀態的傳統整數索引。</span><span class="sxs-lookup"><span data-stu-id="92a56-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="92a56-111">reg： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="92a56-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="92a56-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92a56-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="92a56-113">備註</span><span class="sxs-lookup"><span data-stu-id="92a56-113">Remarks</span></span>

<span data-ttu-id="92a56-114">這項作業會就地執行，而不會明確配置額外的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="92a56-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>