---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: Функция Паулиеволутионсет
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732104"
---
# <a name="paulievolutionset-function"></a>Функция Паулиеволутионсет

Пространство имен: [Microsoft. тактов. Моделирование](xref:Microsoft.Quantum.Simulation)

Пакеты [](https://nuget.org/packages/)


Представляет динамический генератор как набор моделирующих шлюзов и расширение на основе Паули.

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Выходные данные: [эволюционный](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Объект `EvolutionSet` , который сопоставляет объект `GeneratorIndex` для Паули на уровне еволутионунитари.

## <a name="remarks"></a>Remarks

Это достигается частичным применением <xref:microsoft.quantum.simulation.paulievolutionfunction> .