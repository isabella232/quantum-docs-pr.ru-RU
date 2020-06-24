---
title: Знакомство со стандартными библиотеками Microsoft Q#
description: Узнайте о стандартных библиотеках Microsoft Q#, которые определяют операции, функции и типы данных, используемые в квантовых программах.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273814"
---
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="4365d-103">Введение в стандартные библиотеки Q#</span><span class="sxs-lookup"><span data-stu-id="4365d-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="4365d-104">В дополнение к Q# предоставляется широкий набор полезных операций, функций и пользовательских типов, которые собраны в *стандартные библиотеки* Q#.</span><span class="sxs-lookup"><span data-stu-id="4365d-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="4365d-105">[Пакет NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit), который устанавливается в процессе [установки и проверки](xref:microsoft.quantum.install), содержит компилятор Q# и элементы стандартной библиотеки, которые реализованы на целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4365d-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="4365d-106">[Пакет `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) содержит другую часть стандартных библиотек Q#, переносимую между целевыми компьютерами.</span><span class="sxs-lookup"><span data-stu-id="4365d-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="4365d-107">Символы, определенные в стандартных библиотеках Q#, более подробно описаны в [документации по API](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="4365d-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="4365d-108">В следующих разделах мы рассмотрим наиболее важные функции из каждой части стандартных библиотек и вкратце опишем контекст, в котором можно применять на практике каждую из этих функций.</span><span class="sxs-lookup"><span data-stu-id="4365d-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>