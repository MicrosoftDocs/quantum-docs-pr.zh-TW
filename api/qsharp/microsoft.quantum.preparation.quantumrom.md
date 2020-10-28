---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700419"
---
# <a name="quantumrom-function"></a>QuantumROM 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


使用量子 ROM 技術來代表指定的密度矩陣。

假設有一份 $N $ 係數 $ \ Alpha_j $ 的清單，這會傳回單一 $U $，其使用量子 ROM 技術來準備近似 $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ 淨化的密度對照表 $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j} $。 在此近似值中，錯誤 $ \epsilon $ 為 $ | p_j-\frac{| Alpha_j |}{\ sum_k | \ Alpha_k |} |\le \epsilon/N $ 和 $ \| \tilde\rho-\rho \| \le \epsilon $。 換句話說，$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ ket {0} ^ {m} = \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}。
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>輸入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目標錯誤 $ \epsilon $。


### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

$N $ 係數的陣列，指定基礎狀態的機率。
負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a>Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int)) # A4，[Double](xref:microsoft.quantum.lang-ref.double)， ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl) 

## <a name="first-parameter"></a>第一個參數

元組， `(x,(y,z))` 其中 `x = y + z` 是配置的量子位總數， `y` 是註冊的量子位數目 `LittleEndian` ，而 `z` 是垃圾量子位的數目。

## <a name="second-parameter"></a>第二個參數

係數陣列的單一標準 $ \ sum_j | \ Alpha_j | $。

## <a name="third-parameter"></a>第三個參數

單一 $U $。

## <a name="references"></a>參考

- 使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662