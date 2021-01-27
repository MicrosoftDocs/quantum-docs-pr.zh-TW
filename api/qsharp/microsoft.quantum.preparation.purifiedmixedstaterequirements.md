---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856841"
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