---
title: 搭配 Q# 使用的量子基本知識
description: 了解如何以 Q# 撰寫量子程式。 使用 Quantum Development Kit (QDK) 開發貝爾狀態應用程式
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 30135fa8a123e52a92b7187218f9980ba3cdbd2d
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442196"
---
# <a name="quantum-basics-with-q"></a><span data-ttu-id="2f985-104">搭配 Q# 使用的量子基本知識</span><span class="sxs-lookup"><span data-stu-id="2f985-104">Quantum basics with Q#</span></span>

<span data-ttu-id="2f985-105">在本快速入門中，我們會示範如何撰寫 Q# 程式來操控和測量量子位元，並示範疊加和纏結的效果，</span><span class="sxs-lookup"><span data-stu-id="2f985-105">In this Quickstart, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>  <span data-ttu-id="2f985-106">從而引導您安裝 QDK、建立程式，並在量子模擬器上執行該程式。</span><span class="sxs-lookup"><span data-stu-id="2f985-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="2f985-107">您將會撰寫一個名為 Bell 的應用程式以示範量子纏結。</span><span class="sxs-lookup"><span data-stu-id="2f985-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>  <span data-ttu-id="2f985-108">Bell 這個名稱取自「貝爾狀態」，是指兩個量子位元的特定狀態，用來代表疊加和量子纏結的最簡單範例。</span><span class="sxs-lookup"><span data-stu-id="2f985-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span> 

## <a name="pre-requisites"></a><span data-ttu-id="2f985-109">先決條件</span><span class="sxs-lookup"><span data-stu-id="2f985-109">Pre-requisites</span></span>

<span data-ttu-id="2f985-110">如果您已準備好要開始撰寫程式碼，請先遵循下列步驟再繼續進行：</span><span class="sxs-lookup"><span data-stu-id="2f985-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="2f985-111">使用您慣用的語言和開發環境[安裝](xref:microsoft.quantum.install) Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="2f985-111">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment</span></span>
* <span data-ttu-id="2f985-112">如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本</span><span class="sxs-lookup"><span data-stu-id="2f985-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="2f985-113">您也可以在不安裝 QDK 的情況下繼續閱讀本文內容，以了解 Q# 程式設計語言和量子運算的首要概念。</span><span class="sxs-lookup"><span data-stu-id="2f985-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="2f985-114">使用 Q# 示範量子位元行為</span><span class="sxs-lookup"><span data-stu-id="2f985-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="2f985-115">回想一下我們簡單的[量子位元定義](xref:microsoft.quantum.overview.what#the-qubit)。</span><span class="sxs-lookup"><span data-stu-id="2f985-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.what#the-qubit).</span></span>  <span data-ttu-id="2f985-116">其中，古典位元會有單一二進位值，例如 0 或 1，而量子位元的狀態則可以同時是 0 和 1 的**疊加**。</span><span class="sxs-lookup"><span data-stu-id="2f985-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  <span data-ttu-id="2f985-117">在概念上，可以將量子位元想成空間中的方向 (又稱為向量)。</span><span class="sxs-lookup"><span data-stu-id="2f985-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="2f985-118">量子位元可以是任何可能方向的其中一個。</span><span class="sxs-lookup"><span data-stu-id="2f985-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="2f985-119">兩個**古典狀態**是兩個方向，分別代表 100% 測量到 0 的機率和 100% 測量到 1 的機率。</span><span class="sxs-lookup"><span data-stu-id="2f985-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="2f985-120">這種表示法也能以[布洛赫球體](/quantum/concepts/the-qubit?view=qsharp-preview#visualizing-qubits-and-transformations-using-the-bloch-sphere)更正式地視覺化。</span><span class="sxs-lookup"><span data-stu-id="2f985-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit?view=qsharp-preview#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>


<span data-ttu-id="2f985-121">測量動作會產生二進位結果，並變更量子位元狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="2f985-122">測量會產生一個二進位值，也就是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="2f985-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="2f985-123">量子位元會從疊加狀態 (任何方向) 變為兩個古典狀態的其中一個。</span><span class="sxs-lookup"><span data-stu-id="2f985-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="2f985-124">之後，在沒有任何干擾作業的情況下重複相同的測量，會產生相同的二進位結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="2f985-125">多個量子位元可以**纏結**。</span><span class="sxs-lookup"><span data-stu-id="2f985-125">Multiple qubits can be **entangled**.</span></span> <span data-ttu-id="2f985-126">當我們測量一個纏結的量子位元時，對其他量子位元狀態的了解也會隨之更新。</span><span class="sxs-lookup"><span data-stu-id="2f985-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="2f985-127">現在，我們已準備好要來示範如何用 Q# 表示此行為。</span><span class="sxs-lookup"><span data-stu-id="2f985-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="2f985-128">您將從最簡單的程式著手建置，以示範量子疊加和量子纏結。</span><span class="sxs-lookup"><span data-stu-id="2f985-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="2f985-129">設定</span><span class="sxs-lookup"><span data-stu-id="2f985-129">Setup</span></span>

<span data-ttu-id="2f985-130">以 Microsoft 的 Quantum Development Kit 開發的應用程式會包含兩個部分：</span><span class="sxs-lookup"><span data-stu-id="2f985-130">Applications developed with Microsoft's Quantum Development Kit consist of two parts:</span></span>

1. <span data-ttu-id="2f985-131">一或多個量子演算法，使用 Q# 量子程式設計語言來實作。</span><span class="sxs-lookup"><span data-stu-id="2f985-131">One or more quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="2f985-132">一個主機程式，以作為主要進入點，並叫用 Q# 作業以執行量子演算法的程式設計語言來實作，例如 Python 或 C#。</span><span class="sxs-lookup"><span data-stu-id="2f985-132">A host program, implemented in a programming language like Python or C# that serves as the main entry point and invokes Q# operations to execute a quantum algorithm.</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="2f985-133">Python</span><span class="sxs-lookup"><span data-stu-id="2f985-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="2f985-134">選擇應用程式的位置</span><span class="sxs-lookup"><span data-stu-id="2f985-134">Choose a location for your application</span></span>

1. <span data-ttu-id="2f985-135">建立名為 `Bell.qs`的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f985-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="2f985-136">此檔案會包含您的 Q# 程式碼。</span><span class="sxs-lookup"><span data-stu-id="2f985-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="2f985-137">建立名為 `host.py`的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f985-137">Create a file called `host.py`.</span></span> <span data-ttu-id="2f985-138">此檔案會包含您的 Python 主機程式碼。</span><span class="sxs-lookup"><span data-stu-id="2f985-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-linetabtabid-csharp"></a>[<span data-ttu-id="2f985-139">C# 命令列</span><span class="sxs-lookup"><span data-stu-id="2f985-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="2f985-140">建立新的 Q# 專案：</span><span class="sxs-lookup"><span data-stu-id="2f985-140">Create a new Q# project:</span></span>

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="2f985-141">您應該會看到 `.csproj` 檔案、名為 `Operations.qs` 的 Q# 檔案，以及名為 `Driver.cs` 的主機程式檔案</span><span class="sxs-lookup"><span data-stu-id="2f985-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="2f985-142">重新命名 Q# 檔案</span><span class="sxs-lookup"><span data-stu-id="2f985-142">Rename the Q# file</span></span>

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studiotabtabid-vs2019"></a>[<span data-ttu-id="2f985-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2f985-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="2f985-144">建立新專案</span><span class="sxs-lookup"><span data-stu-id="2f985-144">Create a new project</span></span>

   * <span data-ttu-id="2f985-145">開啟 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2f985-145">Open Visual Studio</span></span>
   * <span data-ttu-id="2f985-146">移至 [檔案]  功能表，然後選取 [新增]   -> [專案...] </span><span class="sxs-lookup"><span data-stu-id="2f985-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="2f985-147">在專案範本總管的搜尋欄位中輸入 `Q#`，然後選取 `Q# Application` 範本</span><span class="sxs-lookup"><span data-stu-id="2f985-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="2f985-148">將您的專案命名為 `Bell`</span><span class="sxs-lookup"><span data-stu-id="2f985-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="2f985-149">重新命名 Q# 檔案</span><span class="sxs-lookup"><span data-stu-id="2f985-149">Rename the Q# file</span></span>

   * <span data-ttu-id="2f985-150">瀏覽至 [方案總管] </span><span class="sxs-lookup"><span data-stu-id="2f985-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="2f985-151">以滑鼠右鍵按一下 `Operations.qs` 檔案</span><span class="sxs-lookup"><span data-stu-id="2f985-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="2f985-152">將其重新命名為 `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="2f985-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="2f985-153">撰寫 Q# 作業</span><span class="sxs-lookup"><span data-stu-id="2f985-153">Write a Q# operation</span></span>

<span data-ttu-id="2f985-154">我們的目標是要準備兩個特定量子狀態的量子位元，示範如何利用 Q# 來操作量子位元以變更其狀態，並示範疊加和纏結的效果。</span><span class="sxs-lookup"><span data-stu-id="2f985-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="2f985-155">我們會逐一加以建置，來示範量子位元的狀態、操作和測量。</span><span class="sxs-lookup"><span data-stu-id="2f985-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="2f985-156">**概觀：** 在下列的第一個程式碼中，我們會示範如何在 Q# 中處理量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="2f985-157">我們會引進 `M` 和 `X` 兩項作業來轉換量子位元的狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="2f985-158">在此程式碼片段中定義的 `Set` 作業需要一個量子位元做為參數和另一個參數 `desired`，後者代表我們想要的量子位元狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="2f985-159">`Set` 作業使用 `M` 作業對量子位元執行測量。</span><span class="sxs-lookup"><span data-stu-id="2f985-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="2f985-160">在 Q # 中，量子位元的測量一律會傳回 `Zero` 或 `One`。</span><span class="sxs-lookup"><span data-stu-id="2f985-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="2f985-161">如果測量傳回的值不等於想要的值，Set 會「翻轉」量子位元；意思是說，它會執行 `X` 作業，將量子位元的狀態變更為新的狀態，而新狀態下測量傳回 `Zero` 和 `One` 的機率會相反。</span><span class="sxs-lookup"><span data-stu-id="2f985-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="2f985-162">為了示範 `Set` 作業的效果，於是加入 `TestBellState` 作業。</span><span class="sxs-lookup"><span data-stu-id="2f985-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="2f985-163">這項作業需要一個 `Zero` 或 `One` 的輸入，並使用該輸入來呼叫 `Set` 作業數次，然後計算從量子位元測量傳回 `Zero` 的次數，以及傳回 `One` 的次數。</span><span class="sxs-lookup"><span data-stu-id="2f985-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="2f985-164">當然，在第一次模擬 `TestBellState` 作業時，我們預期輸出會顯示以 `Zero` 作為輸入參數之量子位元的所有測量都會傳回 `Zero`，而以 `One` 作為輸入參數之量子位元的所有測量都會傳回 `One`。</span><span class="sxs-lookup"><span data-stu-id="2f985-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="2f985-165">接下來，我們會在 `TestBellState` 加入更多程式碼來示範疊加和纏結。</span><span class="sxs-lookup"><span data-stu-id="2f985-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="2f985-166">Q# 作業程式碼</span><span class="sxs-lookup"><span data-stu-id="2f985-166">Q# operation code</span></span>

1. <span data-ttu-id="2f985-167">將 Bell.qs 檔案的內容取代為下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="2f985-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="2f985-168">現在已經可以呼叫這項作業來將量子位元設定為古典狀態，亦即 100% 的時間會傳回 `Zero` 或 100% 的時間會傳回 `One`。</span><span class="sxs-lookup"><span data-stu-id="2f985-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="2f985-169">`Zero` 和 `One` 是常數，代表測量量子位元的唯二兩個可能結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="2f985-170">`Set` 作業會測量量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="2f985-171">如果量子位元是我們想要的狀態 `Set`，就不動它；反之，則執行 `X` 作業，將量子位元的狀態變更為想要的狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="2f985-172">關於 Q# 作業</span><span class="sxs-lookup"><span data-stu-id="2f985-172">About Q# operations</span></span>

<span data-ttu-id="2f985-173">Q# 作業是量子副程式。</span><span class="sxs-lookup"><span data-stu-id="2f985-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="2f985-174">也就是說，它是包含量子作業的可呼叫常式。</span><span class="sxs-lookup"><span data-stu-id="2f985-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="2f985-175">作業的引數會在括弧內指定為元組。</span><span class="sxs-lookup"><span data-stu-id="2f985-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="2f985-176">作業的傳回類型指定於冒號後面。</span><span class="sxs-lookup"><span data-stu-id="2f985-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="2f985-177">在此案例中，`Set` 作業不會傳回任何項目，因此會標示為傳回 `Unit`。</span><span class="sxs-lookup"><span data-stu-id="2f985-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="2f985-178">此 Q# 項目等同於 F# 中的 `unit`，且大致上類似於 C# 中的 `void`，以及 Python 中的空元組 (`Tuple[()]`)。</span><span class="sxs-lookup"><span data-stu-id="2f985-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="2f985-179">您在第一個 Q# 作業中使用了兩個量子作業：</span><span class="sxs-lookup"><span data-stu-id="2f985-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="2f985-180">[M](xref:microsoft.quantum.intrinsic.m) 作業，會測量量子位元的狀態</span><span class="sxs-lookup"><span data-stu-id="2f985-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="2f985-181">[X](xref:microsoft.quantum.intrinsic.x) 作業，會翻轉量子位元的狀態</span><span class="sxs-lookup"><span data-stu-id="2f985-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="2f985-182">量子作業會轉換量子位元的狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="2f985-183">有時候會看到「量子閘」這個較接近古典邏輯閘的詞而不是作業。</span><span class="sxs-lookup"><span data-stu-id="2f985-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="2f985-184">這源自於量子運算初期，當時的演算法只是理論架構，是用類似古典運算中的電路圖來做出圖表化的視覺呈現。</span><span class="sxs-lookup"><span data-stu-id="2f985-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="2f985-185">新增 Q# 測試程式碼</span><span class="sxs-lookup"><span data-stu-id="2f985-185">Add Q# test code</span></span>

1. <span data-ttu-id="2f985-186">在 `Bell.qs` 檔案中，將下列作業新增至命名空間內的 `Set` 作業後面：</span><span class="sxs-lookup"><span data-stu-id="2f985-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="2f985-187">此作業 (`TestBellState`) 會迴圈進行 `count` 次反覆運算、設定量子位元的指定 `initial` 值，然後測量 (`M`) 結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="2f985-188">它會收集關於我們測量了多少個零和一的統計資料，並將其傳回給呼叫端。</span><span class="sxs-lookup"><span data-stu-id="2f985-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="2f985-189">它會執行另一項必要的作業。</span><span class="sxs-lookup"><span data-stu-id="2f985-189">It performs one other necessary operation.</span></span> <span data-ttu-id="2f985-190">它會先將量子位元重設為已知狀態 (`Zero`) 再加以傳回，讓其他人可將此量子位元配置於已知狀態中。</span><span class="sxs-lookup"><span data-stu-id="2f985-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="2f985-191">這是 `using` 陳述式所需的條件。</span><span class="sxs-lookup"><span data-stu-id="2f985-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="2f985-192">關於 Q# 中的變數</span><span class="sxs-lookup"><span data-stu-id="2f985-192">About variables in Q#</span></span>

<span data-ttu-id="2f985-193">根據預設，Q# 中的變數是不可變的；其值在繫結之後即無法變更。</span><span class="sxs-lookup"><span data-stu-id="2f985-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="2f985-194">`let` 關鍵字可用來指出不可變變數的繫結。</span><span class="sxs-lookup"><span data-stu-id="2f985-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="2f985-195">作業引數一律為不可變的。</span><span class="sxs-lookup"><span data-stu-id="2f985-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="2f985-196">如果您需要可變更值的變數 (例如範例中的 `numOnes`)，您可以使用 `mutable` 關鍵字來宣告變數。</span><span class="sxs-lookup"><span data-stu-id="2f985-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="2f985-197">可變變數的值可使用 `set` 陳述式來變更。</span><span class="sxs-lookup"><span data-stu-id="2f985-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="2f985-198">在這兩種情況下，都會由編譯器來推斷變數的類型。</span><span class="sxs-lookup"><span data-stu-id="2f985-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="2f985-199">Q# 的變數不需要任何類型註解。</span><span class="sxs-lookup"><span data-stu-id="2f985-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="2f985-200">關於 Q# 中的 `using` 陳述式</span><span class="sxs-lookup"><span data-stu-id="2f985-200">About `using` statements in Q#</span></span>

<span data-ttu-id="2f985-201">在 Q# 中，`using` 陳述式也很特別。</span><span class="sxs-lookup"><span data-stu-id="2f985-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="2f985-202">它會用來配置要用於程式碼區塊中的量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="2f985-203">在 Q # 中，所有量子位元都是動態配置和釋出的，而不是在複雜演算法的整個存留期內都存在的固定資源。</span><span class="sxs-lookup"><span data-stu-id="2f985-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="2f985-204">`using` 陳述式會在一開始配置一組量子位元，並在區塊結尾處釋出這些量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="2f985-205">建立主應用程式的程式碼</span><span class="sxs-lookup"><span data-stu-id="2f985-205">Create the host application code</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="2f985-206">Python</span><span class="sxs-lookup"><span data-stu-id="2f985-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="2f985-207">開啟 `host.py` 檔案並新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="2f985-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="ctabtabid-csharp"></a>[<span data-ttu-id="2f985-208">C#</span><span class="sxs-lookup"><span data-stu-id="2f985-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="2f985-209">將 `Driver.cs` 檔案的內容取代為下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="2f985-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="2f985-210">關於主應用程式的程式碼</span><span class="sxs-lookup"><span data-stu-id="2f985-210">About the host application code</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="2f985-211">Python</span><span class="sxs-lookup"><span data-stu-id="2f985-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="2f985-212">Python 主應用程式有三個部分：</span><span class="sxs-lookup"><span data-stu-id="2f985-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="2f985-213">計算量子演算法所需的任何引數。</span><span class="sxs-lookup"><span data-stu-id="2f985-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="2f985-214">在此範例中，`count` 是固定為 1000，而 `initial` 是量子位元的初始值。</span><span class="sxs-lookup"><span data-stu-id="2f985-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="2f985-215">呼叫已匯入之 Q# 作業的 `simulate()` 方法，以執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="2f985-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="2f985-216">處理作業的結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-216">Process the result of the operation.</span></span> <span data-ttu-id="2f985-217">在範例中，`res` 會接收作業的結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="2f985-218">此處的結果是模擬器所測量的零數目 (`num_zeros`) 和一數目 (`num_ones`) 的元組。</span><span class="sxs-lookup"><span data-stu-id="2f985-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="2f985-219">我們會解構元組以取得這兩個欄位，並列印結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="ctabtabid-csharp"></a>[<span data-ttu-id="2f985-220">C#</span><span class="sxs-lookup"><span data-stu-id="2f985-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="2f985-221">C# 主應用程式有四個部分：</span><span class="sxs-lookup"><span data-stu-id="2f985-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="2f985-222">建構量子模擬器。</span><span class="sxs-lookup"><span data-stu-id="2f985-222">Construct a quantum simulator.</span></span> <span data-ttu-id="2f985-223">範例中的模擬器為 `qsim`。</span><span class="sxs-lookup"><span data-stu-id="2f985-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="2f985-224">計算量子演算法所需的任何引數。</span><span class="sxs-lookup"><span data-stu-id="2f985-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="2f985-225">在此範例中，`count` 是固定為 1000，而 `initial` 是量子位元的初始值。</span><span class="sxs-lookup"><span data-stu-id="2f985-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="2f985-226">執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="2f985-226">Run the quantum algorithm.</span></span> <span data-ttu-id="2f985-227">每個 Q# 作業都會產生一個具有相同名稱的 C# 類別。</span><span class="sxs-lookup"><span data-stu-id="2f985-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="2f985-228">此類別具有 `Run` 方法，會以**非同步方式**執行作業。</span><span class="sxs-lookup"><span data-stu-id="2f985-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="2f985-229">執行是非同步的，因為實際硬體的執行將是非同步的。</span><span class="sxs-lookup"><span data-stu-id="2f985-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="2f985-230">由於 `Run` 方法是非同步的，因此我們會擷取 `Result` 屬性；這將會封鎖執行，直到工作完成並同步傳回結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="2f985-231">處理作業的結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-231">Process the result of the operation.</span></span> <span data-ttu-id="2f985-232">在範例中，`res` 會接收作業的結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="2f985-233">此處的結果是模擬器所測量的零數目 (`numZeros`) 和一數目 (`numOnes`) 的元組。</span><span class="sxs-lookup"><span data-stu-id="2f985-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="2f985-234">在 C# 中，這會以的 ValueTuple 的形式傳回。</span><span class="sxs-lookup"><span data-stu-id="2f985-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="2f985-235">我們會解構元組以取得這兩個欄位，並列印結果，然後等待按鍵。</span><span class="sxs-lookup"><span data-stu-id="2f985-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="2f985-236">建置和執行</span><span class="sxs-lookup"><span data-stu-id="2f985-236">Build and run</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="2f985-237">Python</span><span class="sxs-lookup"><span data-stu-id="2f985-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="2f985-238">在您的終端機上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2f985-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="2f985-239">此命令會執行主應用程式，以模擬 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="2f985-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="2f985-240">結果應為：</span><span class="sxs-lookup"><span data-stu-id="2f985-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-codetabtabid-csharp"></a>[<span data-ttu-id="2f985-241">命令列/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2f985-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="2f985-242">在您的終端機上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2f985-242">Run the following at your terminal:</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="2f985-243">此命令會自動下載所有必要套件、建置應用程式，然後在命令列上加以執行。</span><span class="sxs-lookup"><span data-stu-id="2f985-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="2f985-244">或者，按 **F1** 開啟命令選擇區，然後選取 **[偵錯：啟動但不偵錯]** 。</span><span class="sxs-lookup"><span data-stu-id="2f985-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="2f985-245">系統可能會提示您建立新的 ``launch.json`` 檔案以說明如何啟動程式。</span><span class="sxs-lookup"><span data-stu-id="2f985-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="2f985-246">預設的 ``launch.json`` 應可適用於大部分的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2f985-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="2f985-247">結果應為：</span><span class="sxs-lookup"><span data-stu-id="2f985-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studiotabtabid-vs2019"></a>[<span data-ttu-id="2f985-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2f985-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="2f985-249">只要按 `F5`，您的程式應該就會建置並執行！</span><span class="sxs-lookup"><span data-stu-id="2f985-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="2f985-250">結果應為：</span><span class="sxs-lookup"><span data-stu-id="2f985-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="2f985-251">當您按下按鍵後，程式就會結束。</span><span class="sxs-lookup"><span data-stu-id="2f985-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="2f985-252">準備疊加</span><span class="sxs-lookup"><span data-stu-id="2f985-252">Prepare superposition</span></span>

<span data-ttu-id="2f985-253">**概觀** 現在讓我們來看一下 Q# 如何表示疊加狀態的量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="2f985-254">前面說過，量子位元的狀態可以是 0 和 1 的疊加。</span><span class="sxs-lookup"><span data-stu-id="2f985-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="2f985-255">我們將使用 `Hadamard` 作業來達成此狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="2f985-256">如果量子位元是在其中一個古典狀態 (其測量會傳回一律 `Zero` 或一律 `One` )，則 `Hadamard` 或 `H` 作業會將量子位元置於一種「量子位元測量結果 50% 的時間會傳回 `Zero`、50% 的時間會傳回 `One`」的狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="2f985-257">概念上可以將量子位元想成介於 `Zero` 和 `One` 之間。</span><span class="sxs-lookup"><span data-stu-id="2f985-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="2f985-258">現在，當我們模擬 `TestBellState` 作業時，會看到在測量之後，結果傳回 `Zero` 和 `One` 的次數大致相同。</span><span class="sxs-lookup"><span data-stu-id="2f985-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="2f985-259">首先，我們將嘗試翻轉量子位元 (如果量子位元處於 `Zero` 狀態，會翻轉成 `One`，反之亦然)。</span><span class="sxs-lookup"><span data-stu-id="2f985-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="2f985-260">在 `TestBellState` 中加以測量之前先執行 `X` 作業，即可完成此動作：</span><span class="sxs-lookup"><span data-stu-id="2f985-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="2f985-261">此時，結果 (按下 `F5` 之後) 將會反轉：</span><span class="sxs-lookup"><span data-stu-id="2f985-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="2f985-262">不過，我們到目前為止所看到的一切都是傳統的。</span><span class="sxs-lookup"><span data-stu-id="2f985-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="2f985-263">我們要取得量子結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-263">Let's get a quantum result.</span></span> <span data-ttu-id="2f985-264">我們只需要將先前執行中的 `X` 作業取代為 `H` 或 Hadamard 作業即可。</span><span class="sxs-lookup"><span data-stu-id="2f985-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="2f985-265">我們不會將量子位元從 0 一路翻轉到 1，而是只會翻轉一半。</span><span class="sxs-lookup"><span data-stu-id="2f985-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="2f985-266">`TestBellState` 中取代的行此時會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="2f985-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="2f985-267">現在，結果會更有趣：</span><span class="sxs-lookup"><span data-stu-id="2f985-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="2f985-268">每次測量時，我們都會要求一個傳統值，但量子位元介於 0 到 1 的中間，因此我們 (在統計上) 有一半時間會取得 0，一半的時間會取得 1。</span><span class="sxs-lookup"><span data-stu-id="2f985-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="2f985-269">這就是所謂的__疊加__，它讓我們首次得以實際檢視量子狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="2f985-270">準備糾纏</span><span class="sxs-lookup"><span data-stu-id="2f985-270">Prepare entanglement</span></span>

<span data-ttu-id="2f985-271">**概觀：** 現在讓我們來看一下 Q# 如何表示量子位元纏結。</span><span class="sxs-lookup"><span data-stu-id="2f985-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="2f985-272">首先，我們將第一個量子位元設定為初始狀態，然後使用 `H` 作業將它置於疊加狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="2f985-273">然後，在測量第一個量子位元之前，我們使用新的作業 (`CNOT`)，代表 Controlled-Not。</span><span class="sxs-lookup"><span data-stu-id="2f985-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="2f985-274">對兩個量子位元執行這項作業的結果是：如果第一個量子位元是 `One` 就會翻轉第二個量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="2f985-275">現在，這兩個量子位元相互纏結。</span><span class="sxs-lookup"><span data-stu-id="2f985-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="2f985-276">第一個量子位元的統計資料並未變更 (測量後 `Zero` 或 `One` 的機率各半)，但現在當我們測量第二個量子位元時，其量值「一律」  會與第一個量子位元的相同。</span><span class="sxs-lookup"><span data-stu-id="2f985-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="2f985-277">我們的 `CNOT` 讓這兩個量子位元相互糾纏，因此其中一個量子位元發生的情況，也會出現在另一個量子位元上。</span><span class="sxs-lookup"><span data-stu-id="2f985-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="2f985-278">如果您反轉測量 (先執行第二個量子位元，再執行第一個)，也會發生相同的情況。</span><span class="sxs-lookup"><span data-stu-id="2f985-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="2f985-279">第一個測量是隨機的，第二個測量則會根據第一個測量所發現的結果，以鎖定步驟執行。</span><span class="sxs-lookup"><span data-stu-id="2f985-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="2f985-280">首先我們必須做的是配置 2 個量子位元，而不是 `TestBellState` 中的一個：</span><span class="sxs-lookup"><span data-stu-id="2f985-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="2f985-281">這可讓我們先新增作業 (`CNOT`)，再於 `TestBellState` 中測量 (`M`)：</span><span class="sxs-lookup"><span data-stu-id="2f985-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="2f985-282">我們已新增另一項 `Set` 作業來初始化第一個量子位元，以確保它在作業開始後一律會處於 `Zero` 狀態。</span><span class="sxs-lookup"><span data-stu-id="2f985-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="2f985-283">在加以釋出之前，我們也需要先重設第二個量子位元。</span><span class="sxs-lookup"><span data-stu-id="2f985-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="2f985-284">完整的常式此時會顯示如下：</span><span class="sxs-lookup"><span data-stu-id="2f985-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="2f985-285">如果加以執行，我們會得到與之前相同機率各半的結果。</span><span class="sxs-lookup"><span data-stu-id="2f985-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="2f985-286">不過，我們想知道的是第二個量子位元對第一個測量的量子位元有何反應。</span><span class="sxs-lookup"><span data-stu-id="2f985-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="2f985-287">我們會使用新版本的 `TestBellState` 作業來新增此統計資料：</span><span class="sxs-lookup"><span data-stu-id="2f985-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

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
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="2f985-288">新的傳回值 (`agree`) 會追蹤第一個量子位元的測量與第二個量子位元的測量是否相符。</span><span class="sxs-lookup"><span data-stu-id="2f985-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="2f985-289">我們也必須據以更新主應用程式：</span><span class="sxs-lookup"><span data-stu-id="2f985-289">We also have to update the host application accordingly:</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="2f985-290">Python</span><span class="sxs-lookup"><span data-stu-id="2f985-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="ctabtabid-csharp"></a>[<span data-ttu-id="2f985-291">C#</span><span class="sxs-lookup"><span data-stu-id="2f985-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="2f985-292">執行完成後，會產生讓人眼睛為之一亮的結果：</span><span class="sxs-lookup"><span data-stu-id="2f985-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="2f985-293">如之前在概觀所述，第一個量子位元的統計資料並未變更 (0 或 1 的機率各半)，但現在當我們測量第二個量子位元時，其量值__一律__會與第一個量子位元的相同，因為它們相互纏結!</span><span class="sxs-lookup"><span data-stu-id="2f985-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="2f985-294">恭喜，您已撰寫了第一個量子程式！</span><span class="sxs-lookup"><span data-stu-id="2f985-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="whats-next"></a><span data-ttu-id="2f985-295">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2f985-295">What's next?</span></span>

<span data-ttu-id="2f985-296">「[格羅弗搜尋](xref:microsoft.quantum.quickstarts.search)」快速入門示範如何建立和執行格羅弗搜尋 (最受歡迎的量子運算演算法之一)，並提供 Q# 程式的絕佳範例，可用來解決量子運算的實際問題。</span><span class="sxs-lookup"><span data-stu-id="2f985-296">The QuickStart [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="2f985-297">[開始使用量子開發工具組](xref:microsoft.quantum.welcome)中建議更多學習 Q# 和量子程式設計的方式。</span><span class="sxs-lookup"><span data-stu-id="2f985-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>

