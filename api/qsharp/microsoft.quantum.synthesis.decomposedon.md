---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855519"
---
# <a name="decomposedon-function"></a>DecomposedOn 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


分解變數上的排列

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>描述

指定排列 $ \pi $ (`perm`) 和索引 $i $ (`index`) ，這個方法會傳回三個排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，讓 $ \ pi_l $ 和 $ \ pi_r $ 的影像不會變更其元素中 $i $ 和 $ \pi ' $ 的影像中的位，而不會變更其專案中的位 $i $。

## <a name="input"></a>輸入

### <a name="perm--int"></a>為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) 



## <a name="example"></a>範例

假設輸入是為永久 = [0，2，3，5，7，1，4，6] 和 index = 0，則此函式會根據下表來計算三個排列，這會以 `perm` 二進位標記法來列出以二進位標記法排列，並以群組 A 中的元素和群組 D 中的影像來列出排列。 資料行列出位索引。

|  A |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

索引的所有值不等於 0 (= index) 會從 A 複製到 B，而從 D 複製到 C。

|  A |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

接下來，會針對第一個專案放置0，而第一個元素的第0個專案中的第一個專案具有空的索引，而在第一個案例中，前置詞 (符合第一個案例中的第一個資料列（索引 0 0) 的另一個資料列）
之後，會在區塊 C 的相同資料列中加入1，然後在區塊 C 中將對應的前置詞加上0。 此程式會重複，直到所有索引都放在區塊 B 和 C 中的資料行0為止。

|  A |  B |  C |  D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

我們可以從資料表讀取三個新的排列：

- $ \ pi_l $ 中的元素，B 中的影像 (左) 
- $ \ pi_r $ （含 D 的元素），C 中的影像 (right) 
- $ \pi ' $ （具有 B 中的元素），C 中的影像 (餘數) 

請注意，在索引1和2中，設計位值不會變更 $ \ pi_l $ 和 $ \ pi_r $，而且在 $ \ pi_ ' $ 中的索引0不會變更位值。  另請注意，$ \ pi_l $ 和 $ \ pi_r $ 必須是自反向。

衍生和傳回的排列如下： left = [0，1，2，3，4，5，6，7] right = [0，1，3，2，4，5，7，6] 餘數 = [0，3，2，5，6，1，4，7]