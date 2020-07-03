---
title: 'Q # 檔案結構'
description: '說明 Q # 檔案的結構和語法。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884170"
---
# <a name="q-file-structure"></a>Q # 檔案結構

Q # 檔案是由一系列的*命名空間*宣告所組成。
每個命名空間宣告都包含使用者定義型別、作業和函式的宣告，而且可以包含每個宣告類型的任意數目和任何順序。
如需命名空間內宣告的詳細資訊，請參閱[使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)、[作業](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和[函數](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)。

唯一可以出現在命名空間宣告外的文字是批註。
特別是，命名空間的檔批註會在宣告之前。 如需詳細資訊，請參閱本文中的[檔批註](#documentation-comments)。 

## <a name="namespace-declarations"></a>命名空間宣告

問 # 檔案通常只會有一個命名空間宣告，但可以有 none （而且也可以是空的或只包含批註）或包含多個命名空間。
命名空間宣告不能嵌套。

只要沒有任何類型、作業或具有相同名稱的函式宣告，您就可以在一起編譯的多個 Q # 檔案中宣告相同的命名空間。
特別是，在多個檔案的相同命名空間中定義相同的型別是不正確，即使宣告相同也是一樣。

命名空間宣告包含關鍵字 `namespace` ，後面接著命名空間的名稱，以及包含在以大括弧括住之命名空間中的宣告 `{ }` 。
命名空間名稱會遵循一或多個以句點分隔之合法符號序列的 .NET 模式 `.` 。
例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 都是有效的命名空間名稱。
依照慣例，會將命名空間名稱中的符號大寫，不過，這不是必要的。

在檔案中進一步宣告的類型或 callables 的參考已正確解析;型別、運算或函式宣告不需要在參考之前。

## <a name="open-directives"></a>Open 指示詞

在命名空間區塊內，使用指示詞彙 `open` 入特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱加以參考。
這類指示詞 `open` 包含 `open` 關鍵字，後面接著要開啟的命名空間和終止的分號。

> [!NOTE] 
> 所有指示詞 `open` 必須出現在 `function` `operation` `newtype` 命名空間區塊中的任何、或宣告之前。

（選擇性）您可以為已開啟的命名空間定義簡短名稱。 如果定義了簡短名稱，您必須依據定義的簡短名稱，限定該命名空間中的所有元素。 例如，假設有下列命名空間宣告和 open 指示詞，

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

如果宣告的作業使用來自的 `Op` 作業 `Microsoft.Quantum.Intrinsic` ，您只需要使用來呼叫它 `Op` 。
不過，若要從呼叫特定函式 `Fn` `Microsoft.Quantum.Math` ，您必須使用呼叫它 `Math.Fn` 。

指示詞 `open` 適用于檔案內的整個命名空間區塊。
因此，如果您在與先前相同的問答 # 檔案中定義其他命名空間，則在 `NS` 第二個命名空間中定義的任何作業/函式/類型，都將無法存取來自或的任何專案， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非您重複其中的 open 指示詞。 

若要參考在目前命名空間中*未*開啟的另一個命名空間中定義的類型或可呼叫，您必須以其完整名稱來參考它。
例如，指定 `Op` 命名空間中的作業 `X.Y` ：

* `X.Y.Op`除非 `X.Y` 先前已在目前區塊中開啟命名空間，否則您必須使用完整名稱來參考它。 
* 即使 `X` 已開啟命名空間，也無法以的形式參考此作業 `Y.Op` 。
* 如果您已 `Z` `X.Y` 在該命名空間和檔案中定義的簡短名稱，則必須 `Op` 以形式參考 `Z.Op` 。 

通常最好是使用指示詞來加入命名空間 `open` 。
如果兩個命名空間定義具有相同名稱的結構，而且目前來源使用兩者的結構，則必須使用完整名稱。

問 # 遵循與其他 .NET 語言相同的命名規則。
不過，Q # 不支援命名空間的相對參考。
例如，如果命名空間是開啟的，則名為之作業 `a.b` 的參考不 `c.d` 會解析為具有完整名稱*not*的作業 `a.b.c.d` 。

## <a name="formatting"></a>格式化

大部分的 Q # 語句和指示詞的結尾都是終止的分號 `;` 。
語句和宣告（如 `for` 和 `operation` ），其結尾為語句區塊（請參閱下一節），不需要終止分號。
每個語句描述都會說明結尾分號是否為必要。

語句（例如運算式、宣告和指示詞）可以細分成多行。
避免將多個語句放在同一行上。

## <a name="statement-blocks"></a>語句區塊

Q # 語句會分組成語句區塊，其包含以大括弧括住 `{ }` 。 語句區塊會以開頭開頭 `{` ，並以結尾結束 `}` 。

在另一個區塊中以詞法括住的語句區塊，會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。

## <a name="comments"></a>註解

批註會以兩個正斜線開頭， `//` 並繼續直到行尾為止。
批註可以出現在 Q # 來源檔案中的任何位置。

## <a name="documentation-comments"></a>文件註解

以三個正斜線開頭的批註， `///` 會在它們緊接在命名空間、作業、特製化、函式或類型定義之前，由編譯器特別處理。
在此情況下，編譯器會將它們視為已定義之可呼叫或使用者定義類型的檔，與其他 .NET 語言相同。

在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為[Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指示不同的檔部分。
在 Markdown 中，使用 [ `@"<ref target>"` Q #] 中的交互參考作業、函式和使用者定義類型的擴充功能。 取代 `<ref target>` 為所參考程式碼物件的完整名稱。
不同的檔引擎也可能支援額外的 Markdown 延伸模組。

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

- **摘要**：函數或作業行為的簡短摘要，或類型的用途。 摘要的第一個段落用於暫留資訊。 它應該是純文字。
- **描述**：函數或作業行為的描述，或類型的用途。 總之，[摘要] 和 [描述] 會形成函數、作業或類型所產生的檔檔案。
  此描述支援內嵌 LaTeX 格式的符號和方程式。
- **輸入**：作業或函數之輸入元組的描述。
  可以包含其他 Markdown 子區段，指示輸入元組的每個元素。
- **輸出**：作業或函式所傳回之元組的描述。
- **型別參數**：空的區段，其中包含每個泛型型別參數的一個額外子節。
- **範例**：使用中的作業、函數或類型的簡短範例。
- **備註**：其他 prose，描述作業、函數或類型的某些層面。
- **另請參閱**：表示相關函數、作業或使用者定義類型的完整名稱清單。
- **參考**：已記載專案的參考和引文清單。

## <a name="next-steps"></a>接下來的步驟

瞭解 Q # 中的[作業和功能](xref:microsoft.quantum.guide.operationsfunctions)。