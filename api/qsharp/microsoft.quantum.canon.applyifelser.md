---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Операция Апплифелсер
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209542"
---
# <a name="applyifelser-operation"></a>Операция Апплифелсер

Пространство имен: [Microsoft. тактов. Canon](xref:Microsoft.Quantum.Canon)

Пакет: [Microsoft. такт. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Применяет одну из двух операций в зависимости от значения классического результата.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Описание

Учитывая результат `result` , применяет операцию `zeroOp` с в `zeroInput` качестве входных данных, если равен `result` `Zero` , и применяется, `oneOp(oneInput)` когда `result == One` .

## <a name="input"></a>Входные данные

### <a name="result--__invalidresult__"></a>результат: __недопустимо <Result>__

Результат измерения, используемый для определения `zeroOp` применения или `oneOp` .


### <a name="zeroop--t--unit"></a>Зеруп: 'T = [единица](xref:microsoft.quantum.lang-ref.unit)> 

Операция, которая должна быть применена, когда `result == Zero` .


### <a name="zeroinput--t"></a>Зероинпут: 'T

Входные данные, которые должны быть предоставлены в `zeroOp` when `result == Zero` .


### <a name="oneop--u--unit"></a>Онеоп: "U = [единица](xref:microsoft.quantum.lang-ref.unit)> 

Операция, которая должна быть применена, когда `result == One` .


### <a name="oneinput--u"></a>Онеинпут: ' U

Входные данные, которые должны быть предоставлены в `oneOp` when `result == One` .



## <a name="output--unit"></a>Выходные данные: [единица измерения](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Параметры типа

### <a name="t"></a>Е

Тип входных данных операции `zeroOp` , которая должна применяться условно.
### <a name="u"></a>' U

Тип входных данных операции `oneOp` , которая должна применяться условно.

## <a name="see-also"></a>См. также:

- [Microsoft. тактов. Canon. Апплифзеро](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. тактов. Canon. Апплифоне](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. тактов. Canon. Апплифелсерк](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. тактов. Canon. Апплифелсера](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. тактов. Canon. Апплифелсерка](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)