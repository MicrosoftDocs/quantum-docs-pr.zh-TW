---
title: 探索纏結 Q#
description: 瞭解如何在中撰寫量副程式 Q# 。 使用 Quantum Development Kit (QDK) 開發貝爾狀態應用程式
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac9c060c157ba5ee3bc66852c42298ac8adcb3b3
ms.sourcegitcommit: 685a8ab16d7e6a25e63a168d6e7c385fa6e876cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2020
ms.locfileid: "91492331"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="f9d35-104">教學課程：使用 Q\# 探索糾纏</span><span class="sxs-lookup"><span data-stu-id="f9d35-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="f9d35-105">在本教學課程中，我們會示範如何撰寫 Q# 程式來操作和測量量子位，並示範迭加和纏結的效果。</span><span class="sxs-lookup"><span data-stu-id="f9d35-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="f9d35-106">您將會撰寫一個名為 Bell 的應用程式以示範量子纏結。</span><span class="sxs-lookup"><span data-stu-id="f9d35-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="f9d35-107">Bell 這個名稱取自「貝爾狀態」，是指兩個量子位元的特定狀態，用來代表疊加和量子纏結的最簡單範例。</span><span class="sxs-lookup"><span data-stu-id="f9d35-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f9d35-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="f9d35-108">Pre-requisites</span></span>

<span data-ttu-id="f9d35-109">如果您已準備好要開始撰寫程式碼，請先遵循下列步驟再繼續進行：</span><span class="sxs-lookup"><span data-stu-id="f9d35-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="f9d35-110">使用您慣用的語言和開發環境，[安裝](xref:microsoft.quantum.install)量子開發工具組。</span><span class="sxs-lookup"><span data-stu-id="f9d35-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="f9d35-111">如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本</span><span class="sxs-lookup"><span data-stu-id="f9d35-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="f9d35-112">您也可以在不安裝 QDK 的情況下，追蹤程式 Q# 設計語言的總覽和量子運算的第一個概念。</span><span class="sxs-lookup"><span data-stu-id="f9d35-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="f9d35-113">在本教學課程中，您將了解如何：</span><span class="sxs-lookup"><span data-stu-id="f9d35-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f9d35-114">在 Q 中建立和合併作業\#</span><span class="sxs-lookup"><span data-stu-id="f9d35-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="f9d35-115">建立作業以將量子位放在迭加、纏和測量。</span><span class="sxs-lookup"><span data-stu-id="f9d35-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="f9d35-116">示範 Q# 在模擬器中執行程式的量子纏結。</span><span class="sxs-lookup"><span data-stu-id="f9d35-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="f9d35-117">使用 QDK 示範量子位行為</span><span class="sxs-lookup"><span data-stu-id="f9d35-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="f9d35-118">其中，古典位元會有單一二進位值，例如 0 或 1，而[量子位元](xref:microsoft.quantum.glossary#qubit)的狀態則可以是 0 和 1 的**疊加**。</span><span class="sxs-lookup"><span data-stu-id="f9d35-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="f9d35-119">就概念而言，量子位的狀態可視為抽象空間的方向， (也稱為向量) 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="f9d35-120">量子位狀態可以是任何可能的方向。</span><span class="sxs-lookup"><span data-stu-id="f9d35-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="f9d35-121">兩個**古典狀態**是兩個方向，分別代表 100% 測量到 0 的機率和 100% 測量到 1 的機率。</span><span class="sxs-lookup"><span data-stu-id="f9d35-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="f9d35-122">測量動作會產生二進位結果，並變更量子位元狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="f9d35-123">度量產生的是0或1的二進位值。</span><span class="sxs-lookup"><span data-stu-id="f9d35-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="f9d35-124">量子位元會從疊加狀態 (任何方向) 變為兩個古典狀態的其中一個。</span><span class="sxs-lookup"><span data-stu-id="f9d35-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="f9d35-125">之後，在沒有任何干擾作業的情況下重複相同的測量，會產生相同的二進位結果。</span><span class="sxs-lookup"><span data-stu-id="f9d35-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="f9d35-126">多個量子位元可以[**纏結**](xref:microsoft.quantum.glossary#entanglement)。</span><span class="sxs-lookup"><span data-stu-id="f9d35-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="f9d35-127">當我們測量一個纏結的量子位元時，對其他量子位元狀態的了解也會隨之更新。</span><span class="sxs-lookup"><span data-stu-id="f9d35-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="f9d35-128">現在，我們已經準備好示範 Q# 此行為的表達方式。</span><span class="sxs-lookup"><span data-stu-id="f9d35-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="f9d35-129">您將從最簡單的程式著手建置，以示範量子疊加和量子纏結。</span><span class="sxs-lookup"><span data-stu-id="f9d35-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="f9d35-130">建立 Q# 專案</span><span class="sxs-lookup"><span data-stu-id="f9d35-130">Creating a Q# project</span></span>

<span data-ttu-id="f9d35-131">我們必須做的第一件事是建立新 Q# 專案。</span><span class="sxs-lookup"><span data-stu-id="f9d35-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="f9d35-132">在本教學課程中，我們將使用[ Q# 以 VS Code 的應用程式](xref:microsoft.quantum.install.standalone)為基礎的環境。</span><span class="sxs-lookup"><span data-stu-id="f9d35-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="f9d35-133">若要建立新的專案，請在 VS Code 中：</span><span class="sxs-lookup"><span data-stu-id="f9d35-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="f9d35-134">按一下 [檢視] -> [命令選擇區]，然後選取 **[Q#：建立新專案]** 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="f9d35-135">按一下 [獨立主控台應用程式]。</span><span class="sxs-lookup"><span data-stu-id="f9d35-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="f9d35-136">瀏覽至要儲存專案的位置，然後按一下 [建立專案]。</span><span class="sxs-lookup"><span data-stu-id="f9d35-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="f9d35-137">成功建立專案後，按一下右下方的 [開啟新增專案...]。</span><span class="sxs-lookup"><span data-stu-id="f9d35-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="f9d35-138">在此情況下，我們稱之為專案 `Bell` 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="f9d35-139">這會產生兩個檔案： `Bell.csproj` 、專案檔，以及 `Program.qs` Q# 我們將用來撰寫應用程式的應用程式範本。</span><span class="sxs-lookup"><span data-stu-id="f9d35-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="f9d35-140">的內容 `Program.qs` 應該是：</span><span class="sxs-lookup"><span data-stu-id="f9d35-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="f9d35-141">撰寫 Q \# 應用程式</span><span class="sxs-lookup"><span data-stu-id="f9d35-141">Write the Q\# application</span></span>
 
<span data-ttu-id="f9d35-142">我們的目標是要在特定的量子狀態下準備兩個量子位，示範如何在量子位上操作 Q# 來變更其狀態，並示範迭加和纏結的影響。</span><span class="sxs-lookup"><span data-stu-id="f9d35-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="f9d35-143">我們會逐一建立此內容，以介紹量子位狀態、作業和測量。</span><span class="sxs-lookup"><span data-stu-id="f9d35-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="f9d35-144">使用度量將量子位初始化</span><span class="sxs-lookup"><span data-stu-id="f9d35-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="f9d35-145">在下列第一個程式碼片段中，我們會示範如何在中使用量子位 Q# 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-145">In the first code snippet below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="f9d35-146">我們會介紹兩項作業， [`M`](xref:microsoft.quantum.intrinsic.m) 並 [`X`](xref:microsoft.quantum.intrinsic.x) 轉換量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-146">We’ll introduce two operations, [`M`](xref:microsoft.quantum.intrinsic.m) and [`X`](xref:microsoft.quantum.intrinsic.x) that transform the state of a qubit.</span></span> <span data-ttu-id="f9d35-147">在此程式碼片段中定義的 `SetQubitState` 作業需要一個量子位元做為參數和另一個參數 `desired`，後者代表我們想要的量子位元狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="f9d35-148">`SetQubitState` 作業使用 `M` 作業對量子位元執行測量。</span><span class="sxs-lookup"><span data-stu-id="f9d35-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="f9d35-149">在中 Q# ，量子位測量一律會傳回 `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="f9d35-150">如果量測傳回的值不等於所需的值，則會「 `SetQubitState` 翻轉」量子位; 也就是說，它會執行作業 `X` ，將量子位狀態變更為新的狀態，其中測量的機率會傳回 `Zero` 並 `One` 反轉。</span><span class="sxs-lookup"><span data-stu-id="f9d35-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="f9d35-151">如此一來， `SetQubitState` 一律會將目標量子位置於預期狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="f9d35-152">以下列程式碼取代的內容 `Program.qs` ：</span><span class="sxs-lookup"><span data-stu-id="f9d35-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="f9d35-153">現在已經可以呼叫這項作業來將量子位元設定為古典狀態，亦即 100% 的時間會傳回 `Zero` 或 100% 的時間會傳回 `One`。</span><span class="sxs-lookup"><span data-stu-id="f9d35-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="f9d35-154">`Zero` 和 `One` 是常數，代表測量量子位元的唯二兩個可能結果。</span><span class="sxs-lookup"><span data-stu-id="f9d35-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="f9d35-155">`SetQubitState` 作業會測量量子位元。</span><span class="sxs-lookup"><span data-stu-id="f9d35-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="f9d35-156">如果量子位是我們想要的狀態，請將 `SetQubitState` 它單獨保留; 否則，藉由執行此作業 `X` ，我們會將量子位狀態變更為所需的狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="f9d35-157">關於 Q# 作業</span><span class="sxs-lookup"><span data-stu-id="f9d35-157">About Q# operations</span></span>

<span data-ttu-id="f9d35-158">作業 Q# 是量子副程式。</span><span class="sxs-lookup"><span data-stu-id="f9d35-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="f9d35-159">也就是說，它是一個可呼叫的常式，其中包含對其他量子作業的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f9d35-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="f9d35-160">作業的引數會在括弧內指定為元組。</span><span class="sxs-lookup"><span data-stu-id="f9d35-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="f9d35-161">作業的傳回類型指定於冒號後面。</span><span class="sxs-lookup"><span data-stu-id="f9d35-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="f9d35-162">在此情況下，作業沒有傳回 `SetQubitState` 型別，因此它標示為 return `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="f9d35-163">這相當於 Q# F # 中的對等專案 `unit` ，它大致上類似于 `void` c #，而 Python (中的空元組則是以 `()` 類型提示 `Tuple[()]`) 表示。</span><span class="sxs-lookup"><span data-stu-id="f9d35-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="f9d35-164">您在第一項作業中使用了兩個量子作業 Q# ：</span><span class="sxs-lookup"><span data-stu-id="f9d35-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="f9d35-165">此作業會 [`M`](xref:microsoft.quantum.intrinsic.m) 測量量子位的狀態</span><span class="sxs-lookup"><span data-stu-id="f9d35-165">The [`M`](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="f9d35-166">此作業會 [`X`](xref:microsoft.quantum.intrinsic.x) 翻轉量子位的狀態</span><span class="sxs-lookup"><span data-stu-id="f9d35-166">The [`X`](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="f9d35-167">量子作業會轉換量子位元的狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="f9d35-168">有時候會看到「量子閘」這個較接近古典邏輯閘的詞而不是作業。</span><span class="sxs-lookup"><span data-stu-id="f9d35-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="f9d35-169">這源自於量子運算初期，當時的演算法只是理論架構，是用類似古典運算中的電路圖來做出圖表化的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="f9d35-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="f9d35-170">計算測量結果</span><span class="sxs-lookup"><span data-stu-id="f9d35-170">Counting measurement outcomes</span></span>

<span data-ttu-id="f9d35-171">為了示範 `SetQubitState` 作業的效果，於是加入 `TestBellState` 作業。</span><span class="sxs-lookup"><span data-stu-id="f9d35-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="f9d35-172">這項作業需要一個 `Zero` 或 `One` 的輸入，並使用該輸入來呼叫 `SetQubitState` 作業數次，然後計算從量子位元測量傳回 `Zero` 的次數，以及傳回 `One` 的次數。</span><span class="sxs-lookup"><span data-stu-id="f9d35-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="f9d35-173">當然，在第一次模擬 `TestBellState` 作業時，我們預期輸出會顯示以 `Zero` 作為輸入參數之量子位元的所有測量都會傳回 `Zero`，而以 `One` 作為輸入參數之量子位元的所有測量都會傳回 `One`。</span><span class="sxs-lookup"><span data-stu-id="f9d35-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="f9d35-174">此外，我們會在中新增程式碼， `TestBellState` 以示範迭加和纏結。</span><span class="sxs-lookup"><span data-stu-id="f9d35-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="f9d35-175">在 `Program.qs` 檔案中，將下列作業新增至命名空間內的 `SetQubitState` 作業後面：</span><span class="sxs-lookup"><span data-stu-id="f9d35-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="f9d35-176">請注意，我們已在 `return` 中使用函式 (`Message`) [microsoft. message]，在主控台中列印說明訊息</span><span class="sxs-lookup"><span data-stu-id="f9d35-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="f9d35-177">此作業 (`TestBellState`) 會迴圈進行 `count` 次反覆運算、設定量子位元的指定 `initial` 值，然後測量 (`M`) 結果。</span><span class="sxs-lookup"><span data-stu-id="f9d35-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="f9d35-178">它會收集關於我們測量了多少個零和一的統計資料，並將其傳回給呼叫端。</span><span class="sxs-lookup"><span data-stu-id="f9d35-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="f9d35-179">它會執行另一項必要的作業。</span><span class="sxs-lookup"><span data-stu-id="f9d35-179">It performs one other necessary operation.</span></span> <span data-ttu-id="f9d35-180">它會先將量子位元重設為已知狀態 (`Zero`) 再加以傳回，讓其他人可將此量子位元配置於已知狀態中。</span><span class="sxs-lookup"><span data-stu-id="f9d35-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="f9d35-181">這是 `using` 陳述式所需的條件。</span><span class="sxs-lookup"><span data-stu-id="f9d35-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="f9d35-182">關於 Q 中的變數\#</span><span class="sxs-lookup"><span data-stu-id="f9d35-182">About variables in Q\#</span></span>

<span data-ttu-id="f9d35-183">根據預設，中的變數 Q# 是不可變的，其值在系結之後可能不會變更。</span><span class="sxs-lookup"><span data-stu-id="f9d35-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="f9d35-184">`let` 關鍵字可用來指出不可變變數的繫結。</span><span class="sxs-lookup"><span data-stu-id="f9d35-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="f9d35-185">作業引數一律為不可變的。</span><span class="sxs-lookup"><span data-stu-id="f9d35-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="f9d35-186">如果您需要可變更值的變數 (例如範例中的 `numOnes`)，您可以使用 `mutable` 關鍵字來宣告變數。</span><span class="sxs-lookup"><span data-stu-id="f9d35-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="f9d35-187">可變變數的值可使用 `set` 陳述式來變更。</span><span class="sxs-lookup"><span data-stu-id="f9d35-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="f9d35-188">在這兩種情況下，都會由編譯器來推斷變數的類型。</span><span class="sxs-lookup"><span data-stu-id="f9d35-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="f9d35-189">Q# 變數不需要任何類型注釋。</span><span class="sxs-lookup"><span data-stu-id="f9d35-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="f9d35-190">關於 `using` Q 中的語句\#</span><span class="sxs-lookup"><span data-stu-id="f9d35-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="f9d35-191">`using`語句也是的特殊 Q# 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="f9d35-192">它會用來配置要用於程式碼區塊中的量子位元。</span><span class="sxs-lookup"><span data-stu-id="f9d35-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="f9d35-193">在中 Q# ，所有量子位都是動態配置和釋出，而不是在複雜演算法的整個存留期內的固定資源。</span><span class="sxs-lookup"><span data-stu-id="f9d35-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="f9d35-194">`using` 陳述式會在一開始配置一組量子位元，並在區塊結尾處釋出這些量子位元。</span><span class="sxs-lookup"><span data-stu-id="f9d35-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="f9d35-195">從命令提示字元執行程式碼</span><span class="sxs-lookup"><span data-stu-id="f9d35-195">Run the code from the command prompt</span></span>

<span data-ttu-id="f9d35-196">若要執行程式碼，我們必須告訴編譯器，在我們提供命令時要 *執行的可* 呼叫 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="f9d35-197">這項作業是透過在檔案中的簡單變更來完成， Q# 方法是 `@EntryPoint()` `TestBellState` 在此案例中加入具有直接在可呼叫：作業的一行。</span><span class="sxs-lookup"><span data-stu-id="f9d35-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="f9d35-198">完整的程式碼應該是：</span><span class="sxs-lookup"><span data-stu-id="f9d35-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="f9d35-199">若要執行此程式，我們需要 `count` `initial` 從命令提示字元指定和引數。</span><span class="sxs-lookup"><span data-stu-id="f9d35-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="f9d35-200">讓我們選擇範例 `count = 1000` 和 `initial = One` 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="f9d35-201">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="f9d35-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="f9d35-202">您應該會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="f9d35-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="f9d35-203">如果您嘗試使用 `initial = Zero` ，您應該會看到：</span><span class="sxs-lookup"><span data-stu-id="f9d35-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="f9d35-204">準備疊加</span><span class="sxs-lookup"><span data-stu-id="f9d35-204">Prepare superposition</span></span>

<span data-ttu-id="f9d35-205">現在讓我們看看如何 Q# 在迭加中表達量子位的方式。</span><span class="sxs-lookup"><span data-stu-id="f9d35-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="f9d35-206">前面說過，量子位元的狀態可以是 0 和 1 的疊加。</span><span class="sxs-lookup"><span data-stu-id="f9d35-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="f9d35-207">我們將使用 `Hadamard` 作業來達成此狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="f9d35-208">如果量子位元是在其中一個古典狀態 (其測量會傳回一律 `Zero` 或一律 `One` )，則 `Hadamard` 或 `H` 作業會將量子位元置於一種「量子位元測量結果 50% 的時間會傳回 `Zero`、50% 的時間會傳回 `One`」的狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="f9d35-209">概念上可以將量子位元想成介於 `Zero` 和 `One` 之間。</span><span class="sxs-lookup"><span data-stu-id="f9d35-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="f9d35-210">現在，當我們模擬 `TestBellState` 作業時，會看到在測量之後，結果傳回 `Zero` 和 `One` 的次數大致相同。</span><span class="sxs-lookup"><span data-stu-id="f9d35-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="f9d35-211">`X` 翻轉量子位狀態</span><span class="sxs-lookup"><span data-stu-id="f9d35-211">`X` flips qubit state</span></span>

<span data-ttu-id="f9d35-212">首先，我們會嘗試翻轉量子位 (如果量子位處於 `Zero` 狀態，它會翻轉為 `One` ，反之亦然) 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="f9d35-213">在 `TestBellState` 中加以測量之前先執行 `X` 作業，即可完成此動作：</span><span class="sxs-lookup"><span data-stu-id="f9d35-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="f9d35-214">現在會反轉結果：</span><span class="sxs-lookup"><span data-stu-id="f9d35-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="f9d35-215">現在讓我們來探索量子位的量子屬性。</span><span class="sxs-lookup"><span data-stu-id="f9d35-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="f9d35-216">`H` 準備迭加</span><span class="sxs-lookup"><span data-stu-id="f9d35-216">`H` prepares superposition</span></span>

<span data-ttu-id="f9d35-217">我們只需要將先前執行中的 `X` 作業取代為 `H` 或 Hadamard 作業即可。</span><span class="sxs-lookup"><span data-stu-id="f9d35-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="f9d35-218">我們不會將量子位元從 0 一路翻轉到 1，而是只會翻轉一半。</span><span class="sxs-lookup"><span data-stu-id="f9d35-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="f9d35-219">`TestBellState` 中取代的行此時會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="f9d35-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="f9d35-220">現在，結果會更有趣：</span><span class="sxs-lookup"><span data-stu-id="f9d35-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="f9d35-221">每次測量時，我們都會要求一個傳統值，但量子位元介於 0 到 1 的中間，因此我們 (在統計上) 有一半時間會取得 0，一半的時間會取得 1。</span><span class="sxs-lookup"><span data-stu-id="f9d35-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="f9d35-222">這就是所謂的**疊加**，它讓我們首次得以實際檢視量子狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="f9d35-223">準備糾纏</span><span class="sxs-lookup"><span data-stu-id="f9d35-223">Prepare entanglement</span></span>

<span data-ttu-id="f9d35-224">現在讓我們看看如何 Q# 表達纏量子位的方式。</span><span class="sxs-lookup"><span data-stu-id="f9d35-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="f9d35-225">首先，我們將第一個量子位元設定為初始狀態，然後使用 `H` 作業將它置於疊加狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="f9d35-226">然後，在測量第一個量子位之前，我們會使用 () 的新作業 `CNOT` ，這代表 *受控制-非*。</span><span class="sxs-lookup"><span data-stu-id="f9d35-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT*.</span></span>  <span data-ttu-id="f9d35-227">在兩個量子位上執行這項作業的結果是，如果第一個量子位是，則會翻轉第二個量子位 `One` 。</span><span class="sxs-lookup"><span data-stu-id="f9d35-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="f9d35-228">現在，這兩個量子位元相互纏結。</span><span class="sxs-lookup"><span data-stu-id="f9d35-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="f9d35-229">第一個量子位元的統計資料並未變更 (測量後 `Zero` 或 `One` 的機率各半)，但現在當我們測量第二個量子位元時，其量值「一律」會與第一個量子位元的相同。</span><span class="sxs-lookup"><span data-stu-id="f9d35-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="f9d35-230">我們的 `CNOT` 讓這兩個量子位元相互糾纏，因此其中一個量子位元發生的情況，也會出現在另一個量子位元上。</span><span class="sxs-lookup"><span data-stu-id="f9d35-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="f9d35-231">如果您反轉測量 (先執行第二個量子位元，再執行第一個)，也會發生相同的情況。</span><span class="sxs-lookup"><span data-stu-id="f9d35-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="f9d35-232">第一個測量是隨機的，第二個測量則會根據第一個測量所發現的結果，以鎖定步驟執行。</span><span class="sxs-lookup"><span data-stu-id="f9d35-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="f9d35-233">我們必須做的第一件事是配置兩個量子位，而不是一個 `TestBellState` ：</span><span class="sxs-lookup"><span data-stu-id="f9d35-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="f9d35-234">這可讓我們先新增作業 (`CNOT`)，再於 `TestBellState` 中測量 (`M`)：</span><span class="sxs-lookup"><span data-stu-id="f9d35-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="f9d35-235">我們已新增另一項 `SetQubitState` 作業來初始化第一個量子位元，以確保它在作業開始後一律會處於 `Zero` 狀態。</span><span class="sxs-lookup"><span data-stu-id="f9d35-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="f9d35-236">在加以釋出之前，我們也需要先重設第二個量子位元。</span><span class="sxs-lookup"><span data-stu-id="f9d35-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="f9d35-237">完整的常式此時會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="f9d35-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="f9d35-238">如果加以執行，我們會得到與之前相同機率各半的結果。</span><span class="sxs-lookup"><span data-stu-id="f9d35-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="f9d35-239">不過，我們想知道的是第二個量子位元對第一個測量的量子位元有何反應。</span><span class="sxs-lookup"><span data-stu-id="f9d35-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="f9d35-240">我們會使用新版本的 `TestBellState` 作業來新增此統計資料：</span><span class="sxs-lookup"><span data-stu-id="f9d35-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="f9d35-241">新的傳回值 (`agree`) 會追蹤第一個量子位元的測量與第二個量子位元的測量是否相符。</span><span class="sxs-lookup"><span data-stu-id="f9d35-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="f9d35-242">執行我們取得的程式碼：</span><span class="sxs-lookup"><span data-stu-id="f9d35-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="f9d35-243">如之前在概觀所述，第一個量子位元的統計資料並未變更 (0 或 1 的機率各半)，但現在當我們測量第二個量子位元時，其量值__一律__會與第一個量子位元的相同，因為它們相互纏結!</span><span class="sxs-lookup"><span data-stu-id="f9d35-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="f9d35-244">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f9d35-244">Next steps</span></span>

<span data-ttu-id="f9d35-245">教學課程 [格羅弗的搜尋](xref:microsoft.quantum.quickstarts.search) 會示範如何建立及執行格羅弗搜尋（最受歡迎的量子運算演算法之一），並提供實用的程式範例， Q# 可用來解決量子運算的實際問題。</span><span class="sxs-lookup"><span data-stu-id="f9d35-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="f9d35-246">[使用量子開發工具組開始](xref:microsoft.quantum.welcome) ，建議更多學習 Q# 和量副程式設計的方式。</span><span class="sxs-lookup"><span data-stu-id="f9d35-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
