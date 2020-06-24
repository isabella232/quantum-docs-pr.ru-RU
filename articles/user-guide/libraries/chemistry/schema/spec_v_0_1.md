---
title: Спецификация схемы брумбридже (версия 0,1)
description: Сведения о спецификациях Брумбридже такта химия Schema v 0,1 для библиотеки Microsoft тактов химия.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276047"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="7e301-103">Спецификация брумбридже 0,1</span><span class="sxs-lookup"><span data-stu-id="7e301-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="7e301-104">Ключевые слова "обязательно", "не должны", "обязательно", "должно", "не", "должно", "не должно", "рекомендуется", "Май" и "необязательно" в этом документе должны интерпретироваться, как описано в [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="7e301-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="7e301-105">Любая боковая панель с заголовками «Примечание», «информация» или «предупреждение» является информативной.</span><span class="sxs-lookup"><span data-stu-id="7e301-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="7e301-106">Введение</span><span class="sxs-lookup"><span data-stu-id="7e301-106">Introduction</span></span> ##

<span data-ttu-id="7e301-107">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-107">This section is informative.</span></span>

<span data-ttu-id="7e301-108">Документы брумбридже предназначены для обмена экземплярами проблем моделирования в тактовой химия для обработки с помощью моделирования тактов и программирования цепочек инструментов.</span><span class="sxs-lookup"><span data-stu-id="7e301-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="7e301-109">Сериализация</span><span class="sxs-lookup"><span data-stu-id="7e301-109">Serialization</span></span> ##

<span data-ttu-id="7e301-110">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-110">This section is normative.</span></span>

<span data-ttu-id="7e301-111">Документ Брумбридже должен быть сериализован как [документ YAML 1,2](http://yaml.org/spec/) , представляющий объект JSON, как описано в [RFC 4627](https://tools.ietf.org/html/rfc4627) , раздел 2,2.</span><span class="sxs-lookup"><span data-stu-id="7e301-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="7e301-112">Объект, сериализованный в YAML, должен иметь свойство `"$schema"` , значение которого равно `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` , и должно быть допустимым в соответствии с требованиями схемы JSON — 06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="7e301-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="7e301-113">В оставшейся части этой спецификации объект Брумбридже будет ссылаться на объект JSON, десериализованный из документа YAML Брумбридже.</span><span class="sxs-lookup"><span data-stu-id="7e301-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="7e301-114">Если явно не указано иное, объекты не должны иметь дополнительных свойств, кроме указанных явно в этом документе.</span><span class="sxs-lookup"><span data-stu-id="7e301-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="7e301-115">Дополнительные определения</span><span class="sxs-lookup"><span data-stu-id="7e301-115">Additional Definitions</span></span> ##

<span data-ttu-id="7e301-116">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="7e301-117">Объекты Quantity</span><span class="sxs-lookup"><span data-stu-id="7e301-117">Quantity Objects</span></span> ###

<span data-ttu-id="7e301-118">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-118">This section is normative.</span></span>

<span data-ttu-id="7e301-119">_Объект Quantity_ является объектом JSON и должен иметь свойство `units` , значение которого является одним из допустимых значений, перечисленных в таблице 1.</span><span class="sxs-lookup"><span data-stu-id="7e301-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="7e301-120">Объект Quantity является _простым объектом Quantity_ , если `value` в дополнение к его свойству имеется единственное свойство `units` .</span><span class="sxs-lookup"><span data-stu-id="7e301-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="7e301-121">Значение `value` свойства должно быть числом.</span><span class="sxs-lookup"><span data-stu-id="7e301-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="7e301-122">Объект Quantity — это _привязанный объект Quantity_ , если он содержит свойства `lower` и `upper` в дополнение к его `units` свойству.</span><span class="sxs-lookup"><span data-stu-id="7e301-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="7e301-123">Значения `lower` `upper` свойств и должны быть числами.</span><span class="sxs-lookup"><span data-stu-id="7e301-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="7e301-124">Связанный объект Quantity может иметь свойство `value` , значение которого является числом.</span><span class="sxs-lookup"><span data-stu-id="7e301-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="7e301-125">Объект Quantity — это _объект количества разреженных массивов_ , если он содержит свойство `format` и свойство `values` в дополнение к его `units` свойству.</span><span class="sxs-lookup"><span data-stu-id="7e301-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="7e301-126">Значение `format` должно быть строкой `sparse` .</span><span class="sxs-lookup"><span data-stu-id="7e301-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="7e301-127">Значение `values` свойства должно быть массивом.</span><span class="sxs-lookup"><span data-stu-id="7e301-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="7e301-128">Каждый элемент `values` должен быть массивом, представляющим индексы, и значением количества разреженных массивов.</span><span class="sxs-lookup"><span data-stu-id="7e301-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="7e301-129">Индексы каждого элемента объекта количества разреженных массивов должны быть уникальными во всем объекте количества разреженных массивов.</span><span class="sxs-lookup"><span data-stu-id="7e301-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="7e301-130">Если индекс имеет значение `0` , синтаксический анализатор должен обрабатывать объект Quantity разреженного массива идентично объекту Quantity разреженного массива, в котором этот индекс отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7e301-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="7e301-131">Объект Quantity должен иметь значение</span><span class="sxs-lookup"><span data-stu-id="7e301-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="7e301-132">Объект простого количества,</span><span class="sxs-lookup"><span data-stu-id="7e301-132">a simple quantity object,</span></span>
- <span data-ttu-id="7e301-133">связанный объект Quantity или</span><span class="sxs-lookup"><span data-stu-id="7e301-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="7e301-134">Объект количества разреженных массивов.</span><span class="sxs-lookup"><span data-stu-id="7e301-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="7e301-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="7e301-135">Examples</span></span> ###

<span data-ttu-id="7e301-136">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-136">This section is informative.</span></span>

<span data-ttu-id="7e301-137">Простое количество, представляющее $1.9844146837 \, \масрм{ха} $:</span><span class="sxs-lookup"><span data-stu-id="7e301-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="7e301-138">Ограниченное количество, представляющее равномерное распределение по интервалу $ [-7,-6] \, \масрм{ха} $:</span><span class="sxs-lookup"><span data-stu-id="7e301-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="7e301-139">Ниже приведено количество разреженных массивов с элементом `[1, 2]` , равным `hello` , и элементом, `[3, 4]` равным `world` :</span><span class="sxs-lookup"><span data-stu-id="7e301-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="7e301-140">Раздел формата</span><span class="sxs-lookup"><span data-stu-id="7e301-140">Format Section</span></span> ##

<span data-ttu-id="7e301-141">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-141">This section is normative.</span></span>

<span data-ttu-id="7e301-142">Объект Брумбридже должен иметь свойство `format` , значение которого является объектом JSON с одним свойством с именем `version` .</span><span class="sxs-lookup"><span data-stu-id="7e301-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="7e301-143">`version`Свойство должно иметь значение `"0.1"` .</span><span class="sxs-lookup"><span data-stu-id="7e301-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="7e301-144">Пример</span><span class="sxs-lookup"><span data-stu-id="7e301-144">Example</span></span> ###

<span data-ttu-id="7e301-145">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="7e301-146">Раздел целых наборов</span><span class="sxs-lookup"><span data-stu-id="7e301-146">Integral Sets Section</span></span> ##

<span data-ttu-id="7e301-147">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-147">This section is normative.</span></span>

<span data-ttu-id="7e301-148">Объект Брумбридже должен иметь свойство `integral_sets` , значение которого является массивом JSON.</span><span class="sxs-lookup"><span data-stu-id="7e301-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="7e301-149">Каждый элемент в значении `integral_sets` свойства должен быть объектом JSON, описывающим один набор целых чисел, как описано в оставшейся части этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7e301-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="7e301-150">В оставшейся части этого раздела термин «объект целого набора» будет ссылаться на элемент в значении `integral_sets` свойства объекта брумбридже.</span><span class="sxs-lookup"><span data-stu-id="7e301-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="7e301-151">Каждый объект целочисленного набора должен иметь свойство `metadata` , значение которого является объектом JSON.</span><span class="sxs-lookup"><span data-stu-id="7e301-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="7e301-152">Значение `metadata` может быть пустым объектом JSON (то есть `{}` ) или может содержать дополнительные свойства, определенные разработчиком.</span><span class="sxs-lookup"><span data-stu-id="7e301-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="7e301-153">Раздел хамилтониан</span><span class="sxs-lookup"><span data-stu-id="7e301-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="7e301-154">Обзор</span><span class="sxs-lookup"><span data-stu-id="7e301-154">Overview</span></span> ####

<span data-ttu-id="7e301-155">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-155">This section is informative.</span></span>

<span data-ttu-id="7e301-156">`hamiltonian`Свойство каждого объекта целочисленного набора описывает хамилтониан для определенной проблемы тактовой химия, вычисляя его один-и два основных термина в виде разреженных массивов вещественных чисел.</span><span class="sxs-lookup"><span data-stu-id="7e301-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="7e301-157">Операторы Хамилтониан, описанные каждым объектом целочисленного набора, принимают форму</span><span class="sxs-lookup"><span data-stu-id="7e301-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="7e301-158">$ $ H = \сум \_ \{ i, j \} \сум \_ {\сигма\ин \\ {\упарров, \довнарров \\ }} H \_ \{ ИЖ \} a ^ \{ \дагжер \} \_ {i, \сигма}. \_ {j, \сигма} + \фрак {1} {2} \сум \_ \{ i, j, k, l \} \сум \_ {\сигма, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="7e301-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="7e301-159">Здесь $h _ {ижкл} = (ИЖ | КЛ) $ в соглашении Мулликен.</span><span class="sxs-lookup"><span data-stu-id="7e301-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="7e301-160">Для ясности термина «один электронное» —</span><span class="sxs-lookup"><span data-stu-id="7e301-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="7e301-161">$ $ h_ {ИЖ} = \инт {\масрм d} x \пси ^ \* \_ i (x) \лефт (\фрак {1} {2} \набла ^ 2 + \сум \_ {A} \фрак{з \_ а} {| x-x \_ A |}  \ригхт) \пси \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="7e301-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="7e301-162">и два электронного выражения:</span><span class="sxs-lookup"><span data-stu-id="7e301-162">and the two-electron term is</span></span>

<span data-ttu-id="7e301-163">$ $ h \_ \{ ижкл \} = \иинт \{ \масрм d \} x ^ 2 \пси ^ \{ \* \} \_ i (x \_ 1) \пси \_ j (x \_ 1) \фрак \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \пси \_ k ^ \{ \* \} (x \_ 2) \пси \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="7e301-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="7e301-164">Как отмечалось в описании [ `basis_set` свойства](#basis-set-object) каждого элемента `integral_sets` свойства, мы еще дальше предполагаю, что используемые основные функции являются реальными.</span><span class="sxs-lookup"><span data-stu-id="7e301-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="7e301-165">Это позволяет нам использовать следующие симметриес между терминами для сжатия представления Хамилтониан.</span><span class="sxs-lookup"><span data-stu-id="7e301-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="7e301-166">$ $ h_ {ижкл} = h_ {ижлк} = h_ {жикл} = h_ {жилк} = h_ {клиж} = h_ {клжи} = h_ {лкиж} = h_ {лкжи}.</span><span class="sxs-lookup"><span data-stu-id="7e301-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="7e301-167">Содержимое</span><span class="sxs-lookup"><span data-stu-id="7e301-167">Contents</span></span> ####

<span data-ttu-id="7e301-168">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-168">This section is normative.</span></span>

<span data-ttu-id="7e301-169">Каждый целый набор должен иметь свойство `hamiltonian` , значение которого является объектом JSON.</span><span class="sxs-lookup"><span data-stu-id="7e301-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="7e301-170">Значение `hamiltonian` Свойства известно как объект хамилтониан и должно иметь свойства `one_electron_integrals` и `two_electron_integrals` , как описано в оставшейся части этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7e301-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="7e301-171">Объект Хамилтониан также может иметь свойство `particle_hole_representation` .</span><span class="sxs-lookup"><span data-stu-id="7e301-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="7e301-172">При наличии значение `particle_hole_representation` должно соответствовать формату, описанному в оставшейся части этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7e301-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="7e301-173">Объект «интегралы за один электронный»</span><span class="sxs-lookup"><span data-stu-id="7e301-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="7e301-174">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-174">This section is normative.</span></span>

<span data-ttu-id="7e301-175">`one_electron_integrals`Свойство объекта ХАМИЛТОНИАН должно быть разреженным массивом, индексом которого является два целых числа и значения которых являются числами.</span><span class="sxs-lookup"><span data-stu-id="7e301-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="7e301-176">Каждый термин должен иметь индексы `[i, j]` `i >= j` , где.</span><span class="sxs-lookup"><span data-stu-id="7e301-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="7e301-177">МЕТИМ Это отражает симметрию, которая $h _ {ИЖ} = h_ {ji} $, что является следствием того факта, что Хамилтониан является Хермитиан.</span><span class="sxs-lookup"><span data-stu-id="7e301-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="7e301-178">Пример</span><span class="sxs-lookup"><span data-stu-id="7e301-178">Example</span></span> ######

<span data-ttu-id="7e301-179">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-179">This section is informative.</span></span>

<span data-ttu-id="7e301-180">Следующее количество разреженных массивов представляет хамилтониан $ $ H = \лефт (-5,0 (a ^ \{ \дагжер \} \_ {1, \упарров} a \_ {1, \упарров} + a ^ \{ \дагжер \} \_ {1, \довнарров} \_ {1, \довнарров}) + 0,17 (a ^ \{ \дагжер \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow}. \_ {2, \uparrow} + a ^ \{ \dagger {2, \downarrow} a { \} \_ \_ 1, \downarrow} + a ^ \dagger \{ \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="7e301-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="7e301-181">Брумбридже использует индексирование, основанное на 1.</span><span class="sxs-lookup"><span data-stu-id="7e301-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="7e301-182">Объект интегралов с двумя электронными данными</span><span class="sxs-lookup"><span data-stu-id="7e301-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="7e301-183">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-183">This section is normative.</span></span>

<span data-ttu-id="7e301-184">`two_electron_integrals`Свойство объекта ХАМИЛТОНИАН должно быть количеством разреженных массивов с одним дополнительным свойством с именем `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="7e301-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="7e301-185">Каждый элемент значения `two_electron_integrals` должен иметь четыре индекса.</span><span class="sxs-lookup"><span data-stu-id="7e301-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="7e301-186">Каждое `two_electron_integrals` свойство должно иметь `index_convention` свойство.</span><span class="sxs-lookup"><span data-stu-id="7e301-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="7e301-187">Значение `index_convention` свойства должно быть одним из допустимых значений, перечисленных в таблице 1.</span><span class="sxs-lookup"><span data-stu-id="7e301-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="7e301-188">Если значение `index_convention` равно `mulliken` , то для каждого элемента с `two_electron_integrals` количеством разреженных массивов средство синтаксического анализа, загружая документ брумбридже, должно создать экземпляр хамилтониан, равный двум электронным операторам $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, где $i $, $j $, $k $ и $l $ должны быть целыми числами в диапазоне от 1 до числа электронов, заданных `n_electrons` свойством объекта целочисленного набора, и где $h _ {i, j, k, l} $ является элементом `[i, j, k, l, h(i, j, k, l)]` количества разреженного массива.</span><span class="sxs-lookup"><span data-stu-id="7e301-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="7e301-189">симметриес</span><span class="sxs-lookup"><span data-stu-id="7e301-189">Symmetries</span></span> ######

<span data-ttu-id="7e301-190">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-190">This section is normative.</span></span>

<span data-ttu-id="7e301-191">Если `index_convention` свойство `two_electron_integrals` объекта равно `mulliken` , то при наличии элемента с индексами `[i, j, k, l]` следующие индексы не должны присутствовать, если они не равны `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="7e301-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="7e301-192">Поскольку `index_convention` свойство является объектом разреженного количества, индексы не могут повторяться в разных элементах.</span><span class="sxs-lookup"><span data-stu-id="7e301-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="7e301-193">В частности, если имеется элемент с индексами `[i, j, k, l]` , другие элементы не могут иметь эти индексы.</span><span class="sxs-lookup"><span data-stu-id="7e301-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="7e301-194">Пример</span><span class="sxs-lookup"><span data-stu-id="7e301-194">Example</span></span> #######

<span data-ttu-id="7e301-195">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-195">This section is informative.</span></span>

<span data-ttu-id="7e301-196">Следующий объект указывает Хамилтониан</span><span class="sxs-lookup"><span data-stu-id="7e301-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="7e301-197">$ $ H = \frac12 \сум \_ {\сигма, \рхо\ин \\ {\упарров, \довнарров \\ }} \биггр (1,6 a ^ {\дагжер} \_ {1, \сигма} а ^ {\дагжер} \_ {1, \рхо} a \_ {1, \рхо} \_ {1, \сигма}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 а ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a {3, \sigma}- \_ 0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} \_ {3, \rho} a \_ {2, \sigma}-0,1 а ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho}. \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 а ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} \_ {6, \rho} a \_ {1, \sigma}-0,1 а ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 а ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \рхо} \_ {6, \рхо} a \_ {1, \сигма}-0,1 а ^ {\дагжер} \_ {2, \сигма} a ^ {\дагжер} \_ {3, \рхо} a \_ {1, \Рхо} a \_ {6, \сигма}\биггр) \\ , \текстрм{ха}.</span><span class="sxs-lookup"><span data-stu-id="7e301-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a><span data-ttu-id="7e301-198">Частица — объект представления отверстий</span><span class="sxs-lookup"><span data-stu-id="7e301-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="7e301-199">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-199">This section is normative.</span></span>

<span data-ttu-id="7e301-200">Объект представления частица (дыра) указывает, что хранимые интегралы определяются по отношению к части частицы, где операторы создания и аннихилатион описывают ексЦитатионс от используемого состояния ссылки, например Хартри – Фокк State.</span><span class="sxs-lookup"><span data-stu-id="7e301-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="7e301-201">Объект является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7e301-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="7e301-202">Если объект не указан, Хамилтониан интерпретируется как не заданный в представлении частиц.</span><span class="sxs-lookup"><span data-stu-id="7e301-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="7e301-203">При наличии значение `particle_hole_representation` должно быть разреженным массивом объектов Quantity, индексами которого являются четыре целых числа, а значения — числом и строкой.</span><span class="sxs-lookup"><span data-stu-id="7e301-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="7e301-204">Строковая часть значения каждого элемента должна содержать только символы `'+'` и `'-'` , указывающие, является ли данный фактор в термине оператором создания или аннихилатион в представлении частица — отверстие.</span><span class="sxs-lookup"><span data-stu-id="7e301-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="7e301-205">Например, `"-+++"` обреагирует на отверстие, создаваемое на сайте $i $ и частицы, создаваемые на сайтах $j, k $ и $l $.</span><span class="sxs-lookup"><span data-stu-id="7e301-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="7e301-206">Так как значение `particle_hole_representation` является объектом количества разреженных массивов, `unit` `format` необходимо указать свойства и.</span><span class="sxs-lookup"><span data-stu-id="7e301-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="7e301-207">Допустимые единицы перечислены в таблице 1.</span><span class="sxs-lookup"><span data-stu-id="7e301-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="7e301-208">`format`Свойство является обязательным и указывает, указаны ли коэффициенты хамилтониан в виде сжатого или разреженного массива.</span><span class="sxs-lookup"><span data-stu-id="7e301-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="7e301-209">В текущей версии поддерживаются только разреженные массивы с интерпретацией того, что все неопределенные элементы имеют $0 $, но в будущих версиях может быть добавлена поддержка дополнительных значений `format` Свойства.</span><span class="sxs-lookup"><span data-stu-id="7e301-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="7e301-210">Раздел начального состояния</span><span class="sxs-lookup"><span data-stu-id="7e301-210">Initial State Section</span></span> ###

<span data-ttu-id="7e301-211">Объект initial_state_suggestion Указывает начальные состояния такта, представляющие интерес для указанного Хамилтониан.</span><span class="sxs-lookup"><span data-stu-id="7e301-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="7e301-212">Этот объект должен быть массивом объектов JSON `state` .</span><span class="sxs-lookup"><span data-stu-id="7e301-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="7e301-213">Объект State</span><span class="sxs-lookup"><span data-stu-id="7e301-213">State object</span></span> ####

<span data-ttu-id="7e301-214">Каждое из состояний представляет собой перестановку занятых орбит.</span><span class="sxs-lookup"><span data-stu-id="7e301-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="7e301-215">Каждый объект состояния должен иметь `label` свойство, содержащее строку.</span><span class="sxs-lookup"><span data-stu-id="7e301-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="7e301-216">Каждый объект состояния должен иметь `superposition` свойство, содержащее массив состояний и их ненормализованные амплитуды.</span><span class="sxs-lookup"><span data-stu-id="7e301-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="7e301-217">Например, начальное состояние $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\дагжер} \_ {1, \упарров}а ^ {\дагжер} \_ {2, \упарров}а ^ {\дагжер} \_ {2, \довнарров}) \кет {0} $ $ $ $ \кет{е} = \frac{0.1 (a ^ {\дагжер} \_ {1, \упарров}а ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} $ $ представлены</span><span class="sxs-lookup"><span data-stu-id="7e301-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="7e301-218">Объект базового набора</span><span class="sxs-lookup"><span data-stu-id="7e301-218">Basis Set Object</span></span> ####

<span data-ttu-id="7e301-219">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-219">This section is normative.</span></span>

<span data-ttu-id="7e301-220">Каждый объект целочисленного набора может иметь `basis_set` свойство.</span><span class="sxs-lookup"><span data-stu-id="7e301-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="7e301-221">При наличии значение `basis_set` свойства должно быть объектом с двумя свойствами `type` и `name` .</span><span class="sxs-lookup"><span data-stu-id="7e301-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="7e301-222">Основные функции, определяемые значением `basis_set` свойства, должны быть реальными.</span><span class="sxs-lookup"><span data-stu-id="7e301-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="7e301-223">Предположение, что все основные функции являются реальными, могут быть неослабленными в будущих версиях этой спецификации.</span><span class="sxs-lookup"><span data-stu-id="7e301-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="7e301-224">Таблицы и списки</span><span class="sxs-lookup"><span data-stu-id="7e301-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="7e301-225">Таблица 1.</span><span class="sxs-lookup"><span data-stu-id="7e301-225">Table 1.</span></span> <span data-ttu-id="7e301-226">Разрешенные физические устройства</span><span class="sxs-lookup"><span data-stu-id="7e301-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="7e301-227">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-227">This section is normative.</span></span>

<span data-ttu-id="7e301-228">Любая строка, задающая единицу, должна быть одной из следующих:</span><span class="sxs-lookup"><span data-stu-id="7e301-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="7e301-229">Средства синтаксического анализа и производители должны рассматривать следующие простые объекты Quantity как эквивалентные:</span><span class="sxs-lookup"><span data-stu-id="7e301-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="7e301-230">Таблица 2.</span><span class="sxs-lookup"><span data-stu-id="7e301-230">Table 2.</span></span> <span data-ttu-id="7e301-231">Допустимые соглашения об индексах</span><span class="sxs-lookup"><span data-stu-id="7e301-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="7e301-232">Этот раздел является нормативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-232">This section is normative.</span></span>

<span data-ttu-id="7e301-233">Любая строка, задающая соглашение об индексах, должна быть одной из следующих:</span><span class="sxs-lookup"><span data-stu-id="7e301-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="7e301-234">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-234">This section is informative.</span></span>

<span data-ttu-id="7e301-235">В будущих версиях этой спецификации могут быть введены дополнительные соглашения об индексах.</span><span class="sxs-lookup"><span data-stu-id="7e301-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="7e301-236">Интерпретация соглашений об индексах</span><span class="sxs-lookup"><span data-stu-id="7e301-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="7e301-237">Этот раздел является информативным.</span><span class="sxs-lookup"><span data-stu-id="7e301-237">This section is informative.</span></span>