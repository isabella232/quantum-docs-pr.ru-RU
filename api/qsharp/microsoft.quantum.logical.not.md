---
uid: Microsoft.Quantum.Logical.Not
title: Not, функция
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197455"
---
# <a name="not-function"></a>Not, функция

Пространство имен: [Microsoft. тактов. Logical](xref:Microsoft.Quantum.Logical)

Пакет: [Microsoft. такт. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Возвращает логическое отрицание значения.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Входные данные

### <a name="value--bool"></a>значение: [bool](xref:microsoft.quantum.lang-ref.bool)

Значение, которое необходимо инвертировать.



## <a name="output--bool"></a>Выходные данные: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Если и только если `value` имеет значение `false` .

## <a name="remarks"></a>Комментарии

Следующие эквивалентны:

```Q#
let x = not value;
let x = Not(value);
```