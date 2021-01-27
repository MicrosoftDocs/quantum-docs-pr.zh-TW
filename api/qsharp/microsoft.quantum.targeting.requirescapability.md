---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855143"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability 使用者定義型別

命名空間： [Microsoft 量子. 目標](xref:Microsoft.Quantum.Targeting)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


編譯器可辨識的屬性，可用來將所需的執行時間功能標示為可呼叫。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>命名專案

### <a name="level--string"></a>層級： [字串](xref:microsoft.quantum.lang-ref.string)

可呼叫所需的執行時間功能層級名稱。
### <a name="reason--string"></a>原因： [字串](xref:microsoft.quantum.lang-ref.string)

說明可呼叫的原因為何需要此執行時間功能。

## <a name="remarks"></a>備註

這個屬性會由編譯器自動新增至 callables，除非這個屬性的實例已經存在於可呼叫的上。 除非在罕見的情況下，編譯器無法正確推斷所需的功能，否則不應使用它。

以下是功能層級名稱的清單，依提高功能或減少限制的順序：

## `"BasicQuantumFunctionality"`

測量結果無法針對相等進行比較。

## `"BasicMeasurementFeedback"`

測量結果只能在作業的 if 語句條件運算式中比較是否相等。 相依于結果的 if 語句區塊，不能包含在區塊外宣告之可變動變數的 set 語句，或是 return 語句。

## `"FullComputation"`

無執行時間限制。 任何 Q # 程式都可以執行。