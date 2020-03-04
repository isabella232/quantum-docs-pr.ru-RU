---
title: Глоссарий по тактовым вычислениям
description: Глоссарий общих терминов, действий и объектов, используемых в тактовых вычислениях.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: f47d87f5bc9d677baa12a7ac1581af72894e8a4b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909897"
---
# <a name="quantum-computing-glossary"></a>Глоссарий по тактовым вычислениям

|Термин|Определение|
|-------------|----------|
|Прилегающий|Комплексно сопряженное перестановка операции. Для операций, которые реализуют единые операторы, прилегающим является обратная операция.|
|Предназначен|Операции и функции в совокупности называются *вызываемыми*.|
|Standard|Операции и функции, определенные в Q # здание в логике, определенной в версионного. Реализация стандартной библиотеки не зависит от целевых компьютеров.|
|Группа Клиффорд|Набор операций, занимающих октантс Sphere БЛОЧ. К ним относятся: `X`, `Y`, `Z`, `H` и `S`|
|Управляет|Операция-такт, которая принимает один или несколько Кубитс как созидателями для целевой операции.|
|Нотация Дирак|Сокращенное представление состояния такта. Дополнительные сведения см. в разделе [Дирак Notation](xref:microsoft.quantum.concepts.dirac) .|
|Еиженвалуес и основе собственных векторов|Дополнительные сведения см. в [разделе "дополнительная матрица](xref:microsoft.quantum.concepts.matrix-advanced) ".|
|Пара EPR|Также называется [состоянием колокольчика](https://en.wikipedia.org/wiki/Bell_state)|
|Результатом|Изменение состояния с течением времени. Пример см. в разделе <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials>. |
|Компонент|Чисто классические подпрограммы на языке Q #|
| <a id="global-phase"></a>Глобальный этап | Два состояния, идентичные кратному комплексному числу $e ^ {и\фи} $, отличаются до глобального этапа. В отличие от локальных фаз, глобальные фазы не могут быть замечены в любом измерении. Дополнительные сведения см. в разделе [измерения Паули](xref:microsoft.quantum.concepts.pauli) . |
|Измерения|Получение классического бита от кубит (или набора Кубитс). Дополнительные сведения см. в разделе [Основные понятия кубит](xref:microsoft.quantum.concepts.qubit) .|
|Изменяемый|Переменная, значение которой можно изменить после ее создания.|
|Пространство имен|Метка для коллекции связанных имен (обычно операции, функции и типы). Например, пространство имен [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) помечает все символы, определенные в стандартной библиотеке и помогающие при подготовке начальных состояний.|
|Операция|Базовая единица выполнения такта в Q #. Это похоже на функции в C, C++ и Python или статический метод в C# и Java.|
|Приложение оператора|Выполнение операции над тактом. Обычно это применяет единую матрицу к текущему вектору состояния. Дополнительные сведения см. [в статье Введение в тактовые концепции](xref:microsoft.quantum.concepts.intro) .|
|Oracle;|Подпрограммы, которая предоставляет зависящую от данных информацию в алгоритме такта во время выполнения. Как правило, целью является предоставление части выходных данных, соответствующих входным данным, находящимся в части.   |
|Частичное приложение|Вызов функции или операции без всех обязательных параметров. Метод возвращает новый вызываемый объект, которому требуются только отсутствующие параметры, указанные во время применения в будущем приложении.|
|Операторы Паули|`X`, `Y` и `Z` тактовыми шлюзами.|
|Версионного|Набор примитивных и классических операций и функций, определенных для каждого отдельного целевого компьютера, а не на уровне Q #.|
|Тактовая цепь|Представление программы для тактового компьютера. Дополнительные сведения см. в разделе <xref:microsoft.quantum.concepts.circuits>.|
|Состояние такта|Представление Кубитс в системе. Обычно это обозначается как сложный вектор столбцов. Дополнительные сведения см. в разделе <xref:microsoft.quantum.concepts.vectors>. |
|кубит|Единица хранилища тактов. Дополнительные сведения см. в разделе <xref:microsoft.quantum.concepts.qubit>.|
|Повторение до — успешное завершение|Алгоритм такта, probabilistically с ошибкой. При сбое подпрограммы повторит попытку, пока не завершится успешно (или достигнут предел). |
|Целевой компьютер|Цель компиляции, которая понижает абстрактную тактовую программу для оборудования или моделирования. Обычно это включает повторную запись для многих целей, включая замену шлюза, кодирование для коррекции ошибок, геометрическую структуру и другие.|
|Кортеж|Разделенные запятыми типы, сгруппированные с помощью круглых скобок. |
|Определяемый пользователем тип|Коллекция встроенных или ранее определенных типов, которые могут называться одним блоком.|
