---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830069"
---
# <a name="assertphase-operation"></a>AssertPhase 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


判斷提示等於迭加狀態的階段具有預期的值。

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>描述

這項作業會判斷出某些任意實數 $t $ 具有預期值的量子狀態的階段 $ \phi $，可能表示為 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1}) $。

## <a name="input"></a>輸入

### <a name="expected--double"></a>預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

$ \Phi \in (-\pi，\pi] $ 的預期值。


### <a name="qubit--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)

儲存預期狀態的量子位。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

實際和預期之間差異的絕對容錯。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>範例

下列判斷提示成功：處於 `qubit` state $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ ket {0} + e ^ {i 0.5} \ sqrt {1/2} \ ket {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` 處於 state $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ ket {0} + e ^ {-i 0.5} \ sqrt {1/2} \ ket {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` 處於 state $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ ket {0} + e ^ {i 0.2} \ sqrt {1/2} \ ket {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`