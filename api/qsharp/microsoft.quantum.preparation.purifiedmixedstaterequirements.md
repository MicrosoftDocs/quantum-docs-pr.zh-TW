---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229982"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回必須配置才能套用所傳回之作業的量子位總數 @"microsoft.quantum.preparation.purifiedmixedstate" 。

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>輸入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目標錯誤 $ \epsilon $。


### <a name="ncoefficients--int"></a>nCoefficients： [Int](xref:microsoft.quantum.lang-ref.int)

要在準備混合狀態時指定的係數數目。



## <a name="output--mixedstatepreparationrequirements"></a>輸出： [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

描述每個所需的量子位數目，以及函式所使用的每個索引和垃圾暫存器 @"microsoft.quantum.preparation.purifiedmixedstate" 。

## <a name="see-also"></a>另請參閱

- [PurifiedMixedState。](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)