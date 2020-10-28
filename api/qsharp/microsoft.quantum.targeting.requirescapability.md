---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701042"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability 使用者定義型別

命名空間： [Microsoft 量子. 目標](xref:Microsoft.Quantum.Targeting)

包： [](https://nuget.org/packages/)


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