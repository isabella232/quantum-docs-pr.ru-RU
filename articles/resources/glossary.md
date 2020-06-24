---
title: Глоссарий по тактовым вычислениям
description: Глоссарий общих терминов, действий и объектов, используемых в тактовых вычислениях.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: ba4d171d84d808f082b919dcc6156d9c65df7c05
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275363"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="57331-103">Глоссарий по тактовым вычислениям</span><span class="sxs-lookup"><span data-stu-id="57331-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="57331-104">Прилегающий</span><span class="sxs-lookup"><span data-stu-id="57331-104">Adjoint</span></span>

<span data-ttu-id="57331-105">Комплексно сопряженное перестановка [операции](xref:microsoft.quantum.glossary#operation).</span><span class="sxs-lookup"><span data-stu-id="57331-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="57331-106">Для операций, реализующих оператор с [единым](xref:microsoft.quantum.glossary#unitary-operator) , примыкающим является обратная операция и обозначается символом дагжер.</span><span class="sxs-lookup"><span data-stu-id="57331-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="57331-107">Например, если операция `U` представляет собой оператор $U $ , то `Adjoint U` представляет $U ^ \дагжер $ .</span><span class="sxs-lookup"><span data-stu-id="57331-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="57331-108">Дополнительные сведения см. в разделе [прилегающие](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="57331-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="57331-109">анЦилла</span><span class="sxs-lookup"><span data-stu-id="57331-109">Ancilla</span></span>

<span data-ttu-id="57331-110">[Кубит](xref:microsoft.quantum.glossary#qubit) , который служит временной памятью для тактового компьютера и выделяется и освобождается по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="57331-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="57331-111">Дополнительные сведения см. в разделе [несколько Кубитс](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="57331-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="57331-112">Состояние колокольчика</span><span class="sxs-lookup"><span data-stu-id="57331-112">Bell state</span></span>

<span data-ttu-id="57331-113">Одно из четырех конкретных [запутанными](xref:microsoft.quantum.glossary#entanglement) [состояний такта](xref:microsoft.quantum.glossary#quantum-state) двух Кубитс.</span><span class="sxs-lookup"><span data-stu-id="57331-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="57331-114">Четыре состояния определяются как $ \кет { \ beta_ {ИЖ } } = (\Масбб{и } \Отимес X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="57331-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="57331-115">Состояние колокольчика также называется [парой EPR](xref:microsoft.quantum.glossary#epr-pair).</span><span class="sxs-lookup"><span data-stu-id="57331-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="57331-116">БЛОЧ шар</span><span class="sxs-lookup"><span data-stu-id="57331-116">Bloch sphere</span></span>

<span data-ttu-id="57331-117">Графическое представление[однокубитного](xref:microsoft.quantum.glossary#qubit) [состояния такта](xref:microsoft.quantum.glossary#quantum-state) в виде точки трехмерной единичной сферы.</span><span class="sxs-lookup"><span data-stu-id="57331-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="57331-118">Дополнительные сведения см. [в разделе визуализация Кубитс и преобразований с помощью сферы БЛОЧ](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="57331-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="57331-119">Предназначен</span><span class="sxs-lookup"><span data-stu-id="57331-119">Callable</span></span>

<span data-ttu-id="57331-120">[Операция](xref:microsoft.quantum.glossary#operation) или [функция](xref:microsoft.quantum.glossary#function) в языке Q #.</span><span class="sxs-lookup"><span data-stu-id="57331-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="57331-121">Дополнительные сведения см. в разделе [операции и функции](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="57331-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="57331-122">Группа Клиффорд</span><span class="sxs-lookup"><span data-stu-id="57331-122">Clifford group</span></span>

<span data-ttu-id="57331-123">Набор операций, которые занимают октантс [БЛОЧ Sphere](xref:microsoft.quantum.glossary#bloch-sphere) и влияют на перестановки [операторов Паули](xref:microsoft.quantum.glossary#pauli-operators).</span><span class="sxs-lookup"><span data-stu-id="57331-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="57331-124">К ним относятся операции [$X $ ](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [$Z $ ](xref:microsoft.quantum.intrinsic.z), [$H $ ](xref:microsoft.quantum.intrinsic.h) и [$S $ ](xref:microsoft.quantum.intrinsic.s).</span><span class="sxs-lookup"><span data-stu-id="57331-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="57331-125">Управляет</span><span class="sxs-lookup"><span data-stu-id="57331-125">Controlled</span></span>

<span data-ttu-id="57331-126">[Операция](xref:microsoft.quantum.glossary#operation) -такт, которая принимает один или несколько [Кубитс](xref:microsoft.quantum.glossary#qubit) как созидателями для целевой операции.</span><span class="sxs-lookup"><span data-stu-id="57331-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="57331-127">Дополнительные сведения см. в разделе [контролируемые и смежные операции](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span><span class="sxs-lookup"><span data-stu-id="57331-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="57331-128">Нотация Дирак</span><span class="sxs-lookup"><span data-stu-id="57331-128">Dirac Notation</span></span>

<span data-ttu-id="57331-129">Символьная Краткая форма, упрощающая представление [состояний тактов](xref:microsoft.quantum.glossary#quantum-state), также называемая нотацией *неверное-Сисакет* .</span><span class="sxs-lookup"><span data-stu-id="57331-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="57331-130">*Неверное* часть представляет вектор строки, например $ \бра{а } = \бегин{ bmatrix } a {_1 } & a {_2 } \енд{ bmatrix } $, а часть *Сисакет* представляет вектор столбца, $ \кет{б } = \бегин{ bmatrix } B {_1 } \\ \\ b {_2 } \енд{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="57331-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="57331-131">Дополнительные сведения см. в разделе [Дирак Notation](xref:microsoft.quantum.concepts.dirac).</span><span class="sxs-lookup"><span data-stu-id="57331-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="57331-132">еиженвалуе</span><span class="sxs-lookup"><span data-stu-id="57331-132">Eigenvalue</span></span>

<span data-ttu-id="57331-133">Коэффициент, на который изменяется величина [еиженвектор](xref:microsoft.quantum.glossary#eigenvector) данного преобразования при преобразовании приложением преобразования.</span><span class="sxs-lookup"><span data-stu-id="57331-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="57331-134">При наличии квадратной матрицы $M $ и $v еиженвектор $ , затем $MV = ОПС $ , где $c $ является еиженвалуе и может быть комплексным числом любого аргумента.</span><span class="sxs-lookup"><span data-stu-id="57331-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="57331-135">Дополнительные сведения см. в разделе [Расширенные понятия матрицы](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="57331-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="57331-136">еиженвектор</span><span class="sxs-lookup"><span data-stu-id="57331-136">Eigenvector</span></span>

<span data-ttu-id="57331-137">Вектор, направление которого не изменилось заданным преобразованием и величина которого изменяется коэффициентом, соответствующим [еиженвалуеу](xref:microsoft.quantum.glossary#eigenvalue)вектора.</span><span class="sxs-lookup"><span data-stu-id="57331-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="57331-138">При наличии квадратной матрицы $M $ и $c еиженвалуе $ , затем $MV = ОПС $ , где $v $ является еиженвектор матрицы и может быть комплексным числом любого аргумента.</span><span class="sxs-lookup"><span data-stu-id="57331-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="57331-139">Дополнительные сведения см. в разделе [Расширенные понятия матрицы](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="57331-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="57331-140">Запутанность</span><span class="sxs-lookup"><span data-stu-id="57331-140">Entanglement</span></span>

<span data-ttu-id="57331-141">Частицы тактов, такие как [Кубитс](xref:microsoft.quantum.glossary#qubit), могут быть подключены или *запутанными* таким образом, что их нельзя описать независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="57331-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="57331-142">Результаты измерений сопоставлены, даже если они разделены бесконечно далеко.</span><span class="sxs-lookup"><span data-stu-id="57331-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="57331-143">Замкнутые важно для [измерения](xref:microsoft.quantum.glossary#measurement) [состояния](xref:microsoft.quantum.glossary#quantum-state) кубит.</span><span class="sxs-lookup"><span data-stu-id="57331-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="57331-144">Дополнительные сведения см. в разделе [Расширенные понятия матрицы](xref:microsoft.quantum.concepts.matrix-advanced).</span><span class="sxs-lookup"><span data-stu-id="57331-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="57331-145">Пара EPR</span><span class="sxs-lookup"><span data-stu-id="57331-145">EPR pair</span></span>

<span data-ttu-id="57331-146">Одно из четырех конкретных запутанными [состояний такта](xref:microsoft.quantum.glossary#quantum-state) двух [Кубитс](xref:microsoft.quantum.glossary#qubit).</span><span class="sxs-lookup"><span data-stu-id="57331-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="57331-147">Четыре состояния определяются как $ \кет { \ beta_ {ИЖ } } = (\Mathbb{1 } \Отимес X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $.</span><span class="sxs-lookup"><span data-stu-id="57331-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="57331-148">Пара EPR называется также [состоянием колокольчика](xref:microsoft.quantum.glossary#bell-state)</span><span class="sxs-lookup"><span data-stu-id="57331-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="57331-149">Результатом</span><span class="sxs-lookup"><span data-stu-id="57331-149">Evolution</span></span>

<span data-ttu-id="57331-150">Изменение [состояния такта](xref:microsoft.quantum.glossary#quantum-state) со временем.</span><span class="sxs-lookup"><span data-stu-id="57331-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="57331-151">Дополнительные сведения см. в разделе [экспонента матрицы](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span><span class="sxs-lookup"><span data-stu-id="57331-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="57331-152">Компонент</span><span class="sxs-lookup"><span data-stu-id="57331-152">Function</span></span>
<span data-ttu-id="57331-153">Тип подпрограммы на языке Q #, который является чисто классическим (не в такте).</span><span class="sxs-lookup"><span data-stu-id="57331-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="57331-154">Хотя функции используются в алгоритмах такта, они не могут действовать в [операциях](xref:microsoft.quantum.glossary#operation) [Кубитс](xref:microsoft.quantum.glossary#qubit) или Call.</span><span class="sxs-lookup"><span data-stu-id="57331-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="57331-155">Дополнительные сведения см. в разделе [операции и функции](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="57331-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="57331-156">Frame</span><span class="sxs-lookup"><span data-stu-id="57331-156">Gate</span></span>

<span data-ttu-id="57331-157">Устаревший термин для [операции](xref:microsoft.quantum.glossary#operation)с тактом, основанный на концепции классических логик шлюзов.</span><span class="sxs-lookup"><span data-stu-id="57331-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="57331-158">[Тактовая цепь](xref:microsoft.quantum.glossary#quantum-circuit-diagram) — это сеть шлюзов (или операций), основанная на аналогичной концепции классических логических цепей.</span><span class="sxs-lookup"><span data-stu-id="57331-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="57331-159">Глобальный этап</span><span class="sxs-lookup"><span data-stu-id="57331-159">Global phase</span></span>

<span data-ttu-id="57331-160">Если два [состояния](xref:microsoft.quantum.glossary#quantum-state) идентичны нескольким комплексным числам $e ^ {i \phi } $, говорят, что они отличаются от глобального этапа.</span><span class="sxs-lookup"><span data-stu-id="57331-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="57331-161">В отличие от локальных фаз, глобальные фазы не могут быть просмотрены через любые [меасурмент](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="57331-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="57331-162">Дополнительные сведения см. [в разделе кубит](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="57331-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="57331-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="57331-163">Hadamard</span></span>

<span data-ttu-id="57331-164">Операция Хадамард (также называемая Хадамард Gate или Transform) действует на одном [кубит](xref:microsoft.quantum.glossary#qubit) и помещает ее в четное [Расположение](xref:microsoft.quantum.glossary#superposition) $ \ket{0 } $ или $ \ket{1 } $, если кубит изначально находится в состоянии $ \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="57331-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="57331-165">В Q # эта операция применяется к предварительно определенной [`H`](xref:microsoft.quantum.intrinsic.h) операции.</span><span class="sxs-lookup"><span data-stu-id="57331-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="57331-166">Неизменяемые</span><span class="sxs-lookup"><span data-stu-id="57331-166">Immutable</span></span>

<span data-ttu-id="57331-167">Переменная, значение которой нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="57331-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="57331-168">Неизменяемая переменная в Q # создается с помощью `let` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="57331-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="57331-169">Чтобы объявить переменные, которые *могут* быть изменены, используйте ключевое слово [mutable](xref:microsoft.quantum.glossary#immutable) для объявления и `set` ключевого слова для изменения значения.</span><span class="sxs-lookup"><span data-stu-id="57331-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="57331-170">Измерения</span><span class="sxs-lookup"><span data-stu-id="57331-170">Measurement</span></span>

<span data-ttu-id="57331-171">Обработка [кубит](xref:microsoft.quantum.glossary#qubit) (или набора Кубитс), которая дает результат наблюдения, в результате получения классического бита.</span><span class="sxs-lookup"><span data-stu-id="57331-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="57331-172">Дополнительные сведения см. [в разделе кубит](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span><span class="sxs-lookup"><span data-stu-id="57331-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="57331-173">Изменяемый</span><span class="sxs-lookup"><span data-stu-id="57331-173">Mutable</span></span>

<span data-ttu-id="57331-174">Переменная, значение которой можно изменить после ее создания.</span><span class="sxs-lookup"><span data-stu-id="57331-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="57331-175">Изменяемая переменная в Q # объявляется с помощью `mutable` ключевого слова и изменяется с помощью `set` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="57331-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="57331-176">Переменные, созданные с помощью `let` ключевого слова, являются [неизменяемыми](xref:microsoft.quantum.glossary#immutable) , и их значения нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="57331-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="57331-177">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="57331-177">Namespace</span></span>

<span data-ttu-id="57331-178">Метка для коллекции связанных имен (т. е. [операций](xref:microsoft.quantum.glossary#operation), [функций](xref:microsoft.quantum.glossary#function)и [определяемых пользователем типов](xref:microsoft.quantum.glossary#user-defined-type)).</span><span class="sxs-lookup"><span data-stu-id="57331-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="57331-179">Например, пространство имен [Microsoft. тактов. Подготовка](xref:microsoft.quantum.preparation) помечает все символы, определенные в стандартной библиотеке и помогающие при подготовке начальных состояний.</span><span class="sxs-lookup"><span data-stu-id="57331-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="57331-180">Операция</span><span class="sxs-lookup"><span data-stu-id="57331-180">Operation</span></span>

<span data-ttu-id="57331-181">Базовая единица выполнения такта в Q #.</span><span class="sxs-lookup"><span data-stu-id="57331-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="57331-182">Он примерно эквивалентен функции в C, C++ или Python или статическом методе в C# или Java.</span><span class="sxs-lookup"><span data-stu-id="57331-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="57331-183">Дополнительные сведения см. в разделе [операции и функции](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="57331-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="57331-184">Приложение оператора</span><span class="sxs-lookup"><span data-stu-id="57331-184">Operator application</span></span>

<span data-ttu-id="57331-185">Выполнение операции над тактом.</span><span class="sxs-lookup"><span data-stu-id="57331-185">Performing a quantum operation.</span></span> <span data-ttu-id="57331-186">Обычно это применяет единую матрицу к текущему вектору состояния такта.</span><span class="sxs-lookup"><span data-stu-id="57331-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="57331-187">Oracle;</span><span class="sxs-lookup"><span data-stu-id="57331-187">Oracle</span></span>

<span data-ttu-id="57331-188">Подпрограммы, которая предоставляет зависящую от данных информацию в алгоритме такта во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="57331-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="57331-189">Как правило, целью является [предоставление части выходных](xref:microsoft.quantum.glossary#superposition) данных, соответствующих входным данным, находящимся в части.</span><span class="sxs-lookup"><span data-stu-id="57331-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="57331-190">Дополнительные сведения см. в разделе [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).</span><span class="sxs-lookup"><span data-stu-id="57331-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="57331-191">Частичное приложение</span><span class="sxs-lookup"><span data-stu-id="57331-191">Partial application</span></span>

<span data-ttu-id="57331-192">Вызов [функции](xref:microsoft.quantum.glossary#function) или [операции](xref:microsoft.quantum.glossary#operation) без всех необходимых входных данных.</span><span class="sxs-lookup"><span data-stu-id="57331-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="57331-193">Он возвращает новый [вызываемый](xref:microsoft.quantum.glossary#callable) объект, которому требуются только отсутствующие параметры (обозначенные символом подчеркивания), которые должны быть предоставлены в будущем приложении.</span><span class="sxs-lookup"><span data-stu-id="57331-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="57331-194">Например, при наличии функции `MyFunc(x : int, y : int) : int {return x + y;}` можно частично применить ее к новой функции `let NewFunc = MyFunc(_, 3)` .</span><span class="sxs-lookup"><span data-stu-id="57331-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="57331-195">Затем можно вызвать новую функцию позднее с отсутствующим параметром, `NewFunc(2)` который возвращает значение *5*.</span><span class="sxs-lookup"><span data-stu-id="57331-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="57331-196">Дополнительные сведения см. в разделе [частичное применение](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span><span class="sxs-lookup"><span data-stu-id="57331-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="57331-197">Операторы Паули</span><span class="sxs-lookup"><span data-stu-id="57331-197">Pauli operators</span></span>

<span data-ttu-id="57331-198">Набор из трех одноединых матриц 2 x 2, которые называются `X` `Y` и `Z` тактовыми операциями.</span><span class="sxs-lookup"><span data-stu-id="57331-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="57331-199">Матрица идентификаторов, $I $ , часто также включается в набор.</span><span class="sxs-lookup"><span data-stu-id="57331-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="57331-200">$I = \бегин{ bmatrix } 1 & 0 \\ \\ 0 & 1 \енд{ bmatrix } $, $X = \бегин{ bmatrix } 0 & 1 \\ \\ 1 & 0 \енд{ bmatrix } $, $Y = \бегин{ bmatrix } 0 &-i \\ \\ & 0 \енд{ bmatrix } $, $Z = \бегин{ bmatrix } 1 & 0 \\ \\ 0 &-1 \енд{ bmatrix } $.</span><span class="sxs-lookup"><span data-stu-id="57331-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="57331-201">Дополнительные сведения см. в статье [Single-кубит Operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span><span class="sxs-lookup"><span data-stu-id="57331-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="57331-202">Схема тактовой цепи</span><span class="sxs-lookup"><span data-stu-id="57331-202">Quantum circuit diagram</span></span>

<span data-ttu-id="57331-203">Метод для графического представления последовательности [операций](xref:microsoft.quantum.glossary#operation) (или [шлюзов](xref:microsoft.quantum.glossary#gate)) для простых тактовых программ, например</span><span class="sxs-lookup"><span data-stu-id="57331-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![Образец схемы цепи](~/media/qpe.png)<span data-ttu-id="57331-205">.</span><span class="sxs-lookup"><span data-stu-id="57331-205">.</span></span> 

<span data-ttu-id="57331-206">Дополнительные сведения см. в разделе [тактовые цепи](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="57331-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="57331-207">Библиотеки тактов</span><span class="sxs-lookup"><span data-stu-id="57331-207">Quantum libraries</span></span>

<span data-ttu-id="57331-208">Коллекции [операций](xref:microsoft.quantum.glossary#operation), [функций](xref:microsoft.quantum.glossary#function) и [определяемых пользователем типов](xref:microsoft.quantum.glossary#user-defined-type) для создания программ Q #.</span><span class="sxs-lookup"><span data-stu-id="57331-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="57331-209">[Стандартная библиотека](xref:microsoft.quantum.libraries.standard.intro) устанавливается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57331-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="57331-210">Доступны другие библиотеки: [Библиотека химия](xref:microsoft.quantum.chemistry.concepts.intro), [Библиотека числовых чисел](xref:microsoft.quantum.numerics.intro) и [Библиотека машинного обучения](xref:microsoft.quantum.machine-learning.concepts.intro).</span><span class="sxs-lookup"><span data-stu-id="57331-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="57331-211">Состояние такта</span><span class="sxs-lookup"><span data-stu-id="57331-211">Quantum state</span></span>

<span data-ttu-id="57331-212">Точное состояние изолированной тактовой системы, из которой можно извлечь вероятности [измерения](xref:microsoft.quantum.glossary#measurement) .</span><span class="sxs-lookup"><span data-stu-id="57331-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="57331-213">В тактовых вычислениях имитатор тактовой частоты использует эти сведения для имитации реакции Кубитс на операции.</span><span class="sxs-lookup"><span data-stu-id="57331-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="57331-214">Дополнительные сведения см. [в разделе кубит](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="57331-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="57331-215">кубит</span><span class="sxs-lookup"><span data-stu-id="57331-215">Qubit</span></span>

<span data-ttu-id="57331-216">Базовая единица данных о такте, аналогичная *побиту* в классические вычисления.</span><span class="sxs-lookup"><span data-stu-id="57331-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="57331-217">Дополнительные сведения см. [в разделе кубит](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="57331-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="57331-218">Повторение до — успешное завершение</span><span class="sxs-lookup"><span data-stu-id="57331-218">Repeat-until-success</span></span>

<span data-ttu-id="57331-219">Алгоритм такта, probabilistically с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="57331-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="57331-220">При сбое подпрограммы повторит попытку до тех пор, пока не завершится успешно (или достигнут предел).</span><span class="sxs-lookup"><span data-stu-id="57331-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="57331-221">Дополнительные сведения см. в разделе [повторение до успешного выполнения (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) .</span><span class="sxs-lookup"><span data-stu-id="57331-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="57331-222">Стандартные библиотеки</span><span class="sxs-lookup"><span data-stu-id="57331-222">Standard libraries</span></span>

<span data-ttu-id="57331-223">[Операции](xref:microsoft.quantum.glossary#operation), [функции](xref:microsoft.quantum.glossary#function) и [определяемые пользователем типы](xref:microsoft.quantum.glossary#user-defined-type) , которые устанавливаются вместе с компилятором Q # во время установки.</span><span class="sxs-lookup"><span data-stu-id="57331-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="57331-224">Реализация стандартной библиотеки не зависит от целевых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="57331-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="57331-225">Дополнительные сведения см. в разделе [Стандартные библиотеки](xref:microsoft.quantum.libraries.standard.intro).</span><span class="sxs-lookup"><span data-stu-id="57331-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="57331-226">Суперпозиции</span><span class="sxs-lookup"><span data-stu-id="57331-226">Superposition</span></span>

<span data-ttu-id="57331-227">Концепция в тактовых вычислениях [кубит](xref:microsoft.quantum.glossary#qubit) представляет собой линейное сочетание двух Штатов, $ \ket{0 } $ и $ \ket{1 } $, пока оно не будет [измеряться](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="57331-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="57331-228">Дополнительные сведения см. в разделе [Основные сведения о тактовых вычислениях](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="57331-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="57331-229">Целевой компьютер</span><span class="sxs-lookup"><span data-stu-id="57331-229">Target machine</span></span>

<span data-ttu-id="57331-230">Цель компиляции, которая понижает абстрактную тактовую программу для оборудования или моделирования.</span><span class="sxs-lookup"><span data-stu-id="57331-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="57331-231">Обычно это включает повторную запись для многих целей, включая замену шлюза, кодирование для коррекции ошибок, геометрическую структуру и другие.</span><span class="sxs-lookup"><span data-stu-id="57331-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="57331-232">Дополнительные сведения см. в разделе [тактовые имитаторы и ведущие приложения](xref:microsoft.quantum.machines).</span><span class="sxs-lookup"><span data-stu-id="57331-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="57331-233">Телепортация</span><span class="sxs-lookup"><span data-stu-id="57331-233">Teleportation</span></span>

<span data-ttu-id="57331-234">Метод повторного создания данных или [состояния такта](xref:microsoft.quantum.glossary#quantum-state)одного [кубит](xref:microsoft.quantum.glossary#qubit) из одного места в другое без физического перемещения кубит с использованием [замкнутые](xref:microsoft.quantum.glossary#entanglement) и [измерения](xref:microsoft.quantum.glossary#measurement).</span><span class="sxs-lookup"><span data-stu-id="57331-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="57331-235">Дополнительные сведения см. в разделе [тактовые цепи](xref:microsoft.quantum.concepts.circuits) и соответствующие Ката в [такте Катас](xref:microsoft.quantum.overview.katas).</span><span class="sxs-lookup"><span data-stu-id="57331-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="57331-236">Кортеж</span><span class="sxs-lookup"><span data-stu-id="57331-236">Tuple</span></span>

<span data-ttu-id="57331-237">Коллекция значений с разделителями-запятыми, которая выступает в качестве одного значения.</span><span class="sxs-lookup"><span data-stu-id="57331-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="57331-238">*Тип* кортежа определяется типами содержащихся в нем значений.</span><span class="sxs-lookup"><span data-stu-id="57331-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="57331-239">В Q # кортежи являются [неизменяемыми](xref:microsoft.quantum.glossary#immutable) и могут быть вложенными, содержать массивы или использоваться в массиве.</span><span class="sxs-lookup"><span data-stu-id="57331-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="57331-240">Дополнительные сведения см. в разделе [типы кортежей](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="57331-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="57331-241">Оператор с единым</span><span class="sxs-lookup"><span data-stu-id="57331-241">Unitary operator</span></span>

<span data-ttu-id="57331-242">Оператор, инверсия которого равен его [соседнему](xref:microsoft.quantum.glossary#adjoint)объекту, т. е. $uu ^ {\дагжер } = \ид $ .</span><span class="sxs-lookup"><span data-stu-id="57331-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="57331-243">Определяемый пользователем тип</span><span class="sxs-lookup"><span data-stu-id="57331-243">User-defined type</span></span>

<span data-ttu-id="57331-244">Коллекция встроенных или ранее определенных типов, на которые можно ссылаться как на один блок.</span><span class="sxs-lookup"><span data-stu-id="57331-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="57331-245">Дополнительные сведения см. в разделе [определяемые пользователем типы](xref:microsoft.quantum.guide.types#user-defined-types).</span><span class="sxs-lookup"><span data-stu-id="57331-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>