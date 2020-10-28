---
uid: Microsoft.Quantum.Logical.NotEqualI
title: Функция Нотекуали
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709826"
---
# <a name="notequali-function"></a><span data-ttu-id="d0acf-102">Функция Нотекуали</span><span class="sxs-lookup"><span data-stu-id="d0acf-102">NotEqualI function</span></span>

<span data-ttu-id="d0acf-103">Пространство имен: [Microsoft. тактов. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d0acf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d0acf-104">Пакеты [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0acf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0acf-105">Возвращает значение true только в том случае, если два входных значения не равны.</span><span class="sxs-lookup"><span data-stu-id="d0acf-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="d0acf-106">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d0acf-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d0acf-107">ответ. [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0acf-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0acf-108">Первое сравниваемое значение.</span><span class="sxs-lookup"><span data-stu-id="d0acf-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="d0acf-109">б: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0acf-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0acf-110">Второе сравниваемое значение.</span><span class="sxs-lookup"><span data-stu-id="d0acf-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d0acf-111">Выходные данные: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0acf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d0acf-112">`true` Если и, только если `a` не равно `b` .</span><span class="sxs-lookup"><span data-stu-id="d0acf-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0acf-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0acf-113">Remarks</span></span>

<span data-ttu-id="d0acf-114">Следующие эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="d0acf-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```