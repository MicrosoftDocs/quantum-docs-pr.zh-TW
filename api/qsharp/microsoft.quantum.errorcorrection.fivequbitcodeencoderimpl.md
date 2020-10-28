---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697970"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="f5b82-102">FiveQubitCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="f5b82-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="f5b82-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f5b82-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f5b82-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5b82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5b82-105">私用作業可用來同時執行5個量子位編碼器和解碼器。</span><span class="sxs-lookup"><span data-stu-id="f5b82-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f5b82-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f5b82-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="f5b82-107">data： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f5b82-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f5b82-108">保留1個量子位的陣列，也就是輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="f5b82-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="f5b82-109">臨時： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f5b82-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f5b82-110">保存4個量子位的陣列，這會增加冗余。</span><span class="sxs-lookup"><span data-stu-id="f5b82-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5b82-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5b82-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f5b82-112">備註</span><span class="sxs-lookup"><span data-stu-id="f5b82-112">Remarks</span></span>

<span data-ttu-id="f5b82-113">所選擇的特定編碼器取自 Kliuchnikov 和 d. Maslov、「Clifford 電路優化」 Phys，Phys. A 88、052307 (2013) ; https://arxiv.org/abs/1305.0810、圖 4b) ，且需要總共11個閘道。</span><span class="sxs-lookup"><span data-stu-id="f5b82-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>