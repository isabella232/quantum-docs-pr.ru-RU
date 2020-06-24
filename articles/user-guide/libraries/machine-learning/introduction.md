---
title: Библиотека квантового машинного обучения
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276173"
---
# <a name="introduction-to-quantum-machine-learning"></a><span data-ttu-id="59d6f-102">Введение в тактовую Машинное обучение</span><span class="sxs-lookup"><span data-stu-id="59d6f-102">Introduction to Quantum Machine Learning</span></span>

## <a name="framework-and-goals"></a><span data-ttu-id="59d6f-103">Платформа и цели</span><span class="sxs-lookup"><span data-stu-id="59d6f-103">Framework and goals</span></span>

<span data-ttu-id="59d6f-104">Кодирование и обработка данных в такте — это мощная альтернатива классическим классам-классификаторам такта машинного обучения, в частности, кодирования данных в тактовых регистрах, которые кратко относятся к числу функций, систематически применяют тактовую замкнутые в качестве вычислительного ресурса и используют измерение тактов для вывода класса.</span><span class="sxs-lookup"><span data-stu-id="59d6f-104">Quantum encoding and processing of information is a powerful alternative to classical machine learning Quantum classifiers, in particular, encode data in quantum registers that are concise relative to the number of features, systematically employ quantum entanglement as computational resource and employ quantum measurement for class inference.</span></span>
<span data-ttu-id="59d6f-105">Классификатор такта, ориентированный на канал, — это относительно простое решение, объединяющее кодировку данных с быстрой ентанглинг/распутывание запутанной сети тактовой цепью, за которым следует измерение для определения меток классов для выборок данных.</span><span class="sxs-lookup"><span data-stu-id="59d6f-105">Circuit centric quantum classifier is a relatively simple quantum solution that combines data encoding with a rapidly entangling/disentangling quantum circuit followed by measurement to infer class labels of data samples.</span></span>
<span data-ttu-id="59d6f-106">Цель состоит в том, чтобы обеспечить классический механизм распознавания и хранение цепей предметной области, а также гибридный такт или классический обучающий курс параметров канала даже для очень больших функциональных пространств.</span><span class="sxs-lookup"><span data-stu-id="59d6f-106">The goal is to ensure classical characterization and storage of subject circuits, as well as hybrid quantum/classical training of the circuit parameters even for extremely large feature spaces.</span></span>

## <a name="classifier-architecture"></a><span data-ttu-id="59d6f-107">Архитектура классификатора</span><span class="sxs-lookup"><span data-stu-id="59d6f-107">Classifier architecture</span></span>

<span data-ttu-id="59d6f-108">Классификация — это задача защищенного машинного обучения, где целью является определение меток классов $ \{ y_1, y_2, \лдотс, y_d \} $ некоторых примеров данных.</span><span class="sxs-lookup"><span data-stu-id="59d6f-108">Classification is a supervised machine learning task, where the goal is to infer class labels $\{y_1,y_2,\ldots,y_d\}$ of certain data samples.</span></span> <span data-ttu-id="59d6f-109">"Обучающий набор данных" — это коллекция примеров $ \Маскал{д} = \{ (x, y)} $ с известными предварительно назначенными метками.</span><span class="sxs-lookup"><span data-stu-id="59d6f-109">The "training data set" is a collection of samples $\mathcal{D}=\{(x,y)}$ with known pre-assigned labels.</span></span> <span data-ttu-id="59d6f-110">Здесь $x $ является образцом данных и $y $ — это известная метка с названием «обучающая метка».</span><span class="sxs-lookup"><span data-stu-id="59d6f-110">Here $x$ is a data sample and $y$ is its known label called "training label".</span></span>
<span data-ttu-id="59d6f-111">По аналогии с традиционными методами, классификация тактов состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="59d6f-111">Somewhat similar to traditional methods, quantum classification consists of three steps:</span></span>
- <span data-ttu-id="59d6f-112">кодирование данных</span><span class="sxs-lookup"><span data-stu-id="59d6f-112">data encoding</span></span>
- <span data-ttu-id="59d6f-113">подготовка состояния классификатора</span><span class="sxs-lookup"><span data-stu-id="59d6f-113">preparation of a classifier state</span></span>
- <span data-ttu-id="59d6f-114">измерения из-за природы вероятностная измерения, эти три шага должны повторяться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="59d6f-114">measurement Due to the probabilistic nature of the measurement, these three steps must be repeated multiple times.</span></span> <span data-ttu-id="59d6f-115">Измерение можно просмотреть в виде тактового эквивалента нелинейной активации.</span><span class="sxs-lookup"><span data-stu-id="59d6f-115">The measurement may be viewed as a quantum equivalent of non-linear activation.</span></span>
<span data-ttu-id="59d6f-116">Как кодирование, так и вычисления состояния классификатора выполняются с помощью *цепей тактов*.</span><span class="sxs-lookup"><span data-stu-id="59d6f-116">Both the encoding and the computing of the classifier state are done by means of *quantum circuits*.</span></span> <span data-ttu-id="59d6f-117">Несмотря на то, что канал кодирования обычно управляется данными и без параметров, цепь-классификатор содержит достаточный набор необходимых для изучения параметров.</span><span class="sxs-lookup"><span data-stu-id="59d6f-117">While the encoding circuit is usually data-driven and parameter-free, the classifier circuit contains a sufficient set of learnable parameters.</span></span> 

<span data-ttu-id="59d6f-118">В предложенном решении цепь-классификатор состоит из однокубитных поворотов и кубитных поворотов.</span><span class="sxs-lookup"><span data-stu-id="59d6f-118">In the proposed solution the classifier circuit is composed of single-qubit rotations and two-qubit controlled rotations.</span></span> <span data-ttu-id="59d6f-119">Для изучения этих параметров используются углы поворота.</span><span class="sxs-lookup"><span data-stu-id="59d6f-119">The learnable parameters here are the rotation angles.</span></span> <span data-ttu-id="59d6f-120">Шлюзы ротации и управления, управляемые, являются *универсальными* для вычислений тактов. Это означает, что любую одновесовую матрицу можно разложить на достаточно длинный канал, состоящий из таких шлюзов.</span><span class="sxs-lookup"><span data-stu-id="59d6f-120">The rotation and controlled rotation gates are known to be *universal* for quantum computation, which means that any unitary weight matrix can be decomposed into a long enough circuit consisting of such gates.</span></span>

![Многоуровневый перцептрона и классификатор, ориентированный на канал](~/media/DLvsQCC.png)

<span data-ttu-id="59d6f-122">Мы можем сравнить эту модель с многоуровневой перцептронаой, чтобы получить более полное представление о базовой структуре.</span><span class="sxs-lookup"><span data-stu-id="59d6f-122">We can compare this model to a multilayer perceptron to get a better understanding of the basic structure.</span></span> <span data-ttu-id="59d6f-123">В перцептрона прогнозируемый $p (y | x, \сета) $ является параметризованным по набору весов $ \сета $, который определяет линейные функции, соединяющие функции нелинейной активации (нейроны).</span><span class="sxs-lookup"><span data-stu-id="59d6f-123">In the perceptron the predictor $p(y|x, \theta)$ is parametrized by the set of weights $\theta$ that determine the linear functions connecting the non-linear activation functions (neurons).</span></span> <span data-ttu-id="59d6f-124">Эти параметры можно обучить для создания модели.</span><span class="sxs-lookup"><span data-stu-id="59d6f-124">These parameters can be trained to create the model.</span></span> <span data-ttu-id="59d6f-125">На выходном слое можно получить вероятность выборки, принадлежащей классу, с помощью нелинейных функций активации, таких как softmax.</span><span class="sxs-lookup"><span data-stu-id="59d6f-125">At the output layer we can get the probability of a sample belonging to a class by using non-linear activation functions like softmax.</span></span> <span data-ttu-id="59d6f-126">В классификаторе, ориентированном на канал, прогнозируемый параметризованным с помощью углов вращения, расположенных на поворотах одного кубит и двух кубит, управляемых в цепи моделей.</span><span class="sxs-lookup"><span data-stu-id="59d6f-126">In the circuit centric classifier the predictor is parametrized by the rotation angles of the single-qubit and two-qubit controlled rotations of the model circuit.</span></span> <span data-ttu-id="59d6f-127">Аналогичным образом эти параметры можно обучить с помощью гибридного такта или классической версии алгоритма спуска градиента.</span><span class="sxs-lookup"><span data-stu-id="59d6f-127">In a similar fashion, those parameters can be trained by an hybrid quantum/classical version of the gradient descent algorithm.</span></span> <span data-ttu-id="59d6f-128">Чтобы вычислить выходные данные вместо использования нелинейных функций активации, вероятность класса достигается путем считывания повторяющихся измерений по определенному кубит после управляемого вращения.</span><span class="sxs-lookup"><span data-stu-id="59d6f-128">To calculate the output, instead of using non-linear activation functions, the probability of the class is obtained by reading repeated measurements over a specific qubit after the controlled rotations.</span></span> <span data-ttu-id="59d6f-129">Для кодирования классических данных в состоянии такта мы используем управляемый канал кодирования для подготовки состояния.</span><span class="sxs-lookup"><span data-stu-id="59d6f-129">To encode the classical data in a quantum state we use a controllable encoding circuit for state preparation.</span></span>

<span data-ttu-id="59d6f-130">В нашей архитектуре рассматриваются относительно неполные каналы, которые, следовательно, должны быть *быстро ентанглинг* для захвата всех корреляций между функциями данных во всех диапазонах.</span><span class="sxs-lookup"><span data-stu-id="59d6f-130">Our architecture explores relatively shallow circuits, which therefore must be *rapidly entangling* in order to capture all the correlations between the data features at all ranges.</span></span> <span data-ttu-id="59d6f-131">Пример наиболее полезного компонента ентанглинг цепи показан на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="59d6f-131">An example of the most useful rapidly entangling circuit component is shown on figure below.</span></span> <span data-ttu-id="59d6f-132">Несмотря на то, что канал с этой геометрической схемой состоит только из $3 n + 1 $ Gates, формируемая им матрица единого веса обеспечивает значительный обмен данными между компонентами $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="59d6f-132">Even though a circuit with this geometry consists of only $3 n+1$ gates, the unitary weight matrix that it computes ensures significant cross-talk between $2^n$ features.</span></span>

![Быстро ентанглинг тактовую цепь на 5 Кубитс (с двумя циклическими слоями).](~/media/5-qubit-qccc.png)

<span data-ttu-id="59d6f-134">Цепь в приведенном выше примере состоит из 6 однокубитных шлюзов $ (G_1, \лдотс, G_5; G_ {16} ) $ и 10 2-Кубитс Gates $ (G_6, \лдотс, G_ {15} ) $.</span><span class="sxs-lookup"><span data-stu-id="59d6f-134">The circuit in the above example consists of 6 single-qubit gates $(G_1,\ldots,G_5; G_{16})$ and 10 two-qubits gates $(G_6,\ldots,G_{15})$.</span></span> <span data-ttu-id="59d6f-135">Предполагая, что каждый из шлюзов определен с одним из этих параметров, у нас есть 16 подученных параметров, а измерение 5-кубит Гильберта пространство — 32.</span><span class="sxs-lookup"><span data-stu-id="59d6f-135">Assuming that each of the gates is defined with one learnable parameter we have 16 learnable parameters, while the dimension of the 5-qubit Hilbert space is 32.</span></span> <span data-ttu-id="59d6f-136">Такая геометрия канала может быть легко обобщена любому $n $-кубит регистру, когда $n $ является нечетным, что дает цепи с $3 n + 1 $ параметрами для $2 ^ n $-многомерного пространства.</span><span class="sxs-lookup"><span data-stu-id="59d6f-136">Such circuit geometry can be easily generalized to any $n$-qubit register, when $n$ is odd, yielding circuits with $3 n+1$ parameters for $2^n$-dimensional feature space.</span></span>

## <a name="classifier-training-as-a-supervised-learning-task"></a><span data-ttu-id="59d6f-137">Обучение классификатора как контролируемая задача обучения</span><span class="sxs-lookup"><span data-stu-id="59d6f-137">Classifier training as a supervised learning task</span></span>

<span data-ttu-id="59d6f-138">Обучение модели-классификатора включает в себя поиск оптимальных значений его операционных параметров, что позволяет максимально увеличить среднюю вероятность получения правильных меток обучения по обучающим образцам.</span><span class="sxs-lookup"><span data-stu-id="59d6f-138">Training of a classifier model involves finding optimal values of its operational parameters, such that they maximize the average likelihood of inferring the correct training labels across the training samples.</span></span>
<span data-ttu-id="59d6f-139">Здесь мы будем беспокоиться только о двух уровнях классификации, т. е. в случае $d = $2 и только два класса с метками $y _1, y_2 $.</span><span class="sxs-lookup"><span data-stu-id="59d6f-139">Here, we concern ourselves with two level classification only, i.e. the case of $d=2$ and only two classes with the labels $y_1,y_2$.</span></span>

> [!NOTE]
> <span data-ttu-id="59d6f-140">Способ обобщения наших методов с произвольным числом классов заключается в замене Кубитс на кудитс, т. е. единицами такта с $d $ базисными состояниями и двусторонним измерением с $d $-Way.</span><span class="sxs-lookup"><span data-stu-id="59d6f-140">A principled way of generalizing our methods to arbitrary number of classes is to replace qubits with qudits, i.e. quantum units with $d$ basis states, and the two-way measurement with $d$-way measurement.</span></span>

### <a name="likelihood-as-the-training-goal"></a><span data-ttu-id="59d6f-141">Правдоподобие цели обучения</span><span class="sxs-lookup"><span data-stu-id="59d6f-141">Likelihood as the training goal</span></span>

<span data-ttu-id="59d6f-142">Учитывая проученную цепь тактовой $U (\сета) $, где $ \сета $ является вектором параметров и обозначая окончательную меру на $M $, средняя вероятность правильного вывода метки — $ $ \бегин{алигн} \Маскал{л} (\сета) = \фрак {1} {| \маскал{д} |} \лефт (\ sum_ {(x, y_1) \Ин\маскал{д}} P (M = y_1 | U (\сета) x) + \ sum_ {(x, y_2) \Ин\маскал{д}} P (M = y_2 | U (\сета) x) \ригхт) \енд{алигн} $ $ WHERE $P (M = y | z) $ является вероятностью измерения $y $ в состоянии такта $z $.</span><span class="sxs-lookup"><span data-stu-id="59d6f-142">Given a learnable quantum circuit $U(\theta)$, where $\theta$ is a vector of parameters, and denoting the final measurement by $M$, the average likelihood of the correct label inference is $$ \begin{align} \mathcal{L}(\theta)=\frac{1}{|\mathcal{D}|} \left( \sum_{(x,y_1)\in\mathcal{D}} P(M=y_1|U(\theta) x) + \sum_{(x,y_2)\in\mathcal{D}} P(M=y_2|U(\theta) x)\right) \end{align} $$ where $P(M=y|z)$ is the probability of measuring $y$ in quantum state $z$.</span></span>
<span data-ttu-id="59d6f-143">Здесь достаточно понять, что функция правдоподобия $ \Маскал{л} (\сета) $ является гладким в $ \сета $ и ее производная в любом $ \ theta_j $ может быть вычислена по сути тем же протоколом такта, который используется для вычисления самой функции правдоподобия.</span><span class="sxs-lookup"><span data-stu-id="59d6f-143">Here, it suffices to understand that the likelihood function $\mathcal{L}(\theta)$ is smooth in $\theta$ and its derivative in any $\theta_j$ can be computed by essentially the same quantum protocol as used for computing the likelihood function itself.</span></span> <span data-ttu-id="59d6f-144">Это позволяет оптимизировать спуск шкалы $ \Маскал{л} (\сета) $ по градиенту.</span><span class="sxs-lookup"><span data-stu-id="59d6f-144">This allows for optimizing the $\mathcal{L}(\theta)$ by gradient descent.</span></span>

### <a name="classifier-bias-and-training-score"></a><span data-ttu-id="59d6f-145">Смещение классификатора и оценка курса обучения</span><span class="sxs-lookup"><span data-stu-id="59d6f-145">Classifier bias and training score</span></span>

<span data-ttu-id="59d6f-146">Учитывая некоторые промежуточные (или окончательные) значения параметров в $ \сета $, нам нужно определить одно вещественное значение $b $ знать как *классификатор смещения* для выполнения вывода.</span><span class="sxs-lookup"><span data-stu-id="59d6f-146">Given some intermediate (or final) values of the parameters in $\theta$, we need to identify a single real value $b$ know as *classifier bias* to do the inference.</span></span> <span data-ttu-id="59d6f-147">Правило вывода метки работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59d6f-147">The label inference rule works as follows:</span></span> 
- <span data-ttu-id="59d6f-148">Пример $x $ назначается меткой $y _2 $ if и только в том случае, если $P (M = y_2 | U (\сета) x) + b > $0,5 (RULE1) (в противном случае назначается метка $y _1 $)</span><span class="sxs-lookup"><span data-stu-id="59d6f-148">A sample $x$ is assigned label $y_2$ if and only if $P(M=y_2|U(\theta) x) + b > 0.5$  (RULE1) (otherwise it is assigned label $y_1$)</span></span>

<span data-ttu-id="59d6f-149">Явно $b $ должен быть в пределах $ (-0,5, + 0,5) $, чтобы быть осмысленным.</span><span class="sxs-lookup"><span data-stu-id="59d6f-149">Clearly $b$ must be in the interval $(-0.5,+0.5)$ to be meaningful.</span></span>

<span data-ttu-id="59d6f-150">Обучающий вариант $ (x, y) \ин \Маскал{д} $ считается неправильной *классификацией* с учетом смещения $b $ если метка, выводимая для $x $ в соответствии с RULE1, на самом деле отличается от $y $.</span><span class="sxs-lookup"><span data-stu-id="59d6f-150">A training case $(x,y) \in \mathcal{D}$ is considered a *misclassification* given the bias $b$ if the label inferred for $x$ as per RULE1 is actually different from $y$.</span></span> <span data-ttu-id="59d6f-151">Общее число неправильной классификации — это *показатель обучения* классификатора, заданный в $b $.</span><span class="sxs-lookup"><span data-stu-id="59d6f-151">The overall number of misclassifications is the *training score* of the classifier given the bias $b$.</span></span> <span data-ttu-id="59d6f-152">*Оптимальный* уровень смещения классификатора $b $ свертывает оценку обучения.</span><span class="sxs-lookup"><span data-stu-id="59d6f-152">The *optimal* classifier bias $b$ minimizes the training score.</span></span> <span data-ttu-id="59d6f-153">Это легко увидеть, учитывая предварительно вычисленные оценки вероятности $ \{ P (M = y_2 | U (\сета) x) | (x, \*) \Ин\маскал{д} \} $. оптимальное смещение классификатора можно найти по двоичному поиску в интервале $ (-0,5, + 0,5) $, установив максимум $ \ Log_2 (| \маскал{д} |) $ шаги.</span><span class="sxs-lookup"><span data-stu-id="59d6f-153">It is easy to see that, given the precomputed probability estimates $\{ P(M=y_2|U(\theta) x) | (x,\*)\in\mathcal{D} \}$, the optimal classifier bias can be found by binary search in interval $(-0.5,+0.5)$ by making at most $\log_2(|\mathcal{D}|)$ steps.</span></span>

### <a name="reference"></a><span data-ttu-id="59d6f-154">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="59d6f-154">Reference</span></span>

<span data-ttu-id="59d6f-155">Эта информация должна быть достаточной для начала воспроизведения кода.</span><span class="sxs-lookup"><span data-stu-id="59d6f-155">This information should be enough to start playing with the code.</span></span> <span data-ttu-id="59d6f-156">Однако если вы хотите узнать больше об этой модели, прочитайте первоначальное предложение: [ *"генераторы тактов на основе цепи", Мария Счулд, Алекс Бочаров, Криста Своре и (Nathan виебе*](https://arxiv.org/abs/1804.00633)</span><span class="sxs-lookup"><span data-stu-id="59d6f-156">However, if you want to learn more about this model, please read the original proposal: [*'Circuit-centric quantum classifiers', Maria Schuld, Alex Bocharov, Krysta Svore and Nathan Wiebe*](https://arxiv.org/abs/1804.00633)</span></span>