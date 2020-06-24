---
title: Иордания — представление Вигнер
description: Сведения о Вигнер представлении, которое сопоставляет операторы Хамилтониан с едиными матрицами, которые более легко реализовать на тактовой системе.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 17cb473c6d33e3356d5da886f47985c3828d4d1f
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275921"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="c07e3-103">Иордания — представление Вигнер</span><span class="sxs-lookup"><span data-stu-id="c07e3-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="c07e3-104">Несмотря на то, что второй квантования Хамилтонианс удобно представить в виде $a ^ \дагжер $ (создание) и $a $ (аннихилатион), эти операции не являются фундаментальными операциями на тактовых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="c07e3-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="c07e3-105">В результате, если бы мы хотели реализовать их на тактовый компьютер, необходимо сопоставлять операторы с едиными матрицами, которые могут быть реализованы на тактовый компьютер.</span><span class="sxs-lookup"><span data-stu-id="c07e3-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="c07e3-106">Представление "Иордания — Вигнер" дает одну такую карту.</span><span class="sxs-lookup"><span data-stu-id="c07e3-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="c07e3-107">Тем не менее, другие, например Брави – Китаев, также существуют и имеют собственные относительные преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="c07e3-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="c07e3-108">Основным преимуществом представления «Иордания-Вигнер» является его простота.</span><span class="sxs-lookup"><span data-stu-id="c07e3-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="c07e3-109">Представление "Иордания-Вигнер" прямо вперед к производному.</span><span class="sxs-lookup"><span data-stu-id="c07e3-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="c07e3-110">Помните, что состояние $ \кет {0} _j $ подразумевает, что Spin орбитал $j $ является пустым, а $ \кет {1} _j $ означает, что он занят.</span><span class="sxs-lookup"><span data-stu-id="c07e3-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="c07e3-111">Это означает, что Кубитс может естественным образом сохранить род данного Орбитал.</span><span class="sxs-lookup"><span data-stu-id="c07e3-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="c07e3-112">Затем это $a ^ \ dagger_j \кет {0} _j = \кет {1} _j $ и $a ^ \ dagger_j \кет {1} _j = $0.</span><span class="sxs-lookup"><span data-stu-id="c07e3-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="c07e3-113">Легко проверить, что \бегин{алигн} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \енд{бматрикс} = \фрак{X_j-iY_j} {2} , \нонумбер \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \енд{бматрикс} = \фрак{X_j + iY_j} {2} , \енд{алигн}, где $X _j $ и $Y _j $, являются паули-$X $ and-$Y $, действующими в Qubit $j $.</span><span class="sxs-lookup"><span data-stu-id="c07e3-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>

>[!NOTE]
> <span data-ttu-id="c07e3-114">В Q # состояние $ \кет {0} $ представляет + 1 еиженстате оператора $Z $.</span><span class="sxs-lookup"><span data-stu-id="c07e3-114">In Q# the $\ket{0}$ state represents the +1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="c07e3-115">В некоторых частях физика $ \кет {0} $ представляет состояние заземления в низком энергопотреблении, а значит-1 еиженстате оператора $Z $.</span><span class="sxs-lookup"><span data-stu-id="c07e3-115">In some areas of physics $\ket{0}$ represents the low-energy ground state and thus the -1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="c07e3-116">Поэтому некоторые формулы могут отличаться от популярных.</span><span class="sxs-lookup"><span data-stu-id="c07e3-116">Therefore some formulas might differ from popular literature.</span></span>

<span data-ttu-id="c07e3-117">В библиотеке химия мы используем $ \кет {0} $ для представления незанятого счетчика-Орбитал.</span><span class="sxs-lookup"><span data-stu-id="c07e3-117">In the chemistry library we use $\ket{0}$ to represent an unoccupied spin-orbital.</span></span>
<span data-ttu-id="c07e3-118">Это показывает, что для одного Орбитал можно легко представить операторы создания и аннихилатион в терминах отдельных матриц, которые понимают компьютеры-такты.</span><span class="sxs-lookup"><span data-stu-id="c07e3-118">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="c07e3-119">Обратите внимание, что хотя $X $ и $Y $ являются едиными $a ^ \дагжер $ и $a $ не являются.</span><span class="sxs-lookup"><span data-stu-id="c07e3-119">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="c07e3-120">Далее мы увидим, что это не является проблемой для моделирования.</span><span class="sxs-lookup"><span data-stu-id="c07e3-120">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="c07e3-121">Одна из проблем заключается в том, что хотя описанная выше конструкция работает для одного Орбитал, она завершается ошибкой для систем с двумя или более оборотами.</span><span class="sxs-lookup"><span data-stu-id="c07e3-121">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="c07e3-122">Поскольку Фермионс являются антисимметик, мы понимаем, что $a ^ \ dagger_j a ^ \ dagger_k =-a ^ \ dagger_k ^ \ dagger_j $ для любого $j $ и $k $.</span><span class="sxs-lookup"><span data-stu-id="c07e3-122">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="c07e3-123">Однако $ $ \лефт (\фрак{X_j-iY_j} {2} \ригхт) \лефт (\фрак{X_k-iY_k} {2} \ригхт) = \лефт (\фрак{X_k-iY_k} {2} \ригхт) \лефт (\фрак{X_j-iY_j} {2} \ригхт).</span><span class="sxs-lookup"><span data-stu-id="c07e3-123">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="c07e3-124">$ $ Другими словами, при необходимости два оператора создания не выполняют защиту.</span><span class="sxs-lookup"><span data-stu-id="c07e3-124">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="c07e3-125">Это может быть исправлено, если это неизящный способ.</span><span class="sxs-lookup"><span data-stu-id="c07e3-125">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="c07e3-126">Исправление заключается в том, что Паули операторы естественным образом не работает.</span><span class="sxs-lookup"><span data-stu-id="c07e3-126">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="c07e3-127">В частности, $XZ =-ЗКС $ и $YZ =-зи $.</span><span class="sxs-lookup"><span data-stu-id="c07e3-127">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="c07e3-128">Таким же путем интерсперсинг $Z $ Operators в конструкцию оператора, мы можем эмулировать правильное сглаживание коммутатион.</span><span class="sxs-lookup"><span data-stu-id="c07e3-128">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="c07e3-129">Полная конструкция выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c07e3-129">The full construction is as follows:</span></span> 

<span data-ttu-id="c07e3-130">\бегин{алигн} a ^ \ dagger_1 &= \лефт (\Фрак{КС-ий} {2} \ригхт) \отимес 1 \отимес 1 \отимес 1 \отимес \кдотс \отимес 1, \\ \\ a ^ \ dagger_2 &= Z\otimes\left (\frac{X-iY} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ а ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iY} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iY} \right {2} ).</span><span class="sxs-lookup"><span data-stu-id="c07e3-130">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="c07e3-131">\лабел{ЕК: JW} \енд{алигн}</span><span class="sxs-lookup"><span data-stu-id="c07e3-131">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="c07e3-132">Также удобно выразить числовые операторы $n _j $ в терминах операторов Паули.</span><span class="sxs-lookup"><span data-stu-id="c07e3-132">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="c07e3-133">К счастью, строки $Z $ Operators (известные как «Иордания-Вигнер строки») отменяются после того, как это подставится.</span><span class="sxs-lookup"><span data-stu-id="c07e3-133">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="c07e3-134">После истечения этого (и повторного вызова этого $X _jY_j = iZ_j $) у нас есть \бегин{екуатион} n_j = a ^ \ dagger_j a_j = \фрак{(1-Z_j)} {2} .</span><span class="sxs-lookup"><span data-stu-id="c07e3-134">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="c07e3-135">\енд{екуатион}</span><span class="sxs-lookup"><span data-stu-id="c07e3-135">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="c07e3-136">Создание Хамилтонианс в формате "Иордания-Вигнер"</span><span class="sxs-lookup"><span data-stu-id="c07e3-136">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="c07e3-137">После вызова представления "Иордания-Вигнер", переводимого Хамилтониан на сумму операторов Паули, будет прямо вперед.</span><span class="sxs-lookup"><span data-stu-id="c07e3-137">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="c07e3-138">Необходимо просто заменить каждый из операторов $a ^ \дагжер $ и $a $ в Фермионик Хамилтониан строками Паули-Operators, указанных выше.</span><span class="sxs-lookup"><span data-stu-id="c07e3-138">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="c07e3-139">Когда одна подстановка выполняет эту замену, в Хамилтониан есть только пять классов терминов.</span><span class="sxs-lookup"><span data-stu-id="c07e3-139">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="c07e3-140">Эти пять классов соответствуют различным способам выбора $p, q $ и $p, q, r, s $ в одном основном тексте и двух основных терминах в Хамилтониан.</span><span class="sxs-lookup"><span data-stu-id="c07e3-140">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="c07e3-141">Эти пять классов, если $p>q>r>s $ и орбиты с реальными значениями, являются</span><span class="sxs-lookup"><span data-stu-id="c07e3-141">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="c07e3-142">\бегин{алигн} H_ {PP} a_p ^ \дагжер a_p &= \ sum_p \фрак{H_ {PP}} {2} (1-Z_p) \\ \\ H_ {PQ} (a_p ^ \дагжер a_q + a ^ \ dagger_q a_p) &= \фрак{H_ {PQ}} {2} \лефт (\ prod_ {j = q + 1} ^ {p-1} Z_j \ригхт) \лефт (X_pX_q + Y_pY_q \ригхт) \\ \\ H_ {пккп} n_p n_q &= \фрак{H_ {пккп}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{H_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {PQRS} &= \frac{H_ {PQRS}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}</span><span class="sxs-lookup"><span data-stu-id="c07e3-142">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="c07e3-143">При создании такого Хамилтонианса вручную требуется только применение этих правил замены. это может оказаться невозможным для больших молекул, которые могут состоять из миллионов Хамилтонианных терминов.</span><span class="sxs-lookup"><span data-stu-id="c07e3-143">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="c07e3-144">В качестве альтернативы можно автоматически создать `JordanWignerEncoding` заданное `FermionHamiltonian` представление хамилтониан.</span><span class="sxs-lookup"><span data-stu-id="c07e3-144">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="c07e3-145">После создания Хамилтонианс в этой форме мы можем использовать узел алгоритмов моделирования такта для компиляции Dynamics, созданного $e ^ {-ИХТ} $ в последовательности простейших шлюзов (в пределах некоторой определяемой пользователем отказоустойчивости).</span><span class="sxs-lookup"><span data-stu-id="c07e3-145">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="c07e3-146">В документации по алгоритму рассматриваются два наиболее популярных метода моделирования такта, кубитизатион и Троттер — Сузуки формулы.</span><span class="sxs-lookup"><span data-stu-id="c07e3-146">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="c07e3-147">Мы предоставляем реализации для обоих методов в библиотеке моделирования Хамилтониан.</span><span class="sxs-lookup"><span data-stu-id="c07e3-147">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>