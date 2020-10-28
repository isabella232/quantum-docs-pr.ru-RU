---
uid: Microsoft.Quantum.Logical.NotEqualB
title: Функция Нотекуалб
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709839"
---
# <a name="notequalb-function"></a><span data-ttu-id="2f057-102">Функция Нотекуалб</span><span class="sxs-lookup"><span data-stu-id="2f057-102">NotEqualB function</span></span>

<span data-ttu-id="2f057-103">Пространство имен: [Microsoft. тактов. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2f057-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2f057-104">Пакеты [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f057-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f057-105">Возвращает значение true только в том случае, если два входных значения не равны.</span><span class="sxs-lookup"><span data-stu-id="2f057-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="2f057-106">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2f057-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="2f057-107">ответ. [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f057-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f057-108">Первое сравниваемое значение.</span><span class="sxs-lookup"><span data-stu-id="2f057-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="2f057-109">б: [логическое](xref:microsoft.quantum.lang-ref.bool) значение</span><span class="sxs-lookup"><span data-stu-id="2f057-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f057-110">Второе сравниваемое значение.</span><span class="sxs-lookup"><span data-stu-id="2f057-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2f057-111">Выходные данные: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f057-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f057-112">`true` Если и, только если `a` не равно `b` .</span><span class="sxs-lookup"><span data-stu-id="2f057-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f057-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f057-113">Remarks</span></span>

<span data-ttu-id="2f057-114">Следующие эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="2f057-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```