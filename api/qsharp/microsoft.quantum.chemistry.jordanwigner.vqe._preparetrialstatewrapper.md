---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: 8e1a39cbd307a467ab7f0466c90722e1c8c46d4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224678"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="a7681-102">_prepareTrialStateWrapper 操作</span><span class="sxs-lookup"><span data-stu-id="a7681-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="a7681-103">命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="a7681-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="a7681-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a7681-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a7681-105">PrepareTrialState 上的私用包裝函式，藉由定義 adjoint 來使其與 EstimateFrequencyA 相容。</span><span class="sxs-lookup"><span data-stu-id="a7681-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="a7681-106">EstimateFrequencyA 具有以 QuantumSimulator 為目標時的內建模擬功能，可加速其執行。</span><span class="sxs-lookup"><span data-stu-id="a7681-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a7681-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a7681-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="a7681-108">inputState： ([Int](xref:microsoft.quantum.lang-ref.int)，[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[] ) </span><span class="sxs-lookup"><span data-stu-id="a7681-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="a7681-109">要執行 PrepareTrialState 所需的 Jordan-Wigner 輸入。</span><span class="sxs-lookup"><span data-stu-id="a7681-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a7681-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a7681-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a7681-111">量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="a7681-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7681-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7681-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

