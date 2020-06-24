---
title: Счетчик глубины
description: Узнайте о счетчике Microsoft КДК Depth, который собирает количество всех операций, вызванных в тактовой программе.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275628"
---
# <a name="depth-counter"></a><span data-ttu-id="7f172-103">Счетчик глубины</span><span class="sxs-lookup"><span data-stu-id="7f172-103">Depth Counter</span></span>

<span data-ttu-id="7f172-104">`Depth Counter`Компонент является частью [имитатора трассировки](xref:microsoft.quantum.machines.qc-trace-simulator.intro)компьютерных тактов.</span><span class="sxs-lookup"><span data-stu-id="7f172-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="7f172-105">Он используется для сбора данных о глубине каждой операции, вызванной в тактовой программе.</span><span class="sxs-lookup"><span data-stu-id="7f172-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="7f172-106">Все операции из <xref:microsoft.quantum.intrinsic> выражаются в виде однокубитных поворотов, T-шлюзов, одного кубит Клиффорд Гейтсов, шлюзов кнот и измерений Multi-кубит Паули observable.</span><span class="sxs-lookup"><span data-stu-id="7f172-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="7f172-107">Пользователи могут задать глубину для каждой из примитивных операций с помощью `gateTimes` поля <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="7f172-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="7f172-108">По умолчанию все операции имеют глубину 0, кроме шлюза T, имеющего глубину 1.</span><span class="sxs-lookup"><span data-stu-id="7f172-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="7f172-109">Это означает, что вычисление производится только по умолчанию (что часто желательно).</span><span class="sxs-lookup"><span data-stu-id="7f172-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="7f172-110">Собранные статистические данные суммируются по всем краям графа вызовов операций.</span><span class="sxs-lookup"><span data-stu-id="7f172-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="7f172-111">Теперь мы вычислим <xref:microsoft.quantum.intrinsic.t> глубину <xref:microsoft.quantum.intrinsic.ccnot> операции.</span><span class="sxs-lookup"><span data-stu-id="7f172-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="7f172-112">Мы будем использовать следующий пример кода Q #:</span><span class="sxs-lookup"><span data-stu-id="7f172-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="7f172-113">Использование счетчика глубины в программе C#</span><span class="sxs-lookup"><span data-stu-id="7f172-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="7f172-114">Чтобы проверить, что `CCNOT` имеет `T` глубину 5 и `ApplySampleWithCCNOT` имеет `T` глубину 6, мы можем использовать следующий код C#:</span><span class="sxs-lookup"><span data-stu-id="7f172-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="7f172-115">Выполняется первая часть программы `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="7f172-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="7f172-116">Во второй части мы используем метод `QCTraceSimulator.GetMetric` для получения `T` глубины `CCNOT` и `ApplySampleWithCCNOT` :</span><span class="sxs-lookup"><span data-stu-id="7f172-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="7f172-117">Наконец, чтобы вывести всю статистику, собранную `Depth Counter` в формате CSV, можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7f172-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="7f172-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7f172-118">See also</span></span> ##

- <span data-ttu-id="7f172-119">Обзор [имитатора трассировки](xref:microsoft.quantum.machines.qc-trace-simulator.intro) компьютерных тактов.</span><span class="sxs-lookup"><span data-stu-id="7f172-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>