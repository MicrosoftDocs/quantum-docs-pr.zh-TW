---
title: Q# 檔案結構
description: 描述檔案的結構和語法 Q# 。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833310"
---
# <a name="no-locq-file-structure"></a>Q# 檔案結構

檔案是 Q# 由一系列的 *命名空間*宣告所組成。
每個命名空間宣告都包含使用者定義型別、作業和函式的宣告，而且可以包含每個類型的宣告和任何順序的任意數目。
如需命名空間內宣告的詳細資訊，請參閱 [使用者定義型](xref:microsoft.quantum.guide.types#user-defined-types)別、 [作業](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和 [函數](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)。

唯一可出現在命名空間宣告之外的文字是批註。
尤其是命名空間的檔批註會在宣告之前。 如需詳細資訊，請參閱本文中的 [檔批註](#documentation-comments) 。 

## <a name="namespace-declarations"></a>命名空間宣告

檔案 Q# 通常只有一個命名空間宣告，但不能 (、空白或只包含批註) 或可能包含多個命名空間。
命名空間宣告不能嵌套。

Q#只要沒有任何類型、作業或具有相同名稱的函式宣告，您就可以在多個編譯的檔案中宣告相同的命名空間。
尤其是，在多個檔案的相同命名空間中定義相同的類型是不正確，即使宣告相同也是一樣。

命名空間宣告包含關鍵字 `namespace` 、後面接著命名空間的名稱，以及包含在命名空間中的宣告（以大括弧括住） `{ }` 。
命名空間名稱會遵循以句點分隔的一或多個合法符號序列的 .NET 模式 `.` 。
例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 是有效的命名空間名稱。
依照慣例，將命名空間名稱中的符號大寫，不過這不是必要的。

在檔案中向下宣告的類型或 callables 的參考正確地解析;類型、作業或函式宣告不需要在其參考之前。

## <a name="open-directives"></a>Open 指示詞

在命名空間區塊內，使用指示詞彙 `open` 入在特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱參考它們。
這類指示詞 `open` 由 `open` 關鍵字組成，後面接著要開啟的命名空間和結束的分號。

> [!NOTE] 
> 所有指示詞都 `open` 必須出現 `function` 在 `operation` `newtype` 命名空間區塊中的任何、或宣告之前。

（選擇性）您可以定義已開啟之命名空間的簡短名稱。 如果定義了簡短名稱，您就必須根據定義的簡短名稱來限定該命名空間中的所有元素。 例如，假設有下列命名空間宣告和開放式指示詞，

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

如果宣告的作業使用的作業 `Op` `Microsoft.Quantum.Intrinsic` ，您只需要使用來呼叫它 `Op` 。
不過，若要從呼叫特定函式 `Fn` `Microsoft.Quantum.Math` ，您必須使用來呼叫它 `Math.Fn` 。

指示詞會 `open` 套用至檔案中的整個命名空間區塊。
因此，如果您在稍早的相同檔案中定義其他命名空間 Q# `NS` ，則在第二個命名空間中定義的任何作業/函式/型別都不會存取任何來自或的任何作業/函式/類型， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非您重複上述的 open 指示 

若要參考 *未* 在目前命名空間中開啟之另一個命名空間中定義的類型或可呼叫，您必須使用其完整名稱來參考它。
例如，假設有一個 `Op` 從命名空間命名的作業 `X.Y` ：

* `X.Y.Op`除非 `X.Y` 先前已在目前區塊中開啟命名空間，否則您必須使用完整名稱來參考它。 
* 即使 `X` 已開啟命名空間，也無法將作業參考為 `Y.Op` 。
* 如果您 `Z` `X.Y` 在該命名空間和檔案中定義了的簡短名稱，則必須將參考 `Op` 為 `Z.Op` 。 

通常最好是使用指示詞來包含命名空間 `open` 。
如果有兩個命名空間定義相同名稱的結構，而且目前的來源使用來自兩者的結構，則需要使用完整名稱。

Q# 遵循與其他 .NET 語言命名相同的規則。
但是，不 Q# 支援命名空間的相對參考。
例如，如果命名空間 `a.b` 是開啟的，則名為的作業參考 `c.d` 不*not*會解析為具有完整名稱的作業 `a.b.c.d` 。

## <a name="formatting"></a>格式化

大部分的語句和指示詞都 Q# 是以結束分號結尾 `;` 。
語句和宣告（如 `for` 和） `operation` 會以語句區塊作為結尾 (請參閱下一節) 不需要終止分號。
每個語句描述都會注明是否需要結束分號。

語句（如運算式、宣告和指示詞）可以跨多行分割。
避免將多個語句放在同一行上。

## <a name="statement-blocks"></a>語句區塊

Q# 語句會分組為語句區塊，這些區塊包含在大括弧中 `{ }` 。 語句區塊的開頭為開頭 `{` ，結尾為結尾 `}` 。

以詞法地括住在另一個區塊內的語句區塊會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。

## <a name="comments"></a>註解

批註是以兩個正斜線開始， `//` 然後繼續直到行尾為止。
批註可以出現在來源檔案中的任何位置 Q# 。

## <a name="documentation-comments"></a>文件註解

以三個正斜線開頭的批註， `///` 會在編譯器于命名空間、作業、特製化、函數或型別定義之前出現時，由編譯器進行特殊處理。
在這種情況下，編譯器會將它們視為已定義之可呼叫或使用者定義類型的檔，與其他 .NET 語言相同。

在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為 [Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指出檔的不同部分。
在 Markdown 中，在 `@"<ref target>"` 中使用擴充功能來交互參考作業、函式和使用者定義類型 Q# 。 取代 `<ref target>` 為參考之程式碼物件的完整名稱。
不同的檔引擎也可能支援其他 Markdown 延伸模組。

例如：

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

下列名稱是有效的檔批註標頭。

- **摘要**：函式或作業行為的簡短摘要，或類型的用途。 摘要的第一個段落用於暫止資訊。 它應該是純文字。
- **描述**：函式或作業行為的描述，或類型的用途。 總而言之，摘要和描述會形成函式、作業或類型所產生的檔檔。
  描述支援內嵌 LaTeX 格式的符號和方程式。
- **輸入**：作業或函數之輸入元組的描述。
  可以包含其他 Markdown 子區段，指出輸入元組的每個元素。
- **輸出**：作業或函數所傳回之元組的描述。
- **類型參數**：空白區段，包含每個泛型型別參數一個額外的子區段。
- **範例**：使用中的作業、函數或類型的簡短範例。
- **備註**：其他 prose，描述作業、函式或類型的某些層面。
- **請參閱**：指出相關函式、作業或使用者定義類型的完整名稱清單。
- **參考**：已記載專案的參考與引文清單。

## <a name="next-steps"></a>後續步驟

深入瞭解中的 [作業和功能](xref:microsoft.quantum.guide.operationsfunctions) Q# 。