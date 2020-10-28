---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699681"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


針對一組範例驗證分類器的結果。

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>命名專案

### <a name="nmisclassifications--int"></a>NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)

驗證期間觀察到的情形數目。
### <a name="nvalidationsamples--int"></a>NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)

