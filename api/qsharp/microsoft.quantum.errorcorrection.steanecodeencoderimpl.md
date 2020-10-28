---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697927"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="093df-102">SteaneCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="093df-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="093df-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="093df-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="093df-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="093df-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="093df-105">私用作業可用來同時執行 Steane 程式碼編碼器和解碼器。</span><span class="sxs-lookup"><span data-stu-id="093df-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="093df-106">輸入</span><span class="sxs-lookup"><span data-stu-id="093df-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="093df-107">data： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="093df-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="093df-108">保留1個量子位的陣列，也就是輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="093df-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="093df-109">臨時： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="093df-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="093df-110">保留6個量子位的陣列，這會增加冗余。</span><span class="sxs-lookup"><span data-stu-id="093df-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="093df-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="093df-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

