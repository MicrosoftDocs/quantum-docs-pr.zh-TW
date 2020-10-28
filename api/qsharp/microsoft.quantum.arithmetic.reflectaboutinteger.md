---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699562"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="8838a-102">ReflectAboutInteger 操作</span><span class="sxs-lookup"><span data-stu-id="8838a-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="8838a-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8838a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8838a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8838a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8838a-105">反映指定之傳統整數的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="8838a-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="8838a-106">描述</span><span class="sxs-lookup"><span data-stu-id="8838a-106">Description</span></span>

<span data-ttu-id="8838a-107">如果一開始是以 $ \ sum_i \ Alpha_i \ket{i} $ 表示的量子暫存器，其中每個 $ \ket{i} $ 是代表整數 $i $ 的基礎狀態，則會反映有關指定整數 $ \ket{j} $，$ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ Alpha_i \ket{i} $ $ 的基礎狀態的註冊狀態</span><span class="sxs-lookup"><span data-stu-id="8838a-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="8838a-108">輸入</span><span class="sxs-lookup"><span data-stu-id="8838a-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="8838a-109">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8838a-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8838a-110">針對要反映之基礎狀態的傳統整數索引。</span><span class="sxs-lookup"><span data-stu-id="8838a-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="8838a-111">reg： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8838a-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="8838a-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8838a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8838a-113">備註</span><span class="sxs-lookup"><span data-stu-id="8838a-113">Remarks</span></span>

<span data-ttu-id="8838a-114">這項作業會就地執行，而不會明確配置額外的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="8838a-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>