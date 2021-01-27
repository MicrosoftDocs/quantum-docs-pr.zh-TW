---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854902"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


描述由一系列的參數化和控制的旋轉、旋轉角度的指派，以及模型辨識的兩個類別之間的偏差所組成的量子分類器模型。

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>命名專案

### <a name="structure--controlledrotation"></a>結構： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

用來分類輸入的受控旋轉序列。
### <a name="parameters--double"></a>參數： [Double](xref:microsoft.quantum.lang-ref.double)[]

指派給指定分類結構的旋轉角度。
### <a name="bias--double"></a>偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

此分類器所辨識的兩個類別之間的偏差。

## <a name="references"></a>參考資料

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)