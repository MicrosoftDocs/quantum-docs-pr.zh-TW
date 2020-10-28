---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: ApplyToLittleEndian 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700747"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="f3dcf-102">ApplyToLittleEndian 操作</span><span class="sxs-lookup"><span data-stu-id="f3dcf-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="f3dcf-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f3dcf-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f3dcf-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3dcf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3dcf-105">將作業套用至基礎量子位，以組成位元組由小到大的註冊。</span><span class="sxs-lookup"><span data-stu-id="f3dcf-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="f3dcf-106">這項作業會標示為內部，因為以位元組由小到大的暫存器預期會是「不透明的」，因此只是執行的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f3dcf-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f3dcf-107">輸入</span><span class="sxs-lookup"><span data-stu-id="f3dcf-107">Input</span></span>

### <a name="bareop--qubit--unit-adj--ctl"></a><span data-ttu-id="f3dcf-108">bareOp： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="f3dcf-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="f3dcf-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f3dcf-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f3dcf-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3dcf-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

