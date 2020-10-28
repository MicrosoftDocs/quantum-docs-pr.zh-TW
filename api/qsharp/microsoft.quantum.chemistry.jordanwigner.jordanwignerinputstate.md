---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698439"
---
# <a name="jordanwignerinputstate-user-defined-type"></a><span data-ttu-id="9529e-102">JordanWignerInputState 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="9529e-102">JordanWignerInputState user defined type</span></span>

<span data-ttu-id="9529e-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9529e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9529e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9529e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9529e-105">從 c # 傳遞到 Q # 的資料格式，以表示準備初始狀態，表示資料的意義是由接收它的演算法所決定。</span><span class="sxs-lookup"><span data-stu-id="9529e-105">Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

