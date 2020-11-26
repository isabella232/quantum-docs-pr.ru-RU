---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Определяемый пользователем тип Секуентиалмодел
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196180"
---
# <a name="sequentialmodel-user-defined-type"></a>Определяемый пользователем тип Секуентиалмодел

Пространство имен: [Microsoft. тактов. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Пакет: [Microsoft. тактов. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Описывает модель классификатора такта, состоящую из последовательности параметризованных и контролируемых поворотов, присваивания углов поворота и смещения между двумя классами, распознаваемыми моделью.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Именованные элементы

### <a name="structure--controlledrotation"></a>Структура: [контролледротатион](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Последовательность управляемых поворотов, используемых для классификации входных данных.
### <a name="parameters--double"></a>Параметры: [Double](xref:microsoft.quantum.lang-ref.double)[]

Присваивание углов поворота к заданной структуре классификации.
### <a name="bias--double"></a>Уровень смещения: [Double](xref:microsoft.quantum.lang-ref.double)

Сдвиг между двумя классами, распознаваемыми этим классификатором.

## <a name="references"></a>Ссылки

- [Арксив: 1804.00633](https://arxiv.org/abs/1804.00633)