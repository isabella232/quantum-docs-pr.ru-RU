---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Функция Лесссанорекуали
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197572"
---
# <a name="lessthanorequali-function"></a>Функция Лесссанорекуали

Пространство имен: [Microsoft. тактов. Logical](xref:Microsoft.Quantum.Logical)

Пакет: [Microsoft. такт. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Возвращает значение true только в том случае, если число меньше или равно другому числу.

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Входные данные

### <a name="a--int"></a>ответ. [int](xref:microsoft.quantum.lang-ref.int)

Первое сравниваемое значение.


### <a name="b--int"></a>б: [int](xref:microsoft.quantum.lang-ref.int)

Второе сравниваемое значение.



## <a name="output--bool"></a>Выходные данные: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` только в случае, если `a` меньше или равно `b` .

## <a name="remarks"></a>Комментарии

Следующие эквивалентны:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```