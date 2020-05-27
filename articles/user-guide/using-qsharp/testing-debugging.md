---
title: Тестирование и отладка
description: Узнайте, как использовать модульные тесты, факты и утверждения и функции дампа для тестирования и отладки тактовых программ.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: 374ac42255ab6b2c5eff8ab7879b3a5103181f7f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430923"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="c9e28-103">Тестирование и отладка</span><span class="sxs-lookup"><span data-stu-id="c9e28-103">Testing and debugging</span></span>

<span data-ttu-id="c9e28-104">Как и в случае с классическим программированием, важно иметь возможность проверить, правильно ли работают тактовые программы и может ли она диагностировать неправильные тактовые программы.</span><span class="sxs-lookup"><span data-stu-id="c9e28-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="c9e28-105">В этом разделе мы рассмотрим средства, предлагаемые Q # для тестирования и отладки тактовых программ.</span><span class="sxs-lookup"><span data-stu-id="c9e28-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="c9e28-106">Модульные тесты</span><span class="sxs-lookup"><span data-stu-id="c9e28-106">Unit Tests</span></span>

<span data-ttu-id="c9e28-107">Одним из распространенных подходов к тестированию классических программ является написание небольших программ, именуемых *модульными тестами* , которые выполняют код в библиотеке и сравнивают выходные данные с ожидаемыми выходными данными.</span><span class="sxs-lookup"><span data-stu-id="c9e28-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="c9e28-108">Например, мы можем гарантировать, что возвраты будут возникать `Square(2)` `4` , так как мы узнали *приори* , что $2 ^ 2 = $4.</span><span class="sxs-lookup"><span data-stu-id="c9e28-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="c9e28-109">Q # поддерживает создание модульных тестов для тактовых программ и может выполняться как тесты в среде модульного тестирования [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="c9e28-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="c9e28-110">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="c9e28-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9e28-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9e28-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c9e28-112">Запустите Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c9e28-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="c9e28-113">Перейдите в `File` меню и выберите `New`  >  `Project...` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="c9e28-114">В верхнем правом углу найдите `Q#` и выберите `Q# Test Project` шаблон.</span><span class="sxs-lookup"><span data-stu-id="c9e28-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9e28-115">Командная строка и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9e28-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c9e28-116">В командной строке избранного выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c9e28-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="c9e28-117">Новый проект будет иметь один файл `Tests.qs` , который предоставляет удобное место для определения новых модульных тестов Q #.</span><span class="sxs-lookup"><span data-stu-id="c9e28-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="c9e28-118">Изначально этот файл содержит один пример модульного теста, `AllocateQubit` который проверяет, что вновь выделенное кубит находится в {0} состоянии $ \кет $, и выводит сообщение:</span><span class="sxs-lookup"><span data-stu-id="c9e28-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="c9e28-119">: New. Любая операция или функция Q #, которая принимает аргумент типа `Unit` и возвращает значение, `Unit` может быть помечена как модульный тест с помощью `@Test("...")` атрибута.</span><span class="sxs-lookup"><span data-stu-id="c9e28-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="c9e28-120">Аргумент для этого атрибута `"QuantumSimulator"` выше указывает целевой объект, на котором выполняется тест.</span><span class="sxs-lookup"><span data-stu-id="c9e28-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="c9e28-121">Один тест может выполняться на нескольких целевых объектах.</span><span class="sxs-lookup"><span data-stu-id="c9e28-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="c9e28-122">Например, добавьте атрибут `@Test("ResourcesEstimator")` выше `AllocateQubit` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="c9e28-123">Сохраните файл и выполните все тесты.</span><span class="sxs-lookup"><span data-stu-id="c9e28-123">Save the file and execute all tests.</span></span> <span data-ttu-id="c9e28-124">Теперь должно быть два модульных теста: один, где Аллокатекубит выполняется в Куантумсимулатор, и один, где он выполняется в Ресаурцеестиматор.</span><span class="sxs-lookup"><span data-stu-id="c9e28-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="c9e28-125">Компилятор Q # распознает встроенные целевые объекты "Куантумсимулатор", "Тоффолисимулатор" и "Ресаурцесестиматор" как допустимые целевые объекты выполнения для модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="c9e28-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="c9e28-126">Можно также указать любое полное имя для определения пользовательского целевого объекта выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9e28-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="c9e28-127">Выполнение модульных тестов Q #</span><span class="sxs-lookup"><span data-stu-id="c9e28-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9e28-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9e28-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c9e28-129">В качестве одноразовой настройки для каждого решения перейдите в `Test` меню и выберите `Test Settings`  >  `Default Processor Architecture`  >  `X64` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="c9e28-130">Параметр архитектуры процессора по умолчанию для Visual Studio хранится в файле параметров решения ( `.suo` ) для каждого решения.</span><span class="sxs-lookup"><span data-stu-id="c9e28-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="c9e28-131">При удалении этого файла необходимо `X64` снова выбрать архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="c9e28-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="c9e28-132">Выполните сборку проекта, перейдите в `Test` меню и выберите `Windows`  >  `Test Explorer` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="c9e28-133">`AllocateQubit`будет отображаться в списке тестов в `Not Run Tests` группе.</span><span class="sxs-lookup"><span data-stu-id="c9e28-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="c9e28-134">Выберите `Run All` или запустите этот отдельный тест, и он должен пройти!</span><span class="sxs-lookup"><span data-stu-id="c9e28-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9e28-135">Командная строка и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9e28-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c9e28-136">Чтобы запустить тесты, перейдите в папку проекта (папку, содержащую `Tests.csproj` ) и выполните команду:</span><span class="sxs-lookup"><span data-stu-id="c9e28-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="c9e28-137">Должен отобразиться результат, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="c9e28-137">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="c9e28-138">Модульные тесты можно фильтровать в соответствии с их именем и (или) целевым объектом выполнения:</span><span class="sxs-lookup"><span data-stu-id="c9e28-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="c9e28-139">Встроенная функция <xref:microsoft.quantum.intrinsic.message> имеет тип `(String -> Unit)` и позволяет создавать сообщения диагностики.</span><span class="sxs-lookup"><span data-stu-id="c9e28-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9e28-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9e28-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c9e28-141">После выполнения теста в обозревателе тестов и нажатия кнопки тест появится панель со сведениями о выполнении теста: состояние пройдено/неудачно, затраченное время и ссылка "выходные данные".</span><span class="sxs-lookup"><span data-stu-id="c9e28-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="c9e28-142">Если щелкнуть ссылку "выходные данные", тестовый вывод откроется в новом окне.</span><span class="sxs-lookup"><span data-stu-id="c9e28-142">If you click the "Output" link, test output will open in a new window.</span></span>

![выходные данные теста](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9e28-144">Командная строка и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9e28-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c9e28-145">Состояние "успех/сбой" для каждого теста выводится на консоль `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="c9e28-146">Для неудачных тестов выходные данные также выводятся на консоль для облегчения диагностики сбоя.</span><span class="sxs-lookup"><span data-stu-id="c9e28-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="c9e28-147">Факты и утверждения</span><span class="sxs-lookup"><span data-stu-id="c9e28-147">Facts and Assertions</span></span>

<span data-ttu-id="c9e28-148">Поскольку функции в Q # не имеют _логических_ побочных эффектов, любые _другие виды_ эффектов выполнения функции, тип вывода которой является пустым кортежем, `()` никогда не могут рассматриваться в программе Q #.</span><span class="sxs-lookup"><span data-stu-id="c9e28-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="c9e28-149">Таким образом, целевой компьютер может не выполнять какую-либо функцию, которая возвращает, `()` что это не приведет к изменению поведения любого следующего кода Q #.</span><span class="sxs-lookup"><span data-stu-id="c9e28-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="c9e28-150">Это позволяет функциям возвращать `()` (т. е. `Unit` ) полезные средства для внедрения утверждений и логики отладки в программы Q #.</span><span class="sxs-lookup"><span data-stu-id="c9e28-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="c9e28-151">Рассмотрим простой пример:</span><span class="sxs-lookup"><span data-stu-id="c9e28-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="c9e28-152">Здесь ключевое слово `fail` указывает, что вычисления не должны продолжаться, вызывая исключение на целевом компьютере, на котором выполняется программа Q #.</span><span class="sxs-lookup"><span data-stu-id="c9e28-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="c9e28-153">По определению, сбой этого вида не может рассматриваться в Q #, так как дальнейший код Q # не будет выполняться после `fail` достижения оператора.</span><span class="sxs-lookup"><span data-stu-id="c9e28-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="c9e28-154">Таким же, если мы продолжением вызова `PositivityFact` , мы можем быть уверены, что его входные данные были положительными.</span><span class="sxs-lookup"><span data-stu-id="c9e28-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="c9e28-155">Обратите внимание, что мы можем реализовать такое же поведение, как и при `PositivityFact` использовании [`Fact`](xref:microsoft.quantum.diagnostics.fact) функции из <xref:microsoft.quantum.diagnostics> пространства имен:</span><span class="sxs-lookup"><span data-stu-id="c9e28-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="c9e28-156">*Утверждения*, с другой стороны, используются аналогично фактам, но могут зависеть от состояния целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c9e28-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="c9e28-157">Соответственно, они определяются как операции, тогда как факты определяются как функции (как показано выше).</span><span class="sxs-lookup"><span data-stu-id="c9e28-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="c9e28-158">Чтобы понять различие, рассмотрим следующее применение факта в утверждении:</span><span class="sxs-lookup"><span data-stu-id="c9e28-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="c9e28-159">Здесь мы используем операцию, <xref:microsoft.quantum.environment.getqubitsavailabletouse> чтобы вернуть количество Кубитс, доступных для использования.</span><span class="sxs-lookup"><span data-stu-id="c9e28-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="c9e28-160">Так как это очевидно зависит от глобального состояния программы и среды выполнения, наше определение `AssertQubitsAreAvailable` должно также быть операцией.</span><span class="sxs-lookup"><span data-stu-id="c9e28-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="c9e28-161">Однако можно использовать это глобальное состояние, чтобы получить простое значение в `Bool` качестве входных данных для `Fact` функции.</span><span class="sxs-lookup"><span data-stu-id="c9e28-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="c9e28-162">Основываясь на этих идеях, [версионного](xref:microsoft.quantum.libraries.standard.prelude) предлагает два особо полезных утверждения, <xref:microsoft.quantum.intrinsic.assert> которые <xref:microsoft.quantum.intrinsic.assertprob> моделируются как операции `()` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="c9e28-163">Каждый из этих утверждений принимает Оператор Паули, описывающий определенное измерение интересов, тактовый регистр, на котором выполняется измерение, и гипотетический результат.</span><span class="sxs-lookup"><span data-stu-id="c9e28-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="c9e28-164">На целевых компьютерах, работающих по моделированию, мы не привязаны [к Теорема без клонирования](https://en.wikipedia.org/wiki/No-cloning_theorem)и могут выполнять такие измерения без нарушения регистра, передаваемого в такие утверждения.</span><span class="sxs-lookup"><span data-stu-id="c9e28-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="c9e28-165">Симулятор может, как и приведенная `PositivityFact` выше функция, прерывать вычисления, если гипотетический результат не наблюдается на практике:</span><span class="sxs-lookup"><span data-stu-id="c9e28-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="c9e28-166">На оборудовании физического такта, где Теорема без клонирования предотвращает исследование состояния такта, `Assert` операции и `AssertProb` просто возвращают без какого- `()` либо другого действия.</span><span class="sxs-lookup"><span data-stu-id="c9e28-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="c9e28-167"><xref:microsoft.quantum.diagnostics>Пространство имен предоставляет несколько дополнительных функций `Assert` семейства, которые позволяют проверить более сложные условия.</span><span class="sxs-lookup"><span data-stu-id="c9e28-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="c9e28-168">Функции дампа</span><span class="sxs-lookup"><span data-stu-id="c9e28-168">Dump Functions</span></span>

<span data-ttu-id="c9e28-169">Для облегчения устранения неполадок в тактовых программах <xref:microsoft.quantum.diagnostics> пространство имен предлагает две функции, которые могут выводить дамп в файл текущее состояние целевого компьютера: <xref:microsoft.quantum.diagnostics.dumpmachine> и <xref:microsoft.quantum.diagnostics.dumpregister> .</span><span class="sxs-lookup"><span data-stu-id="c9e28-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="c9e28-170">Созданные выходные данные каждого из них зависят от целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c9e28-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="c9e28-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="c9e28-171">DumpMachine</span></span>

<span data-ttu-id="c9e28-172">Симулятор такта с полным состоянием, распространяемый в составе пакета разработки тактов, записывает в файл [функцию Wave](https://en.wikipedia.org/wiki/Wave_function) всей тактовой системы, в виде одномерного массива комплексных чисел, в котором каждый элемент представляет амплитуду вероятности измерения вычислительного состояния $ \кет{н} $, где $ \кет{н} = \кет{B_ {n-1}... b_1b_0} $ для BITS $ \{ b_i \} $.</span><span class="sxs-lookup"><span data-stu-id="c9e28-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="c9e28-173">Например, на компьютере, где только два выделенных Кубитс и в состоянии такта $ $ \бегин{алигн} \кет{\пси} = \фрак {1} {\скрт {2} } \кет {00} -\фрак{(1 + i)} {2} \кет {10} , \енд{алигн} $ $ вызов <xref:microsoft.quantum.diagnostics.dumpmachine> создает этот результат:</span><span class="sxs-lookup"><span data-stu-id="c9e28-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c9e28-174">Первая строка содержит комментарий с идентификаторами соответствующего Кубитс в значительном порядке.</span><span class="sxs-lookup"><span data-stu-id="c9e28-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="c9e28-175">Остальные строки описывают амплитуду вероятности по измерению вектора состояния базы данных $ \кет{н} $ в декартовой и полярной форматах.</span><span class="sxs-lookup"><span data-stu-id="c9e28-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="c9e28-176">Подробно для первой строки:</span><span class="sxs-lookup"><span data-stu-id="c9e28-176">In detail for the first row:</span></span>

* <span data-ttu-id="c9e28-177">**`∣0❭:`** Эта строка соответствует `0` состоянию вычислительного основания</span><span class="sxs-lookup"><span data-stu-id="c9e28-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="c9e28-178">**`0.707107 +  0.000000 i`**: амплитуда вероятности в формате Декарт.</span><span class="sxs-lookup"><span data-stu-id="c9e28-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="c9e28-179">**` == `**: `equal` знак разписывает оба эквивалентных представления.</span><span class="sxs-lookup"><span data-stu-id="c9e28-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="c9e28-180">**`**********  `**: Графическое представление величины, количество `*` пропорционально вероятности измерения этого вектора состояния.</span><span class="sxs-lookup"><span data-stu-id="c9e28-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="c9e28-181">**`[ 0.500000 ]`**: числовое значение величины.</span><span class="sxs-lookup"><span data-stu-id="c9e28-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="c9e28-182">**`    ---`**: Графическое представление фазы амплитуды (см. ниже).</span><span class="sxs-lookup"><span data-stu-id="c9e28-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="c9e28-183">**`[ 0.0000 rad ]`**: числовое значение этапа (в радианах).</span><span class="sxs-lookup"><span data-stu-id="c9e28-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="c9e28-184">Как величина, так и фаза отображаются с графическим представлением.</span><span class="sxs-lookup"><span data-stu-id="c9e28-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="c9e28-185">Представление величины прямо вперед: в нем отображается полоска `*` , чем больше вероятность, чем увеличено на полосе.</span><span class="sxs-lookup"><span data-stu-id="c9e28-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="c9e28-186">Для этапа показаны следующие символы, представляющие угол на основе диапазонов:</span><span class="sxs-lookup"><span data-stu-id="c9e28-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="c9e28-187">В следующих примерах показаны `DumpMachine` некоторые распространенные состояния.</span><span class="sxs-lookup"><span data-stu-id="c9e28-187">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="c9e28-188">Идентификатор кубит назначается во время выполнения и не обязательно соответствует порядку выделения кубит или его позиции в кубит регистре.</span><span class="sxs-lookup"><span data-stu-id="c9e28-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c9e28-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c9e28-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="c9e28-190">Чтобы определить идентификатор кубит в Visual Studio, поместите точку останова в код и проверьте значение переменной кубит, например:</span><span class="sxs-lookup"><span data-stu-id="c9e28-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![показывать идентификатор кубит в Visual Studio](~/media/qubit_id.png)
  >
  > <span data-ttu-id="c9e28-192">Кубит с индексом `0` с `register2` идентификатором ID = `3` , кубит с индексом `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c9e28-193">Командная строка и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9e28-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="c9e28-194">Вы можете определить идентификатор кубит с помощью <xref:microsoft.quantum.intrinsic.message> функции и передать переменную кубит в сообщении, например:</span><span class="sxs-lookup"><span data-stu-id="c9e28-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="c9e28-195">которые могут формировать этот результат:</span><span class="sxs-lookup"><span data-stu-id="c9e28-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="c9e28-196">Это означает, что кубит с индексом с `0` `register2` идентификатором ID = `3` , кубит с индексом `1` ID = `2` .</span><span class="sxs-lookup"><span data-stu-id="c9e28-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="c9e28-197"><xref:microsoft.quantum.diagnostics.dumpmachine>является частью <xref:microsoft.quantum.diagnostics> пространства имен, поэтому для его использования необходимо добавить `open` оператор:</span><span class="sxs-lookup"><span data-stu-id="c9e28-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="c9e28-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="c9e28-198">DumpRegister</span></span>

<span data-ttu-id="c9e28-199"><xref:microsoft.quantum.diagnostics.dumpregister>работает <xref:microsoft.quantum.diagnostics.dumpmachine> , как, за исключением того, что он также принимает массив Кубитс, чтобы ограничить объем информации, относящейся только к соответствующему Кубитс.</span><span class="sxs-lookup"><span data-stu-id="c9e28-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="c9e28-200">Как и в <xref:microsoft.quantum.diagnostics.dumpmachine> случае, сведения, созданные в, <xref:microsoft.quantum.diagnostics.dumpregister> зависят от целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c9e28-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="c9e28-201">Для имитатора с полным состоянием он записывает в файл функцию Wave вплоть до глобального этапа подсистемы такта, созданной предоставленным Кубитс в том же формате, что и <xref:microsoft.quantum.diagnostics.dumpmachine> .</span><span class="sxs-lookup"><span data-stu-id="c9e28-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="c9e28-202">Например, повторите попытку на компьютере с двумя выделенными Кубитс и в состоянии такта $ $ \бегин{алигн} \кет{\пси} = \фрак {1} {\скрт {2} } \кет {00} -\фрак{(1 + i)} {2} \кет {10} =-e ^ {-i \ PI/4} ((\фрак {1} {\скрт {2} } \кет {0} -\фрак{(1 + i)} {2} \кет {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ). \end{align} $ $ вызов метода <xref:microsoft.quantum.diagnostics.dumpregister> для `qubit[0]` создает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="c9e28-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c9e28-203">и вызов метода <xref:microsoft.quantum.diagnostics.dumpregister> для `qubit[1]` создает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="c9e28-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="c9e28-204">Как правило, состояние регистра, запутанными с другим регистром, находится в смешанном состоянии, а не в чистом состоянии.</span><span class="sxs-lookup"><span data-stu-id="c9e28-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="c9e28-205">В этом случае <xref:microsoft.quantum.diagnostics.dumpregister> выводит следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="c9e28-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="c9e28-206">В следующем примере показано, как можно использовать <xref:microsoft.quantum.diagnostics.dumpregister> и <xref:microsoft.quantum.diagnostics.dumpmachine> в коде Q #:</span><span class="sxs-lookup"><span data-stu-id="c9e28-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="c9e28-207">Отладка</span><span class="sxs-lookup"><span data-stu-id="c9e28-207">Debugging</span></span>

<span data-ttu-id="c9e28-208">Поверх `Assert` функций и `Dump` операций, Q # поддерживает подмножество стандартных возможностей отладки Visual Studio: [Установка точек останова в строке](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [пошаговое выполнение кода с помощью клавиши F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) и [Проверка значений классических переменных](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) во время выполнения кода в симуляторе.</span><span class="sxs-lookup"><span data-stu-id="c9e28-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="c9e28-209">Отладка в Visual Studio Code использует возможности отладки, предоставляемые C# для Visual Studio Code расширения на базе OmniSharp и требует установки [последней версии](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="c9e28-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 