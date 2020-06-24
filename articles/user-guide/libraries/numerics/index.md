---
title: Базовые сведения о библиотеке Quantum Numerics | Документация Майкрософт
description: Базовые сведения о библиотеке Quantum Numerics
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273968"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="03a5c-103">Базовые сведения о библиотеке Quantum Numerics</span><span class="sxs-lookup"><span data-stu-id="03a5c-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="03a5c-104">Многие квантовые алгоритмы используют [оракулов](xref:microsoft.quantum.concepts.oracles), которые оценивают математические функции как суперпозицию входных данных.</span><span class="sxs-lookup"><span data-stu-id="03a5c-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="03a5c-105">Например, основной компонент алгоритма Шора оценивает выражение $f(x) = a^x\operatorname{mod} N$ для фиксированного значения $a$, раскладываемого на множители числа $N$, и значения $x$ с целочисленным типом из $2n$ кубитов с равномерным распределением по всем строкам длиной $2n$ бит.</span><span class="sxs-lookup"><span data-stu-id="03a5c-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="03a5c-106">Чтобы выполнить алгоритм Шора на реальном квантовом компьютере, эту функцию нужно переписать в синтаксис операций, поддерживаемых целевым компьютером.</span><span class="sxs-lookup"><span data-stu-id="03a5c-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="03a5c-107">Используя двоичное представление $x$, где $x_i$ обозначает $i$-й бит, начиная с наименее значимого, мы можем записать $f(x)$ как $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="03a5c-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="03a5c-108">В свою очередь, это выражение преобразуется в product (mod N) для терминов $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="03a5c-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="03a5c-109">Это позволяет реализовать функцию $f(x)$ в виде последовательности $2n$ (modular) умножений на $a^{2^i}$ с дополнительным условием, что $x_i$ не равно нулю.</span><span class="sxs-lookup"><span data-stu-id="03a5c-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="03a5c-110">Константы $a^{2^i}$ можно вычислить заранее и сократить до остатка от деления на N до выполнения алгоритма.</span><span class="sxs-lookup"><span data-stu-id="03a5c-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="03a5c-111">Такую последовательность управляемых модульных операций умножения можно еще упростить. Каждое умножение можно выполнять через последовательность из $n$ контролируемых модульных сложений, где каждое модульное сложение создается из обычного сложения и блока сравнения.</span><span class="sxs-lookup"><span data-stu-id="03a5c-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="03a5c-112">Учитывая, что для фактической реализации нужно так много действий, было бы очень полезно сразу иметь такую функциональность.</span><span class="sxs-lookup"><span data-stu-id="03a5c-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="03a5c-113">Поэтому Quantum Development Kit поддерживает широкий спектр операций с числами.</span><span class="sxs-lookup"><span data-stu-id="03a5c-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="03a5c-114">Функциональность</span><span class="sxs-lookup"><span data-stu-id="03a5c-114">Functionality</span></span>

<span data-ttu-id="03a5c-115">Помимо целочисленной арифметики, которую мы уже упоминали, библиотека числовых значений предоставляет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="03a5c-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="03a5c-116">Работа с целыми числами со знаком и без знака (умножение, возведение в квадрат, деление с остатком, инверсия, и т. д.), где в качестве входных данных принимаются одно или два целых числа в квантовом формате.</span><span class="sxs-lookup"><span data-stu-id="03a5c-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="03a5c-117">Работа с фиксированной десятичной запятой (сложение и вычитание, умножение, возведение в квадрат, обратное значение, полиномиальная оценка), где в качестве входных данных принимается одно или два числа с фиксированной запятой.</span><span class="sxs-lookup"><span data-stu-id="03a5c-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="03a5c-118">Начало работы</span><span class="sxs-lookup"><span data-stu-id="03a5c-118">Getting started</span></span>

<span data-ttu-id="03a5c-119">Чтобы начать работу с библиотекой числовых значений, изучите [руководство по установке](xref:microsoft.quantum.numerics.installation) и дополнительные сведения [об использовании библиотеки числовых значений](xref:microsoft.quantum.numerics.usage).</span><span class="sxs-lookup"><span data-stu-id="03a5c-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>