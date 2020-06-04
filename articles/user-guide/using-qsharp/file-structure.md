---
title: 'Q # 檔案結構'
description: '說明 Q # 檔案的結構和語法。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327453"
---
# <a name="q-file-structure"></a>Q # 檔案結構

每個 Q # 作業、函式和使用者定義類型都定義在命名空間中。

Q # 檔案是由一系列的*命名空間*宣告所組成。
每個命名空間宣告都包含使用者定義類型、作業和函式的宣告。
命名空間宣告可包含每個宣告類型的任意數目，並依任何順序。
請遵循下列連結，以[取得在命名空間中宣告](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)[使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)、[作業](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和函式的詳細資訊。

唯一可以出現在命名空間宣告外的文字是批註。
特別是在宣告之前，命名空間的檔批註（以下詳細資料）。

## <a name="namespace-declarations"></a>命名空間宣告

問 # 檔案通常只會有一個命名空間宣告，但可能會有 none （而且是空的或只包含批註），或可能包含多個命名空間。
命名空間宣告不可以是嵌套的。

同一個命名空間可以宣告在一起編譯的多個 Q # 檔案中，只要沒有任何類型、作業或具有相同名稱的函式宣告即可。
特別是，在多個檔案的相同命名空間中定義相同的型別是不正確，即使宣告相同也是一樣。

命名空間宣告包含關鍵字 `namespace` ，後面接著命名空間名稱、左大括弧 `{` 、命名空間中包含的宣告和右大括弧 `}` 。
命名空間名稱會遵循一或多個以句點分隔之合法符號序列的 .NET 模式 `.` 。
例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 都是有效的命名空間名稱。
依照慣例，命名空間名稱中的符號是大寫的，但這不是必要的。

在檔案中進一步宣告之類型或 callables 的參考會正確解析;型別、運算或函式宣告不需要在參考之前。

## <a name="open-directives"></a>Open 指示詞

在命名空間區塊內，指示詞可用 `open` 來匯入特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱加以參考。
這類指示詞 `open` 包含 `open` 關鍵字，後面接著要開啟的命名空間和終止的分號。

> [!NOTE] 
> 所有指示詞 `open` 必須出現在 `function` `operation` `newtype` 命名空間區塊中的任何、或宣告之前。

（選擇性）可能會定義已開啟之命名空間的簡短名稱，讓來自該命名空間的所有元素都可以（和需要）以定義的簡短名稱限定。 例如，假設有下列命名空間宣告和 open 指示詞，

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

如果我們宣告的作業使用來自的 `Op` 作業 `Microsoft.Quantum.Intrinsic` ，我們只需要使用來呼叫它 `Op` 。
不過，如果我們想要從呼叫特定函 `Fn` 式 `Microsoft.Quantum.Math` ，則需要使用來呼叫它 `Math.Fn` 。

指示詞 `open` 適用于檔案內的整個命名空間區塊。
因此，如果我們要在與上述相同的問答 # 檔案中定義其他命名空間 `NS` ，則在第二個命名空間中定義的任何作業/函式/類型，都將無法存取來自或的任何專案， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非我們重複其中的 open 指示詞。 

在*未*于目前命名空間中開啟的另一個命名空間中定義的類型或可呼叫，必須以其完整名稱來參考。
例如， `Op` `X.Y` `X.Y.Op` 除非 `X.Y` 先前已在目前區塊中開啟命名空間，否則從命名空間命名的作業必須由其完整名稱參考。 如上所述，即使已 `X` 開啟命名空間，也無法以的形式參考此作業 `Y.Op` 。
如果已 `Z` `X.Y` 在該命名空間和檔案中定義的簡短名稱，則必須 `Op` 將稱為 `Z.Op` 。 

通常最好是使用指示詞來加入命名空間 `open` 。
如果兩個命名空間定義具有相同名稱的結構，而且目前來源使用兩者的結構，則必須使用完整名稱。

問 # 遵循與其他 .NET 語言相同的命名規則。
不過，Q # 不支援命名空間的相對參考。
也就是說，如果已開啟命名空間 `a.b` ，名為之作業的參考 `c.d` 將*不*會解析為具有完整名稱的作業 `a.b.c.d` 。

## <a name="formatting"></a>格式化

大部分的 Q # 語句和指示詞的結尾都是終止的分號 `;` 。
語句和宣告（如 `for` 和 `operation` ），其結尾為語句區塊（如下所示），不需要終止分號。
每個語句描述都會說明結尾分號是否為必要。

語句（例如運算式、宣告和指示詞）可能會細分成多行。
應避免在單一行上使用多個語句。

## <a name="statement-blocks"></a>語句區塊

Q # 語句會分組到語句區塊中。
語句區塊會以開頭開頭 `{` ，並以結尾結束 `}` 。

在另一個區塊中以詞法括住的語句區塊，會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。

## <a name="comments"></a>註解

批註會以兩個正斜線開頭， `//` 並繼續直到行尾為止。
批註可能會出現在 Q # 來源檔案中的任何位置。

## <a name="documentation-comments"></a>文件註解

以三個正斜線開頭的批註， `///` 會在它們緊接在命名空間、作業、特製化、函式或類型定義之前，由編譯器特別處理。
在此情況下，會將其內容視為已定義之可呼叫或使用者定義類型的檔，就像其他 .NET 語言一樣。

在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為[Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指出檔的不同部分。
如需 Markdown 的延伸模組，可以使用包含 Q # 中作業、函式和使用者定義類型的交互參考 `@"<ref target>"` ，其中會 `<ref target>` 由所參考之程式碼物件的完整名稱取代。
（選擇性）檔引擎也可能支援其他 Markdown 延伸模組。

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

下列名稱會被辨識為檔批註標頭。

- **摘要**：函數或作業行為的簡短摘要，或類型的用途。 摘要的第一個段落用於暫留資訊。 它應該是純文字。
- **描述**：函數或作業行為的描述，或類型的用途說明。 摘要和描述會串連，以形成函式、作業或類型所產生的檔檔案。
  描述可以包含內嵌 LaTeX 格式的符號和方程式。
- **輸入**：作業或函數之輸入元組的描述。
  可能包含其他 Markdown 子區段，指示輸入元組的每個個別元素。
- **輸出**：作業或函式所傳回之元組的描述。
- **型別參數**：空的區段，其中包含每個泛型型別參數的一個額外子節。
- **範例**：使用中的作業、函數或類型的簡短範例。
- **備註**：其他 prose，描述作業、函數或類型的某些層面。
- **另請參閱**：表示相關函數、作業或使用者定義類型的完整名稱清單。
- **參考**：要記載之專案的參考和引文清單。

## <a name="next-steps"></a>下一步

瞭解 Q # 中的[作業和功能](xref:microsoft.quantum.guide.operationsfunctions)。