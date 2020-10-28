---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: PrepareSparseMultiConfigurationalState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698402"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="d9ff0-102">PrepareSparseMultiConfigurationalState 操作</span><span class="sxs-lookup"><span data-stu-id="d9ff0-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="d9ff0-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d9ff0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d9ff0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9ff0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9ff0-105">藉由將 excitations 新增到初始試用狀態，來準備試用狀態的稀疏多重 configurational 狀態。</span><span class="sxs-lookup"><span data-stu-id="d9ff0-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d9ff0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d9ff0-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="d9ff0-107">initialStatePreparation： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9ff0-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d9ff0-108">單一準備初始試用狀態。</span><span class="sxs-lookup"><span data-stu-id="d9ff0-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="d9ff0-109">excitations： [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="d9ff0-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="d9ff0-110">初始試用狀態的 Excitations，由 excitation 的波幅和 excitation 作用所在的量子位索引所代表。</span><span class="sxs-lookup"><span data-stu-id="d9ff0-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d9ff0-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d9ff0-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d9ff0-112">Hamiltonian 的量子位。</span><span class="sxs-lookup"><span data-stu-id="d9ff0-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9ff0-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9ff0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

