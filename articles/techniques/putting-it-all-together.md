---
title: Q# 技術 - 將其全部放在一起
description: 流覽演示量子傳送的基本 Q# 程式。
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030560"
---
# <a name="putting-it-all-together-teleportation"></a>將所有功能放在一起:傳送 #
讓我們回到[量子電路](xref:microsoft.quantum.concepts.circuits)中定義的傳送電路的例子。 我們將用它來說明我們迄今學到的概念。 下面為不熟悉該理論的人提供量子傳送的說明,隨後在Q# 中介紹代碼實現。 

## <a name="quantum-teleportation-theory"></a>量子傳送:理論
量子傳送是一種將未知量子狀態(我們稱之為"__消息__")從一個位置的量子位發送到另一個位置的量子位的技術(我們將這些量子位分別稱為"__此處__"和"__此處__"。 我們可以使用 Dirac 表示法表示我們__的消息__作為向量: 

$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$

__消息__qubit 的狀態是未知的,因為我們不知道 $_alpha$ 和 $_beta$的值。

### <a name="step-1-create-an-entangled-state"></a>第一步:建立糾纏狀態
為了__發送消息,我們需要____在這裡__的量子位與那裡的量子位糾纏在一__起__。 這是通過應用哈達馬德門來實現的,然後是 CNOT 門。 讓我們來看看這些門操作背後的數學。

我們將從__此處__和__此處__的 qubit 開始{0},兩者都位於 $ket $ 狀態。 糾纏這些量子位后,它們處於以下狀態:

{1}$$$\ket_phi_= = _frac [sqrt](\ket{2} {00} ={11}\ket) $$$

### <a name="step-2-send-the-message"></a>第二步:傳送訊息
為了__發送消息,我們__首先應用一個帶有__消息__qubit的 CNOT 門,__此處__將 qubit 作為輸入(__消息__qubit 是控制項,__此處__的 qubit 是目標 qubit,在這種情況下)。 可以寫入此輸入狀態:

$$$\ket\psi_ket_ket_phi_]= (\alpha_ket{0} {1}={1}\beta_ket)(\frac [sqrt](\ket{2} {00} {11}= \ket)$$

這會擴展到:

$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$

作為提醒,當控件 qubit 為 1 時,CNOT 門將翻轉目標量子位。 因此,例如,$_ket{000}$ 的輸入不會導致任何變化,因為第一個 qubit(控件)為 0。 但是,以第一個 qubit 為 1{100}的情況為例 , 例如 ,輸入為 $_ket $。 在這種情況下,輸出為 $_ket{110}$,因為第二個 qubit(目標)由 CNOT 門翻轉。

現在,讓我們考慮我們的輸出,一旦CNOT門已經按照我們上面的意見採取行動。 結果如下：

{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$

發送__消息__的下一步是將 Hadamard 門應用於__消息__qubit(這是每個術語的第一個 qubit)。 

作為提醒,哈達馬德門執行以下操作:

輸入 | 輸出
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $_frac{1}\sqrt{2}[(\ket{0} ={1}\ket )$
$\ket{1}$  | $_frac{1}\sqrt{2}\(\ket{0} -{1}\ket )$

如果我們將 Hadamard 門應用於上述輸出的每個術語的第一個 qubit,我們會得到以下結果:

$${2}_frac_alpha_sqrt{1}_(\frac _sqrt{2}{0} \c{1}\c =ket )\ket{00} \c =\c_\c_\c_\c_\c_sqrt{2}[(\frac{1}_sqrt{2}\c{0} {1}_ket)\ket{11} ]{2}[frac_beta]_sqrt{1}_(\frac{1}_sqrt{10} {2}\c _c_ket{0} )\ket{1} {01} {2}=\c_beta_sqrt_(_frac{1}_sqrt{2}_(\ket{0} - \ket))\ket $$$$$$$

請注意,每個術語都有兩個{1}$frac \sqrt{2}\$$因數。 我們可以將這些乘數乘以給出以下結果:

$${2}[frac_alpha] (\ket{0} {1}={00} \ket{2}{0} )\ket{1}= \ket{11} \ket )\ket{2} {0} {1}=\c_beta](\ket - \ket)\ket{10} {2}=\c_beta](\ket{0} - \ket)\ket)\ket{1} {01}

$_frac{1}{2}$ 因數是每個術語的通用,因此我們現在可以在括弧外將其採用:

$${1}{2}\frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$

然後,我們可以將每個術語的括弧相乘:

$$ \frac{1}{2}\big[\Alpha\ket{000} + \Alpha\ket{100} +{011} \alpha\ket{111} + \Alpha\ket + \beta\ket{010} -{110} \beta\ket + \Beta\ket{001} - \beta\ket{101}\big] $$

### <a name="step-3-measure-the-result"></a>第三步:測量結果

由於__這裡____和那裡__糾纏,__任何測量在這裡__將影響__那裡__的狀態。 如果我們測量第一個和第二量子位(__消息__和__這裡__),我們可以知道__處於__什麼狀態,由於這種糾纏的屬性。 

* 如果我們測量並獲取結果 00,疊加將摺疊,僅保留與此結果一致的術語。 那是 $_alpha\ket{000} \beta\ket{001}$。 這可以重構為 $\ket{00}(\alpha\ket{1}{0} \beta_ket )$。 因此,如果我們將第一個和第二個 qubit 測量為 00,我們知道第三個 qubit,__有__,處於狀態 $(\Alpha\ket\beta\ket)$。{0} {1}
* 如果我們測量並獲取結果 01,疊加將摺疊,僅保留與此結果一致的術語。 那是 $_alpha\ket{011} \beta\ket{010}$。 這可以重構為 $\ket{01}(\alpha\ket{0}{1} \beta_ket )$。 因此,如果我們測量第一個和第二個量子位為 01,我們知道第三個 qubit,__有__,在狀態 $(\Alpha\ket\beta\ket)$。{1} {0}
* 如果我們測量並獲取結果 10,疊加將摺疊,僅保留與此結果一致的術語。 那是 $_alpha\ket{100} -\beta\ket{101}$。 這可以重構為 $\ket{10}(\alpha\ket{1}{0} -_beta_ket )$。 因此,如果我們將第一個和第二個量子位度量為 10,我們知道第三個 qubit,__有__,處於狀態 $(\alpha_ket-_beta_ket)$。{0} {1}
* 如果我們測量並獲取結果 11,疊加將摺疊,僅保留與此結果一致的術語。 那是 $_alpha\ket{111} -\beta\ket{110}$。 這可以重構為 $\ket{11}(\alpha\ket{0}{1} -_beta_ket )$。 因此,如果我們將第一個和第二個量子位度量為 11,我們知道第三個 qubit,__有__,處於狀態 $(\alpha_ket-_beta_ket)$。{1} {0}

### <a name="step-4-interpret-the-result"></a>第 4 步:解釋結果

作為提醒,我們希望傳送的原始__資訊__是:

$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$

我們需要將__那裡的__qubit放入此狀態,以便接收的狀態是預期狀態。 

* 如果我們測量並得到的結果為 00,則第三個 qubit,__有__,處於狀態 $(\alpha\ket\beta\ket)$。{0} {1} 由於這是預期__的消息__,因此無需更改。
* 如果我們測量並得到 01 的結果,則第三個 qubit,__有__,處於狀態 $(\alpha\ket\beta_ket)$。{1} {0} 這與預期__消息__不同,但是應用 NOT 門會給我們所需的狀態 $(\alpha\ket\beta\ket)$。{0} {1}
* 如果我們測量並得到 10 的結果,則第三個 qubit,__有__,在狀態 $(\alpha\ket{0} -_beta_ket)$。{1} 這與預期__消息__不同,但是應用 Z 門會給我們所需的狀態 $(\Alpha\ket\beta\ket)$。{0} {1}
* 如果我們測量並得到 11 的結果,那麼第三個 qubit,__有__,是在狀態 $(\alpha\ket{1} -_beta_ket)$。{0} 這與預期__消息__不同,但是應用 NOT 門後跟 Z 門會給我們所需的狀態 $(\alpha\ket\beta_ket)$。{0} {1}

總之,如果我們測量第一個量子位為 1,則應用 Z 門。 如果我們測量第二個量子位為 1,則應用 NOT 門。

### <a name="summary"></a>摘要
下面顯示了實現傳送的教科書量子電路。 從左至右移動,您可以看到:
- 第1步:通過應用哈達馬德門和CNOT門,__在這裡____和那裡__糾纏。
- 第 2 步 __:使用__CNOT 門和哈達馬德門發送消息。
- 步驟 3:測量第一和第二個量子位,__消息__和__這裡__。
- 步驟 4:根據步驟 3 中的測量結果應用不門或 Z 門。

!['傳送(msg: Qubit, 有 : Qubit) : 單位'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>量子傳送:代碼

我們有用於量子傳送的電路:

!['傳送(msg: Qubit, 有 : Qubit) : 單位'](~/media/teleportation.svg)

現在,我們可以將此量子電路中的每個步驟轉換為 Q#。

### <a name="step-0-definition"></a>步驟 0:定義
當我們執行傳送時,我們必須知道我們想要__發送的資訊__,以及我們希望發送的位置(__那裡__)。 因此,我們首先定義一個新的傳送運運運,該操作給定兩個 qubit`msg`作為`there`參數 , 和 :

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

我們還需要分配一個通過`here``using`塊實現的量子位:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>第一步:建立糾纏狀態
然後`here`,我們可以`there`@"microsoft.quantum.intrinsic.h"使用@"microsoft.quantum.intrinsic.cnot"和操作創建和之間的糾纏對:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>第二步:傳送訊息
然後,我們使用下一個 $_運算符名稱[CNOT_$ 和 $H$ 門來移動我們的消息庫比特:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>第3步&4:測量和解釋結果
最後,我們使用@"microsoft.quantum.intrinsic.m"執行測量並執行必要的門操作以獲得所需的狀態,`if`如語句所述:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>第 5 步:重新啟動量子位寄存器

在每個 Q# 操作結束時,我們需要讓狀態中的 qubit{0}$\ket $$。 我們可以使用@"microsoft.quantum.intrinsic.reset"重新啟動所有量子位到零狀態,這將完成我們的操作。

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


