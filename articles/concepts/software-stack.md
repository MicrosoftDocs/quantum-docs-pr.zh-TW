---
title: 軟體堆疊 |Microsoft Docs
description: Software stack
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184724"
---
# <a name="software-stack-for-quantum-computing"></a>用於量子運算的軟體堆疊
通常當我們想到電腦時，我們想像到一個執行應用程式的裝置，但是現代化的運算環境更複雜且更先進。 我們與互動的應用程式通常會在多層的軟體上提供，讓應用程式的執行向下到硬體層級。 這些軟體層是將應用程式解決方案的開發從完整計算系統的基礎複雜度抽象化的必要步驟。 如果開發人員在撰寫簡單的 smartphone 應用程式時，必須考慮匯流排、快取架構、通訊協定等，則工作會變得更複雜。  *軟體堆疊*的概念是在傳統計算中開發，以解決這些問題。  從傳統概念來借用，軟體堆疊也是使用 Q # 進行配量運算的重要部分。

## <a name="conventional-stack"></a>傳統堆疊
軟體堆疊背後的主要概念是遞迴。  它是由數個嵌套的介面層所組成，可將裝置較低層級的詳細資料，從開發人員中抽象化出來。  For example, a commonly used software stack involves running ASP.NET (a programming language), on top of SQL server (a relational database management system), which runs on top of Internet Information Services (a web server), which runs on top of Windows server (an operating system), which drives the computer hardware.  By looking at software as a hierarchy, one can write software in ASP.NET without needing to understand the low-level details of all the software below it.

## <a name="quantum-stack"></a>Quantum stack

The software stack in quantum computing is no different in principle, and in practice operates at a lower level than traditional stacks.  What does a quantum stack look like?  A quantum computer is not a replacement for traditional (often called classical) computers.  In fact, quantum computers will almost certainly work in tandem with classical computers to solve computational problems.  In part, this arises because of the fragility of quantum data.  Quantum data is so fragile that if you even look at it you almost certainly damage the information being observed.  Quantum computers will thus need to be designed with quantum error correction in mind so that stray interactions from its physical environment do not inadvertently damage the information and computation. For this reason, a natural target for Q# is an error-corrected quantum computer (often called a *fault-tolerant* quantum computer) that accepts a list of quantum instructions (called gates or gate operations) and applies those instructions to the quantum data stored within it.  Note that if the number of qubits and gate operations in a quantum algorithm or program is small enough, error correction may not be absolutely necessary.  However as the number of qubits and gate operations grow, it will more certainly be a requirement, thus we architect our software stack and Q# to aptly and efficiently handle error correction and enable scalable, fault-tolerant quantum computing.

### <a name="error-correction"></a>Error correction
Error correction requires a fast and reliable classical computer to be run in concert with the quantum computer to correct errors as they appear in the quantum computation.  In practice, components such as field-programmable gate arrays (FPGAs) or fast cryogenic processors may be needed to identify and correct the errors faster than they naturally accumulate in the quantum computer.  As a result, a quantum computer is a hybrid machine comprised of several different computational devices that operate over a wide range of temperatures.  For this reason, it is much more helpful to think about programming a quantum computer through the lens of a software stack, as there are many layers of hardware and software (classical and quantum) required to ultimately achieve the implementation of a quantum algorithm on a quantum computer.

### <a name="quantum-conceptual-stack"></a>Quantum conceptual stack
A conceptual stack that illustrates the functional flow of factoring 8704143553785700723 in a quantum computing environment is shown below:

![Software stack](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Specification and algorithm
There are several broad stages of programming such a quantum computation.  The first, and arguably most challenging phase, is specifying the problem that one wishes to solve.  In this case, the problem is to factor the number 8704143553785700723  into a product of two prime numbers.  The next step involves designing an algorithm for solving this computational problem.  In this case, Shor's famous quantum factoring algorithm can be used to find the factors.  This algorithm is expressed in Q# and then a sequence of quantum operations is output that could be run on an idealized error-free quantum computer.  

### <a name="physical-gates"></a>Physical gates
In this example, assume nature is not so kind as to provide an error-free quantum computer so the subsequent step takes the operations emitted by Q# and translates them using templates specified by the quantum error correction method chosen into physical gates that the basic hardware can execute.  This process involves replacing every logical qubit described in the previous model with a host of physical qubits that are used to store and protect the information within a single qubit in a redundant fashion that can resist local errors on the constituent physical qubits long enough for such errors to be detected and corrected.  Just as the logical qubits described by the Q# code need to be replaced with many physical qubits, similarly each quantum gate described in the output needs to be translated into a sequence of physical gates that act upon the physical qubits.  For this reason, the output of Q# is seldom the final target for quantum computing and further levels of abstraction are needed to execute the code on hardware in an oblivious fashion.

### <a name="control-computer"></a>Control computer
The physical gate sequence is then loaded into an ordinary computer that sends these instructions down to a control computer that interfaces directly with the quantum computer.  This layer within the software stack is often handled by experimental control software such as [QCoDeS](http://qcodes.github.io/Qcodes/).

### <a name="interface-computer"></a>介面電腦
此程式的最後一個步驟包括介面電腦先視需要將閘道串流至快速控制電腦。 然後，快速控制電腦會套用所需的電壓（通常稱為「脈衝」），以在 qubits 上執行所需的閘道。 這必須在更正透過量子錯誤更正所觀察到的任何錯誤時完成。  可能需要 Cryogenic Fpga 或其他外來硬體，才能在量子電腦出現錯誤的速率所強加的嚴格時間需求內執行這些步驟。  此層級上的目的語言通常是[VHDL](https://en.wikipedia.org/wiki/VHDL)，這需要不同的思考方式，在堆疊的頂端端用來剖析量子演算法的描述。

### <a name="the-q-quantum-programming-language"></a>Q # 量副程式設計語言
問 # 的目的是要提供一種簡單的語言，讓開發人員能夠撰寫以眾多量子運算平臺為目標的程式碼，以及與使用者和量子裝置之間的仲介層軟體互動的介面。  語言藉由採用軟體堆疊的概念，並抽象化基礎量子電腦的許多詳細資料，並允許其他堆疊層級（例如C#，透過之類的語言公開）以執行必要的從 Q # 程式碼到基本作業的翻譯。  這可讓開發人員專注于他們的最佳做法：設計演算法和解決問題。
