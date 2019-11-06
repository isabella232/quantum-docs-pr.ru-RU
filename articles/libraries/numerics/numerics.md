---
title: Использование библиотеки числовых библиотек | Документация Майкрософт
description: Использование библиотеки числовых средств
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184616"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="4d7ad-103">Использование библиотеки числовых средств</span><span class="sxs-lookup"><span data-stu-id="4d7ad-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="4d7ad-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="4d7ad-104">Overview</span></span>

<span data-ttu-id="4d7ad-105">Библиотека числовых данных состоит из трех компонентов.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="4d7ad-106">**Базовая целочисленная арифметика** с целочисленным методах и операторами сравнения</span><span class="sxs-lookup"><span data-stu-id="4d7ad-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="4d7ad-107">**Высокоуровневые целочисленные функции** , построенные на основе базовой функциональности; Он включает умножение, деление, инверсию и т. д.  для целых чисел со знаком и без знака.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="4d7ad-108">**Арифметические функции с фиксированной запятой** с инициализацией, сложение, умножение, обратная Оценка и измерение.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="4d7ad-109">Доступ ко всем этим компонентам можно получить с помощью одной инструкции `open`:</span><span class="sxs-lookup"><span data-stu-id="4d7ad-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="4d7ad-110">Типы</span><span class="sxs-lookup"><span data-stu-id="4d7ad-110">Types</span></span>

<span data-ttu-id="4d7ad-111">Библиотека числовых типов поддерживает следующие типы</span><span class="sxs-lookup"><span data-stu-id="4d7ad-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="4d7ad-112">**`LittleEndian`** : массив кубит `qArr : Qubit[]`, представляющий целое число, где `qArr[0]` обозначает наименее значащий бит.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="4d7ad-113">**`SignedLittleEndian`** : то же, что `LittleEndian`, за исключением того, что он представляет целое число со знаком, хранящееся в дополнениех двух.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="4d7ad-114">**`FixedPoint`** : представляет вещественное число, состоящее из массива кубит `qArr2 : Qubit[]` и позиции двоичной точки `pos`, которая подсчитывает количество двоичных разрядов слева от двоичной точки.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="4d7ad-115">`qArr2` хранится так же, как `SignedLittleEndian`.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="4d7ad-116">Operations</span><span class="sxs-lookup"><span data-stu-id="4d7ad-116">Operations</span></span>

<span data-ttu-id="4d7ad-117">Для каждого из трех перечисленных выше типов доступны различные операции:</span><span class="sxs-lookup"><span data-stu-id="4d7ad-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="4d7ad-118">Сложение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-118">Addition</span></span>
    - <span data-ttu-id="4d7ad-119">Сравнение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-119">Comparison</span></span>
    - <span data-ttu-id="4d7ad-120">Умножение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-120">Multiplication</span></span>
    - <span data-ttu-id="4d7ad-121">Ведения</span><span class="sxs-lookup"><span data-stu-id="4d7ad-121">Squaring</span></span>
    - <span data-ttu-id="4d7ad-122">Деление (с остатком)</span><span class="sxs-lookup"><span data-stu-id="4d7ad-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="4d7ad-123">Сложение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-123">Addition</span></span>
    - <span data-ttu-id="4d7ad-124">Сравнение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-124">Comparison</span></span>
    - <span data-ttu-id="4d7ad-125">Дополнение модуля инверсии по модулю 2</span><span class="sxs-lookup"><span data-stu-id="4d7ad-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="4d7ad-126">Умножение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-126">Multiplication</span></span>
    - <span data-ttu-id="4d7ad-127">Ведения</span><span class="sxs-lookup"><span data-stu-id="4d7ad-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="4d7ad-128">Подготовка или инициализация для классических значений</span><span class="sxs-lookup"><span data-stu-id="4d7ad-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="4d7ad-129">Сложение (классическая константа или другой такт с фиксированной точкой)</span><span class="sxs-lookup"><span data-stu-id="4d7ad-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="4d7ad-130">Сравнение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-130">Comparison</span></span>
    - <span data-ttu-id="4d7ad-131">Умножение</span><span class="sxs-lookup"><span data-stu-id="4d7ad-131">Multiplication</span></span>
    - <span data-ttu-id="4d7ad-132">Ведения</span><span class="sxs-lookup"><span data-stu-id="4d7ad-132">Squaring</span></span>
    - <span data-ttu-id="4d7ad-133">Оценка полинома с специализацией для четных и нечетных функций</span><span class="sxs-lookup"><span data-stu-id="4d7ad-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="4d7ad-134">Обратная (1/x)</span><span class="sxs-lookup"><span data-stu-id="4d7ad-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="4d7ad-135">Измерение (классическое значение Double)</span><span class="sxs-lookup"><span data-stu-id="4d7ad-135">Measurement (classical Double)</span></span>

<span data-ttu-id="4d7ad-136">Дополнительные сведения и подробную документацию по каждой из этих операций см. в справочной документации по библиотеке Q # по адресу [docs.Microsoft.com](https://docs.microsoft.com/en-us/quantum)</span><span class="sxs-lookup"><span data-stu-id="4d7ad-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/en-us/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="4d7ad-137">Пример: сложение целых чисел</span><span class="sxs-lookup"><span data-stu-id="4d7ad-137">Sample: Integer addition</span></span>

<span data-ttu-id="4d7ad-138">В качестве простого примера рассмотрим операцию $ $ \кет кс\кет и\мапсто \кет кс\кет {x + y} $ $, т. е. операцию, которая принимает n-кубит целое $x $ и n-или (n + 1)-кубит Register $y $ в качестве входных данных, второй из которых сопоставляется с суммой $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="4d7ad-139">Обратите внимание, что сумма вычисляется по модулю $2 ^ n $, если $y $ хранится в $n $-разрядном регистре.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="4d7ad-140">С помощью пакета средств разработки тактов эту операцию можно применить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d7ad-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="4d7ad-141">Пример. Вычисление гладких функций</span><span class="sxs-lookup"><span data-stu-id="4d7ad-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="4d7ad-142">Для вычисления гладких функций, таких как $ \син (x) $, на компьютере-такте, где $x $ является `FixedPoint`ным числом, Библиотека числовых пакетов разработки тактов предоставляет операции `EvaluatePolynomialFxP` и `Evaluate[Even/Odd]PolynomialFxP`.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="4d7ad-143">Первый, `EvaluatePolynomialFxP`, позволяет оценить полином вида $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \кдотс + a_dx ^ d, $ $, где $d $ обозначает *степень*.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="4d7ad-144">Для этого все, что требуется, — это коэффициенты полинома `[a_0,..., a_d]` (типа `Double[]`), входные `x : FixedPoint` и выходное `y : FixedPoint` (изначально ноль):</span><span class="sxs-lookup"><span data-stu-id="4d7ad-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="4d7ad-145">Результат, $P (x) = 1 + 2x $, будет храниться в `yFxP`.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="4d7ad-146">Второй, `EvaluateEvenPolynomialFxP`и третий `EvaluateOddPolynomialFxP`, являются специализациями для случаев четных и нечетных функций соответственно.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="4d7ad-147">Это значит, что для четной или нечетной функции $f (x) $ и $ $ P_ {четный} (x) = a_0 + A_1 x ^ 2 + A_2 x ^ 4 + \кдотс + a_d x ^ {2D}, $ $ $f (x) $ приблизительно хорошо подходит для $P _ {четный} (x) $ или $P _ {нечет} (x): = кс\кдот P_ {четный} (x) $ содержани.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="4d7ad-148">В Q # эти два варианта можно обработать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d7ad-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="4d7ad-149">который вычисляет $P _ {четный} (x) = 1 + 2x ^ 2 $ и</span><span class="sxs-lookup"><span data-stu-id="4d7ad-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="4d7ad-150">который вычисляет $P _ {нечетный} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="4d7ad-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="4d7ad-151">Другие примеры</span><span class="sxs-lookup"><span data-stu-id="4d7ad-151">More samples</span></span>

<span data-ttu-id="4d7ad-152">Дополнительные примеры можно найти в [основном репозитории примеров](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="4d7ad-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="4d7ad-153">Чтобы приступить к работе, клонировать репозиторий и открыть вложенную папку `Numerics`:</span><span class="sxs-lookup"><span data-stu-id="4d7ad-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="4d7ad-154">Затем `cd` в один из примеров папок и запустите пример с помощью</span><span class="sxs-lookup"><span data-stu-id="4d7ad-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```