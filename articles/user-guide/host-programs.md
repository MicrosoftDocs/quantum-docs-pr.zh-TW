---
title: 執行程式的方式 Q#
description: 概述執行程式的不同方式 Q# 。 從命令列、 Q# Jupyter 筆記本和傳統主機程式（以 Python 或 .net 語言）。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869727"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="acc9e-104">執行程式的方式 Q#</span><span class="sxs-lookup"><span data-stu-id="acc9e-104">Ways to run a Q# program</span></span>

<span data-ttu-id="acc9e-105">其中一個配量開發工具組的最大優點是跨平臺和開發環境的彈性。</span><span class="sxs-lookup"><span data-stu-id="acc9e-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="acc9e-106">不過，這也表示新的 Q# 使用者可能會因為[安裝指南](xref:microsoft.quantum.install)中的許多選項而感到困惑或不知所措。</span><span class="sxs-lookup"><span data-stu-id="acc9e-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="acc9e-107">在此頁面上，我們會說明執行程式時所發生 Q# 的狀況，並比較使用者可以執行的不同方式。</span><span class="sxs-lookup"><span data-stu-id="acc9e-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="acc9e-108">主要的差別在於 Q# 可以執行：</span><span class="sxs-lookup"><span data-stu-id="acc9e-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="acc9e-109">作為獨立應用程式，其中 Q# 是所牽涉到的唯一語言，而程式則是直接叫用。</span><span class="sxs-lookup"><span data-stu-id="acc9e-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="acc9e-110">有兩種方法實際上屬於此類別：</span><span class="sxs-lookup"><span data-stu-id="acc9e-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="acc9e-111">命令列介面</span><span class="sxs-lookup"><span data-stu-id="acc9e-111">the command line interface</span></span>
  - <span data-ttu-id="acc9e-112">Q#Jupyter 筆記本</span><span class="sxs-lookup"><span data-stu-id="acc9e-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="acc9e-113">使用以 Python 或 .NET 語言撰寫的其他*主機程式* (例如 c # 或 F # ) ，接著會叫用程式，並可進一步處理傳回的結果。</span><span class="sxs-lookup"><span data-stu-id="acc9e-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="acc9e-114">為了充分瞭解這些程式及其差異，我們考慮了一個簡單的 Q# 程式，並比較它可以執行的方式。</span><span class="sxs-lookup"><span data-stu-id="acc9e-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="acc9e-115">基本 Q# 程式</span><span class="sxs-lookup"><span data-stu-id="acc9e-115">Basic Q# program</span></span>

<span data-ttu-id="acc9e-116">基本的量副程式可能包含在重迭狀態為 $ \ket $ 和 $ \ket $ 的等中準備 qubit {0} {1} 、測量它，然後傳回結果，而這兩個狀態的其中一種會以相等的機率隨機進行。</span><span class="sxs-lookup"><span data-stu-id="acc9e-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="acc9e-117">事實上，此程式是「[量子亂數產生器](xref:microsoft.quantum.quickstarts.qrng)」快速入門的核心。</span><span class="sxs-lookup"><span data-stu-id="acc9e-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="acc9e-118">在中 Q# ，這會由下列程式碼執行：</span><span class="sxs-lookup"><span data-stu-id="acc9e-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="acc9e-119">不過，此程式碼單獨無法由執行 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="acc9e-120">為此，它需要組成作業的[主體，然後](xref:microsoft.quantum.guide.basics#q-operations-and-functions)在呼叫---直接或另一個作業時執行。</span><span class="sxs-lookup"><span data-stu-id="acc9e-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="acc9e-121">因此，您可以撰寫下列格式的作業：</span><span class="sxs-lookup"><span data-stu-id="acc9e-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="acc9e-122">您已定義 `MeasureSuperposition` 不接受任何輸入的作業，而且會傳回[結果](xref:microsoft.quantum.guide.types)類型的值。</span><span class="sxs-lookup"><span data-stu-id="acc9e-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="acc9e-123">雖然此頁面上的範例只包含 Q# *作業*，但我們所討論的所有概念也等同于函式 Q# \* *，因此我們將它們統稱為*callables\*。</span><span class="sxs-lookup"><span data-stu-id="acc9e-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="acc9e-124">其差異會在[ Q# 基本概念：作業](xref:microsoft.quantum.guide.basics#q-operations-and-functions)和函式中討論，而有關定義它們的詳細資訊可在[作業和](xref:microsoft.quantum.guide.operationsfunctions)函式中找到。</span><span class="sxs-lookup"><span data-stu-id="acc9e-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="acc9e-125">檔案中 Q# 定義的可呼叫</span><span class="sxs-lookup"><span data-stu-id="acc9e-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="acc9e-126">可呼叫的就是所呼叫和所執行的 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="acc9e-127">不過，它還需要一些額外的新增專案，才能組成完整的檔案 `*.qs` Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="acc9e-128">所有 Q# 類型和 callables (您所定義的，以及語言) 內建的，都是在*命名空間*中定義，這會提供可供參考的每一個完整名稱。</span><span class="sxs-lookup"><span data-stu-id="acc9e-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="acc9e-129">例如， [`H`](xref:microsoft.quantum.intrinsic.h) 和 [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 作業可在 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) 和命名空間中找到 [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) (部分的標準連結[ Q# 庫](xref:microsoft.quantum.qsharplibintro)) 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="acc9e-130">因此，一律可以透過其*完整*名稱來呼叫它們， `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 但一律這麼做會導致非常雜亂的程式碼。</span><span class="sxs-lookup"><span data-stu-id="acc9e-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="acc9e-131">相反地， `open` 語句可讓您以更精確的縮寫來參考 callables，如同我們在上述作業主體中所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="acc9e-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="acc9e-132">因此，包含作業的完整檔案 Q# 包括定義我們自己的命名空間、開啟作業所使用之 callables 的命名空間，然後進行作業：</span><span class="sxs-lookup"><span data-stu-id="acc9e-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="acc9e-133">命名空間也可以在開啟時進行*別名*，這有助於在兩個命名空間中的可呼叫/型別名稱衝突時很有説明。</span><span class="sxs-lookup"><span data-stu-id="acc9e-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="acc9e-134">例如，我們可以改為使用 `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` 上述，然後透過呼叫 `H` `NamespaceWithH.H(<qubit>)` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="acc9e-135">其中一個例外狀況是 [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) 命名空間，它一律會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="acc9e-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="acc9e-136">因此，您 [`Length`](xref:microsoft.quantum.core.length) 一律可以直接使用 callables like。</span><span class="sxs-lookup"><span data-stu-id="acc9e-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="acc9e-137">在目的電腦上執行</span><span class="sxs-lookup"><span data-stu-id="acc9e-137">Execution on target machines</span></span>

<span data-ttu-id="acc9e-138">現在，程式的一般執行模式 Q# 會變得很清楚。</span><span class="sxs-lookup"><span data-stu-id="acc9e-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="acc9e-139">首先，要執行的特定可呼叫具有相同命名空間中定義的任何其他 callables 和類型的存取權。</span><span class="sxs-lookup"><span data-stu-id="acc9e-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="acc9e-140">它也會從任何程式庫存取這些連結[ Q# 庫](xref:microsoft.quantum.libraries)，但必須透過其完整名稱或使用上述語句來參考它們 `open` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="acc9e-141">可呼叫的本身會在*[目的電腦](xref:microsoft.quantum.machines)* 上執行。</span><span class="sxs-lookup"><span data-stu-id="acc9e-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="acc9e-142">這類目的機器可以是實際的量子硬體，或 QDK 中提供的多個模擬器。</span><span class="sxs-lookup"><span data-stu-id="acc9e-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="acc9e-143">就我們的目的而言，最有用的目的機器是一種[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器的實例， `QuantumSimulator` 它會計算程式的行為，就像是在免雜訊的量子電腦上執行一樣。</span><span class="sxs-lookup"><span data-stu-id="acc9e-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="acc9e-144">到目前為止，我們已說明在執行特定的可呼叫時，會發生什麼事 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="acc9e-145">不論 Q# 是用於獨立應用程式還是主機程式中，這個一般程式都是更多或更少的---因此 QDK 的彈性。</span><span class="sxs-lookup"><span data-stu-id="acc9e-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="acc9e-146">另一種呼叫量子開發工具組的方法，因此會在叫用呼叫的*方式*中顯示其本身 Q# ，並以何種方式傳回任何結果。</span><span class="sxs-lookup"><span data-stu-id="acc9e-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="acc9e-147">更具體的說，差異在於</span><span class="sxs-lookup"><span data-stu-id="acc9e-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="acc9e-148">指出要執行哪些可呼叫 Q# ，</span><span class="sxs-lookup"><span data-stu-id="acc9e-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="acc9e-149">如何提供可能的可呼叫引數，</span><span class="sxs-lookup"><span data-stu-id="acc9e-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="acc9e-150">指定要在其上執行的目的電腦，以及</span><span class="sxs-lookup"><span data-stu-id="acc9e-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="acc9e-151">傳回任何結果的方式。</span><span class="sxs-lookup"><span data-stu-id="acc9e-151">how any results are returned.</span></span>

<span data-ttu-id="acc9e-152">首先，我們會討論如何 Q# 從命令列使用獨立應用程式來完成此作業，然後繼續使用 Python 和 c # 主機程式。</span><span class="sxs-lookup"><span data-stu-id="acc9e-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="acc9e-153">我們會保留 Jupyter 筆記本的獨立應用程式 Q# ，因為與前三項不同的是，它的主要功能並不是以本機檔案為中心 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="acc9e-154">雖然我們不會在這些範例中說明它，但執行方法之間的一個共同點是，從程式內部列印的任何訊息，都是透過 Q# 或的方式 ([`Message`](xref:microsoft.quantum.intrinsic.message) ，例如 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine)) 通常會列印到個別的主控台。</span><span class="sxs-lookup"><span data-stu-id="acc9e-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-line"></a><span data-ttu-id="acc9e-155">Q#從命令列</span><span class="sxs-lookup"><span data-stu-id="acc9e-155">Q# from the command line</span></span>
<span data-ttu-id="acc9e-156">開始撰寫程式最簡單的方法之一， Q# 就是避免擔心個別檔案和第二種語言。</span><span class="sxs-lookup"><span data-stu-id="acc9e-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="acc9e-157">搭配 QDK 擴充功能使用 Visual Studio Code 或 Visual Studio，可讓我們從單一檔案執行 callables 的順暢工作流程 Q# Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="acc9e-158">為此，我們最終會藉由輸入來叫用程式的執行</span><span class="sxs-lookup"><span data-stu-id="acc9e-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="acc9e-159">在命令列中。</span><span class="sxs-lookup"><span data-stu-id="acc9e-159">in the command line.</span></span>
<span data-ttu-id="acc9e-160">最簡單的工作流程是當終端機的目錄位置與檔案相同時 Q# ，您可以 Q# 使用 VS Code 中的整合式終端機，輕鬆地在檔案編輯的同時進行處理，例如。</span><span class="sxs-lookup"><span data-stu-id="acc9e-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="acc9e-161">不過，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)會接受許多選項，而且只要提供檔案的位置，程式也可以從不同的位置執行 `--project <PATH>` Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="acc9e-162">將進入點新增 Q# 至檔案</span><span class="sxs-lookup"><span data-stu-id="acc9e-162">Add entry point to Q# file</span></span>

<span data-ttu-id="acc9e-163">大部分的檔案 Q# 會包含一個以上的可呼叫，因此，我們需要讓編譯器知道當我們提供命令時要執行*的可*呼叫 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="acc9e-164">這是使用檔案本身的簡單變更來完成 Q# ：</span><span class="sxs-lookup"><span data-stu-id="acc9e-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="acc9e-165">加入具有 `@EntryPoint()` 直接在可呼叫前面的一行。</span><span class="sxs-lookup"><span data-stu-id="acc9e-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="acc9e-166">因此，上述的檔案會變成</span><span class="sxs-lookup"><span data-stu-id="acc9e-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="acc9e-167">現在， `dotnet run` 從命令列呼叫 `MeasureSuperposition` 會導致執行，然後傳回的值會直接列印到終端機。</span><span class="sxs-lookup"><span data-stu-id="acc9e-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="acc9e-168">因此，您會看到 `One` 或 `Zero` 列印。</span><span class="sxs-lookup"><span data-stu-id="acc9e-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="acc9e-169">請注意，如果您在下方定義了更多 callables，則只 `MeasureSuperposition` 會執行。</span><span class="sxs-lookup"><span data-stu-id="acc9e-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="acc9e-170">此外，如果您的可呼叫在宣告之前包含[檔批註](xref:microsoft.quantum.guide.filestructure#documentation-comments)，就不會有任何問題， `@EntryPoint()` 屬性可以直接放在它們的上方。</span><span class="sxs-lookup"><span data-stu-id="acc9e-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="acc9e-171">可呼叫的引數</span><span class="sxs-lookup"><span data-stu-id="acc9e-171">Callable arguments</span></span>

<span data-ttu-id="acc9e-172">到目前為止，我們只考慮不接受輸入的作業。</span><span class="sxs-lookup"><span data-stu-id="acc9e-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="acc9e-173">假設我們想要執行類似的作業，但在多個 qubits 上---提供作為引數的數目。</span><span class="sxs-lookup"><span data-stu-id="acc9e-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="acc9e-174">這類作業可以撰寫成</span><span class="sxs-lookup"><span data-stu-id="acc9e-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="acc9e-175">其中，傳回的值是測量結果的陣列。</span><span class="sxs-lookup"><span data-stu-id="acc9e-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="acc9e-176">請注意， [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 和 [`ForEach`](xref:microsoft.quantum.arrays.foreach) 都在 [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) 和 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 命名空間中， `open` 每個都需要額外的語句。</span><span class="sxs-lookup"><span data-stu-id="acc9e-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="acc9e-177">如果我們將 `@EntryPoint()` 屬性移至這個新作業的前面 (注意，檔案) 中只能有一條這一行，而嘗試執行它只會 `dotnet run` 產生錯誤訊息，指出需要哪些額外的命令列選項，以及如何表達它們。</span><span class="sxs-lookup"><span data-stu-id="acc9e-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="acc9e-178">命令列的一般格式實際上是 `dotnet run [options]` ，而且會在該處提供可呼叫的引數。</span><span class="sxs-lookup"><span data-stu-id="acc9e-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="acc9e-179">在此情況下， `n` 會遺漏引數，並顯示我們需要提供選項 `-n <n>` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="acc9e-180">若要 `MeasureSuperpositionArray` 執行 `n=4` qubits，我們因此使用</span><span class="sxs-lookup"><span data-stu-id="acc9e-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="acc9e-181">產生類似于的輸出</span><span class="sxs-lookup"><span data-stu-id="acc9e-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="acc9e-182">這當然會延伸到多個引數。</span><span class="sxs-lookup"><span data-stu-id="acc9e-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="acc9e-183">在中定義的引數名稱， `camelCase` 會由編譯器稍微改變，以接受作為 Q# 輸入。</span><span class="sxs-lookup"><span data-stu-id="acc9e-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="acc9e-184">例如，如果不是 `n` ，我們使用上述的名稱 `numQubits` ，則會在命令列中透過 `--num-qubits 4` （而不是）來提供此輸入 `-n 4` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="acc9e-185">錯誤訊息也會提供可使用的其他選項，包括如何變更目的電腦。</span><span class="sxs-lookup"><span data-stu-id="acc9e-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="acc9e-186">不同的目的電腦</span><span class="sxs-lookup"><span data-stu-id="acc9e-186">Different target machines</span></span>

<span data-ttu-id="acc9e-187">由於我們的作業輸出在實際的 qubits 上是預期的動作結果，因此從命令列的預設目的電腦就是全狀態 quauntum 模擬器 `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="acc9e-188">不過，我們可以指示 callables 在特定目的電腦上執行，並使用 `--simulator` (或速記 `-s`) 選項。</span><span class="sxs-lookup"><span data-stu-id="acc9e-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="acc9e-189">例如，我們可以在上執行它 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ：</span><span class="sxs-lookup"><span data-stu-id="acc9e-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="acc9e-190">列印的輸出就是</span><span class="sxs-lookup"><span data-stu-id="acc9e-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="acc9e-191">如需這些計量指示的詳細資訊，請參閱[Resource 估計工具：回報的計量](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)。</span><span class="sxs-lookup"><span data-stu-id="acc9e-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="acc9e-192">命令列執行摘要</span><span class="sxs-lookup"><span data-stu-id="acc9e-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="acc9e-193">非 Q# `dotnet run` 選項</span><span class="sxs-lookup"><span data-stu-id="acc9e-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="acc9e-194">如同我們在上面提到的 `--project` 選項，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)也會接受與可呼叫引數無關的選項 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="acc9e-195">如果同時提供兩種選項， `dotnet` 必須先提供特定的選項，後面接著分隔符號 `--` ，然後是 Q# 特定的選項。</span><span class="sxs-lookup"><span data-stu-id="acc9e-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="acc9e-196">例如，針對上述作業，指定路徑和數位 qubits 會透過執行 `dotnet run --project <PATH> -- -n <n>` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="acc9e-197">Q#使用主機程式</span><span class="sxs-lookup"><span data-stu-id="acc9e-197">Q# with host programs</span></span>

<span data-ttu-id="acc9e-198">使用我們的檔案 Q# 時，直接從命令列呼叫作業或函式的替代方法，是使用其他傳統語言的*主機程式*。</span><span class="sxs-lookup"><span data-stu-id="acc9e-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="acc9e-199">具體而言，這可以透過 Python 或 .NET 語言（例如 c # 或 F # (）來完成，因此我們只會在此詳述 c #) 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="acc9e-200">若要啟用互通性，需要進行一些設定，但這些詳細資料可在[安裝指南](xref:microsoft.quantum.install)中找到。</span><span class="sxs-lookup"><span data-stu-id="acc9e-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="acc9e-201">簡言之，這種情況現在包含主機程式檔案 (例如 `*.py` `*.cs` ，或) 在與檔案相同的位置 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="acc9e-202">它現在是已執行的*主機*程式，在執行過程中，它可以從檔案呼叫特定的 Q# 作業和函數 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="acc9e-203">互通性的核心是以編譯器為基礎， Q# 讓主機程式可以存取檔案的內容， Q# 以便呼叫這些檔案。</span><span class="sxs-lookup"><span data-stu-id="acc9e-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="acc9e-204">使用主機程式的其中一個主要優點是，程式所傳回的傳統資料 Q# 可以在主機語言中進一步處理。</span><span class="sxs-lookup"><span data-stu-id="acc9e-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="acc9e-205">這可能是由一些先進的資料處理所組成 (例如，無法在) 內部執行的專案 Q# ，然後 Q# 根據這些結果呼叫進一步的動作，或做為繪製結果的簡單 Q# 方式。</span><span class="sxs-lookup"><span data-stu-id="acc9e-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="acc9e-206">一般的配置如下所示，我們將在下面討論 Python 和 c # 的特定執行。</span><span class="sxs-lookup"><span data-stu-id="acc9e-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="acc9e-207">您可以在[.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)（英文）中找到使用 F # 主機程式的範例。</span><span class="sxs-lookup"><span data-stu-id="acc9e-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="acc9e-208">`@EntryPoint()` Q# 命令列應用程式所使用的屬性不能與主機程式一起使用。</span><span class="sxs-lookup"><span data-stu-id="acc9e-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="acc9e-209">如果主機所呼叫的檔案中有錯誤，則會引發錯誤 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="acc9e-210">若要使用不同的主機程式，檔案不需要進行任何變更 `*.qs` Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="acc9e-211">下列主機程式執行全都使用相同的檔案 Q# ：</span><span class="sxs-lookup"><span data-stu-id="acc9e-211">The following host program implementations all work with the same Q# file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="acc9e-212">選取與您感歡迎的主機語言相對應的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="acc9e-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="acc9e-213">Python</span><span class="sxs-lookup"><span data-stu-id="acc9e-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="acc9e-214">Python 主機程式的結構如下所示：</span><span class="sxs-lookup"><span data-stu-id="acc9e-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="acc9e-215">匯入 `qsharp` 模組，其會註冊模組載入器以進行 Q# 互通性。</span><span class="sxs-lookup"><span data-stu-id="acc9e-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="acc9e-216">這可讓 Q# 命名空間顯示為 Python 模組，我們可以從這裡「匯入」 Q# callables。</span><span class="sxs-lookup"><span data-stu-id="acc9e-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="acc9e-217">請注意，技術上並不是匯 Q# 入的 callables 本身，而是允許呼叫它們的 Python 存根。</span><span class="sxs-lookup"><span data-stu-id="acc9e-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="acc9e-218">然後這些類別的行為就像是 Python 類別的物件，我們會使用方法來指定要將作業傳送至執行的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="acc9e-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="acc9e-219">匯入這些 Q# callables，我們將在此案例中直接叫用--- `MeasureSuperposition` 和 `MeasureSuperpositionArray` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="acc9e-220">匯 `qsharp` 入模組之後，您也可以直接從連結 Q# 庫命名空間匯入 callables。</span><span class="sxs-lookup"><span data-stu-id="acc9e-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="acc9e-221">在任何其他 Python 程式碼中，您現在可以在特定目的電腦上呼叫這些 callables，並將它們的傳回指派給變數， (如果傳回值) 以供進一步使用。</span><span class="sxs-lookup"><span data-stu-id="acc9e-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="acc9e-222">指定目的電腦</span><span class="sxs-lookup"><span data-stu-id="acc9e-222">Specifying target machines</span></span>
<span data-ttu-id="acc9e-223">呼叫要在特定目的電腦上執行的作業，是透過匯入物件上不同的 Python 方法來完成。</span><span class="sxs-lookup"><span data-stu-id="acc9e-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="acc9e-224">例如， `.simulate(<args>)` `QuantumSimulator` 會使用來執行作業，而 `.estimate_resources(<args>)` 則是在上執行 `ResourcesEstimator` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="acc9e-225">將輸入傳遞至 Q\#</span><span class="sxs-lookup"><span data-stu-id="acc9e-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="acc9e-226">可呼叫的引數 Q# 應該以關鍵字引數的形式提供，其中關鍵字是可呼叫定義中的引數名稱 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="acc9e-227">也就是 `MeasureSuperpositionArray.simulate(n=4)` 有效，而則 `MeasureSuperpositionArray.simulate(4)` 會擲回錯誤。</span><span class="sxs-lookup"><span data-stu-id="acc9e-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="acc9e-228">因此，Python 主機程式</span><span class="sxs-lookup"><span data-stu-id="acc9e-228">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="acc9e-229">會產生如下所示的輸出：</span><span class="sxs-lookup"><span data-stu-id="acc9e-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="acc9e-230">C#</span><span class="sxs-lookup"><span data-stu-id="acc9e-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="acc9e-231">C # 主機程式有多個元件，而且非常接近 QDK 的某些元件，例如模擬器，其本身是以 c # 為基礎。</span><span class="sxs-lookup"><span data-stu-id="acc9e-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="acc9e-232">Q#編譯器的運作方式是從檔案中的命名空間產生名為 c # 的命名空間 Q# Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="acc9e-233">它會針對其中所定義的每個 callables 或類型，進一步產生名為的 c # 類別 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="acc9e-234">首先，我們會將主機程式中使用的任何類別提供 `using` 給語句使用，其大致類似于為檔案 `open` 中的語句 Q# ：</span><span class="sxs-lookup"><span data-stu-id="acc9e-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="acc9e-235">接下來，我們會宣告 c # 命名空間、一些其他部分和片段 (在) 之下看到完整的程式碼區塊，然後使用任何傳統程式設計 (（例如計算 callables) 的引數） Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="acc9e-236">在我們的案例中，這不是必要的，但在[.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)中可以找到這種用法的範例。</span><span class="sxs-lookup"><span data-stu-id="acc9e-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="acc9e-237">目標電腦</span><span class="sxs-lookup"><span data-stu-id="acc9e-237">Target machines</span></span>

<span data-ttu-id="acc9e-238">回到 Q# ，我們必須建立要在其中執行作業的目的電腦的實例。</span><span class="sxs-lookup"><span data-stu-id="acc9e-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="acc9e-239">使用其他目的機器就像具現化不同的電腦一樣簡單，不過執行此作業和處理傳回的方式可能稍有不同。</span><span class="sxs-lookup"><span data-stu-id="acc9e-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="acc9e-240">為求簡潔，我們現在會將設為 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ，並包含 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [下列](#including-the-resources-estimator)。</span><span class="sxs-lookup"><span data-stu-id="acc9e-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="acc9e-241">從作業產生的每個 c # 類別 Q# 都有 `Run` 方法，其第一個引數必須是目的機器實例。</span><span class="sxs-lookup"><span data-stu-id="acc9e-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="acc9e-242">因此，若要 `MeasureSuperposition` 在上執行 `QuantumSimulator` ，我們使用 `MeasureSuperposition.Run(sim)` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="acc9e-243">然後，可以將傳回的結果指派給 c # 中的變數：</span><span class="sxs-lookup"><span data-stu-id="acc9e-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="acc9e-244">`Run`方法會以非同步方式執行，因為這會是實際量子硬體的情況，因此 `await` 關鍵字會封鎖進一步執行，直到工作完成為止。</span><span class="sxs-lookup"><span data-stu-id="acc9e-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="acc9e-245">如果可呼叫的沒有任何傳回 (也就是 Q#) 的傳回型別 `Unit` ，則執行仍然可以相同的方式進行，而不需要將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="acc9e-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="acc9e-246">在此情況下，整個程式程式碼只會包含</span><span class="sxs-lookup"><span data-stu-id="acc9e-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="acc9e-247">引數</span><span class="sxs-lookup"><span data-stu-id="acc9e-247">Arguments</span></span>

<span data-ttu-id="acc9e-248">可呼叫的任何引數 Q# 只會當做 afer 目的電腦的其他引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="acc9e-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="acc9e-249">因此，qubits 上的結果會透過來 `MeasureSuperpositionArray` `n=4` 提取</span><span class="sxs-lookup"><span data-stu-id="acc9e-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="acc9e-250">因此，完整的 c # 主機程式可能如下所示</span><span class="sxs-lookup"><span data-stu-id="acc9e-250">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="acc9e-251">在 c # 檔案的位置，您可以在命令列中輸入來執行主機程式。</span><span class="sxs-lookup"><span data-stu-id="acc9e-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="acc9e-252">在此情況下，您會看到寫入主控台的輸出，如下所示</span><span class="sxs-lookup"><span data-stu-id="acc9e-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="acc9e-253">由於編譯器與命名空間的互通性，我們也可以 Q# 在沒有語句的情況下提供 callables `using NamespaceName;` ，並只比對 c # 命名空間的標題。</span><span class="sxs-lookup"><span data-stu-id="acc9e-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="acc9e-254">也就是將取代 `namespace host` 為 `namespace NamespaceName` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="acc9e-255">包含資源估計工具</span><span class="sxs-lookup"><span data-stu-id="acc9e-255">Including the resources estimator</span></span>

<span data-ttu-id="acc9e-256">[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)需要稍微不同的實作為捕獲輸出。</span><span class="sxs-lookup"><span data-stu-id="acc9e-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="acc9e-257">首先，改為使用語句來將它們具現化為變數 `using` (如同我們處理 `QuantumSimulator`) ，我們會透過將類別的物件更直接具現化</span><span class="sxs-lookup"><span data-stu-id="acc9e-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="acc9e-258">請注意，而不是多個作業所使用的單一目標模擬器 Q# ，我們已為每個作業具現化一個。</span><span class="sxs-lookup"><span data-stu-id="acc9e-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="acc9e-259">這是因為物件本身會在做為目的機器時修改，而且之後可以使用類別方法來抓取其結果 `.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="acc9e-260">若要在資源估算器上執行作業，我們使用</span><span class="sxs-lookup"><span data-stu-id="acc9e-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="acc9e-261">然後以 tab 鍵分隔值的形式提取結果， (TSV) 搭配 `estimatorSingleQ.ToTSV()` 和 `estimatorMultiQ.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="acc9e-262">因此，完整的 c # 主機程式使用 `QuantumSimulator` 和都 `ResourcesEstimator` 可以採用下列格式：</span><span class="sxs-lookup"><span data-stu-id="acc9e-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="acc9e-263">這會產生類似的輸出</span><span class="sxs-lookup"><span data-stu-id="acc9e-263">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="acc9e-264">Q#Jupyter 筆記本</span><span class="sxs-lookup"><span data-stu-id="acc9e-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="acc9e-265">Q#Jupyter 筆記本利用 I Q# 核心，可讓您在單一筆記本中定義、編譯和執行 Q# callables，---全部都隨附指示、附注和其他內容。</span><span class="sxs-lookup"><span data-stu-id="acc9e-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="acc9e-266">這表示雖然可以匯入和使用檔案的內容 `*.qs` Q# ，但它們在執行模型中並不是必要的。</span><span class="sxs-lookup"><span data-stu-id="acc9e-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="acc9e-267">在這裡，我們將詳細說明如何執行 Q# 上述定義的作業，但在 Q# [簡介 Q# 和 Jupyter 筆記本](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中，會提供使用 Jupyter 筆記本的更廣泛簡介。</span><span class="sxs-lookup"><span data-stu-id="acc9e-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="acc9e-268">定義作業</span><span class="sxs-lookup"><span data-stu-id="acc9e-268">Defining operations</span></span>

<span data-ttu-id="acc9e-269">在 Q# Jupyter Notebook 中，您會輸入程式碼，就像我們在檔案的 Q# 命名空間內所做的一樣 Q# 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="acc9e-270">因此，我們可以使用適用于其個別命名空間的語句，從[ Q# 標準程式庫](xref:microsoft.quantum.qsharplibintro)啟用 callables 的存取權 `open` 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="acc9e-271">使用這類語句執行資料格時，這些命名空間的定義可在整個工作區中使用。</span><span class="sxs-lookup"><span data-stu-id="acc9e-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="acc9e-272">Callables 會[Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 自動提供給 Q# Jupyter 筆記本中的資料格內所定義的作業，而 Canon (例如和) 。</span><span class="sxs-lookup"><span data-stu-id="acc9e-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="acc9e-273">不過，從外部來源檔案引入的程式碼不是如此， Q# ([簡介 Q# 和 Jupyter 筆記本](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)) 所顯示的進程。</span><span class="sxs-lookup"><span data-stu-id="acc9e-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="acc9e-274">同樣地，定義作業只需要撰寫程式 Q# 代碼並執行儲存格。</span><span class="sxs-lookup"><span data-stu-id="acc9e-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="acc9e-275">然後，輸出會列出這些作業，然後再從未來的資料格進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="acc9e-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="acc9e-276">目標電腦</span><span class="sxs-lookup"><span data-stu-id="acc9e-276">Target machines</span></span>

<span data-ttu-id="acc9e-277">在特定目的電腦上執行作業的功能是透過[我的 Q# 魔術命令](xref:microsoft.quantum.guide.quickref.iqsharp)來提供。</span><span class="sxs-lookup"><span data-stu-id="acc9e-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="acc9e-278">例如， `%simulate` 會使用 `QuantumSimulator` ，並 `%estimate` 使用 `ResourcesEstimator` ：</span><span class="sxs-lookup"><span data-stu-id="acc9e-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="acc9e-279">將輸入傳遞至函數和作業</span><span class="sxs-lookup"><span data-stu-id="acc9e-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="acc9e-280">執行魔術命令目前只能搭配不接受引數的作業使用。</span><span class="sxs-lookup"><span data-stu-id="acc9e-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="acc9e-281">因此，若要執行，我們必須定義「包裝函式」作業， `MeasureSuperpositionArray` 然後使用引數呼叫作業：</span><span class="sxs-lookup"><span data-stu-id="acc9e-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="acc9e-282">這項作業當然可以與 `%estimate` 和其他執行命令類似使用。</span><span class="sxs-lookup"><span data-stu-id="acc9e-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
