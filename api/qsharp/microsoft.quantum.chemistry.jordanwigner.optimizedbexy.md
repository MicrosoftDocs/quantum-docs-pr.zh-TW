---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698419"
---
# <a name="optimizedbexy-operation"></a>OptimizedBEXY 操作

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


單一 $U $，其會將 Pauli 字串套用至 $ (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1} .。。Z_0 $ on 量子位 $ 0. p $ 條件的索引 $z \in \{ 0、1 \} $ 和 $p $。 亦即 $ $ \begin{align} U\ket {z} \ ket {p} \ ket {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1} .。。Z_0 \ket{\psi} \end{align} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="paulibasis--qubit"></a>pauliBasis： [量子位](xref:microsoft.quantum.lang-ref.qubit)

當此量子位處於狀態 $ \ket {0} $ 時，就會套用 $X $。 當其處於狀態 $ \ket {1} $ 時，就會套用 $Y $。


### <a name="indexregister--littleendian"></a>indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

此註冊的狀態 $ \ket{p} $ 會決定套用 $X $ 或 $Y $ 的量子位。


### <a name="targetregister--qubit"></a>targetRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊已套用 Pauli 運算子的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- 使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662