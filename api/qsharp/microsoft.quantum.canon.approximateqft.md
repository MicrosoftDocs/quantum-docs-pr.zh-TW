---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850330"
---
# <a name="approximateqft-operation"></a>ApproximateQFT 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將大約的量子傅立葉轉換 (AQFT) 套用至量子暫存器。

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

近似值參數，決定 QFT 電路中所發生之受控制 Z 旋轉的水準剪除。

近似值參數 a 決定 Z 旋轉的剪除層級，亦即，∈ {0 ... n} 和所有 Z 旋轉2π/2k，其中 k>a 會從 QFT 電路中移除。 已知 >= log ₂ (n) + log ₂ (1/ε) + 3 1 可以系結 | |QFT-AQFT | |<ε。


### <a name="qs--bigendian"></a>qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

套用近似量子傅立葉轉換之 n 量子位的量子暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

AQFT 需要2π/2k 和 Hadamard 閘道格式的 Z 旋轉閘道。

輸入和輸出會假設以位元組由大到小的編碼方式進行編碼。

## <a name="references"></a>參考資料

- [*Roetteler，Beth*，Appl.exe. Commun。電腦.19 (3) ： 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv： quant-ph/0201067v1](https://arxiv.org/abs/quant-ph/0201067)