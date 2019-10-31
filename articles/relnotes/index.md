---
title: Заметки о выпуске предварительной версии Quantum Development Kit
description: Заметки о выпуске предварительной версии Quantum Development Kit
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: 169a8ac31c53f2892624618a227d8bdbdc458458
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "72958885"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Заметки о выпуске Microsoft Quantum Development Kit

Эта статья содержит сведения обо всех выпусках Quantum Development Kit

См. [инструкции по установке](xref:microsoft.quantum.install).

См. [инструкции по обновлению](xref:microsoft.quantum.update).

## <a name="version-0919093002"></a>Версия 0.9.1909.3002

*Дата выпуска: 30 сентября 2019 г.*

Этот выпуск включает следующие обновления:

- Добавлена поддержка завершения кода для Q# в Visual Studio 2019 (версии 16.3 или более поздней) и Visual Studio Code.
- Добавлены ката в [Quantum Katas](https://github.com/Microsoft/QuantumKatas), посвященные квантовым блокам сложения.

См. полный список закрытых запросов на вытягивание для [библиотек](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [компилятора](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [среды выполнения](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [примеров](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) и [ката](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Версия 0.9 (*PackageReference 0.9.1908.2902*)

*Дата выпуска: 29 августа 2019 г.*

Этот выпуск включает следующие обновления:

- Добавлена поддержка [инструкций конъюгации](xref:microsoft.quantum.language.statements#conjugations) в Q#.
- Новые действия с кодом в компиляторе, в том числе"заменить", "добавить документацию" и обновление элементов простого массива.
- Добавлен шаблон установки и новые команды проекта для расширения Visual Studio Code.
- Добавлены новые варианты блока объединения ApplyIf, например [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone).
- Еще несколько ката из [Quantum Katas](https://github.com/Microsoft/QuantumKatas) преобразованы в записные книжки Jupyter.
- Теперь для расширения Visual Studio требуется Visual Studio 201.9

См. полный список закрытых запросов на вытягивание для [библиотек](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [компилятора](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [среды выполнения](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [примеров](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) и [ката](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Здесь перечислены эти изменения вместе с инструкциями по обновлению существующих программ.  См. об этих изменениях в [блоге для разработчиков Q#](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Версия 0.8 (*PackageReference 0.8.1907.1701*)

*Дата выпуска: 12 июля 2019 г.*

Этот выпуск включает следующие обновления:

- Добавлены расположения индексирования для массивов срезов (см. сведения в [справочнике по языку программирования](xref:microsoft.quantum.language.expressions#array-slices)).
- Добавлены файлы Dockerfile, размещенные в [Реестре контейнеров Майкрософт](https://github.com/microsoft/ContainerRegistry) (см. сведения в [репозитории IQ#](https://github.com/microsoft/iqsharp/blob/master/README.md)).
- Критическое изменение в [симуляторе трассировки](xref:microsoft.quantum.machines.qc-trace-simulator.intro); изменены параметры конфигурации и имена (см. сведения о [средстве просмотра API .NET](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)).

См. полный список закрытых запросов на вытягивание для [библиотек](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) и [примеров](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Версия 0.7 (*PackageReference 0.7.1905.3109*)

*Дата выпуска: 31 мая 2019 г.*

Этот выпуск включает следующие обновления:
- Дополнения к языку Q#. 
- Обновления библиотеки для химической отрасли. 
- Новая библиотека числовых значений.

См. полный список закрытых запросов на вытягивание для [библиотек](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) и [примеров](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Здесь перечислены эти изменения вместе с инструкциями по обновлению существующих программ.  См. об этих изменениях в [блоге для разработчиков Q#](https://devblogs.microsoft.com/qsharp).

### <a name="q-language-syntax"></a>Синтаксис языка Q#
В этом выпуске добавлен новый синтаксис языка Q#.
* Добавлены именованные элементы для [определяемых пользователем типов](xref:microsoft.quantum.language.type-model#user-defined-types).  
* Теперь конструкторы определяемых пользователем типов можно использовать в качестве функций.
* Добавлена поддержка операций [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) и [apply-and-reassign]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) для определяемых пользователем типов.
* Блок исправления для циклов [repeat-until-success](xref:microsoft.quantum.language.statements#repeat-until-success-loop) теперь необязателен.
* Теперь мы поддерживаем циклы while в функциях (но не операциях).

### <a name="library"></a>Библиотека 

В этом выпуске добавлена библиотека числовых значений. Узнайте о том, как [использовать новую библиотеку числовых значений](xref:microsoft.quantum.numerics.usage) и испытайте [новые примеры](https://github.com/microsoft/quantum/tree/master/Numerics).  [PR №102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

В этом выпуске переработана, расширена и обновлена библиотека для химической отрасли.
* Улучшена модульность компонентов, расширяемость, а также в целом очищен код.  [PR №58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Добавлена поддержка [волновых функций с несколькими опорными сигналами](xref:microsoft.quantum.chemistry.concepts.multireference), в том числе разреженных волновых функций с несколькими опорными сигналами и единых связанных кластеров.  [PR №110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* Благодарим участника [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)). Оценка энергопотребления с использованием вариативного подхода. [PR №120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Обновлена схема [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) до новой [версии 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), которая добавляет спецификацию единого связанного кластера. [Проблема №65](https://github.com/microsoft/QuantumLibraries/issues/65)
* Добавлена возможность взаимодействия Python с функциями из библиотеки для химической отрасли. Опробуйте [этот пример](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Проблема №53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR №110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Версия 0.6.1905

*Дата выпуска: 3 мая 2019 г.*

Этот выпуск включает следующие обновления:
- Внесены изменения в язык Q#. 
- Реструктуризированы библиотеки для Quantum Development Kit. 
- Добавлены примеры. 
- Исправлены ошибки.  Закрыты несколько запросов на вытягивание для [библиотек](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) и [примеров](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Здесь перечислены эти изменения вместе с инструкциями по обновлению существующих программ.  См. сведения об этих изменениях на странице devblogs.microsoft.com/qsharp.

### <a name="q-language-syntax"></a>Синтаксис языка Q#
В этом выпуске добавлен новый синтаксис языка Q#.
* Добавлен [краткий способ для выражения специализации квантовых операций](xref:microsoft.quantum.language.type-model#functors) (control и adjoints) с помощью операторов `+`.  Старый синтаксис объявлен устаревшим.  Программы, в которых используется старый синтаксис (например, `: adjoint`), по-прежнему будут работать, но при их компиляции будет создаваться предупреждение.  
* Добавлен новый оператор `w/` для операции [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions), который позволяет выразить создание массива как изменение существующего массива.
* Добавлена общая инструкция [apply-and-upate](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols), например `+=` и `w/=`.
* Добавлен способ указать короткое имя для пространств имен в директивах [open](xref:microsoft.quantum.language.file-structure#open-directives).

Начиная с этого выпуска, не допускается указание элемента массива в левой части инструкции set.  Это связано с тем, что такой синтаксис подразумевает изменяемость массивов, тогда как в результате этой операции всегда создавался новый массив с изменением.  Теперь будет создаваться ошибка компилятора с предложением применить новый оператор copy-and-update `w/`, который возвращает такой же результат.  

### <a name="library-restructuring"></a>Реструктуризация библиотек
В этом выпуске библиотеки реорганизованы так, чтобы они развивались единообразно:
* Пространство имен Microsoft.Quantum.Primitive переименовано в Microsoft.Quantum.Intrinsic.  Эти операции реализуются на целевом компьютере.  Пространство имен Microsoft.Quantum.Primitive объявлено устаревшим.  Предупреждение среды выполнения будет информировать о вызове в программах операций и функций с устаревшими именами.

* Пакет Microsoft.Quantum.Canon переименован в Microsoft.Quantum.Standard.  Этот пакет содержит пространства имен, которые обычно используются в большинстве программ Q#.  А именно:  
    - Microsoft.Quantum.Canon для типичных операций;
    - Microsoft.Quantum.Arithmetic для арифметических операций общего назначения;
    - Microsoft.Quantum.Preparation для операций подготовки состояния кубитов;
    - Microsoft.Quantum.Simulation для функций моделирования.

После этого изменения могут возникать ошибки компиляции для программ, которые используют один оператор open для пространства имен Microsoft.Quatum.Canon и вызывают операции, которые перемещены в три новых пространства имен.  Самый простой способ устранить такую проблему — добавить инструкции open для трех новых пространств имен.  

* Несколько пространств имен объявлены устаревшими, так как операции из них перемещены в другие пространства имен. Программы, которые используют эти пространства имен, будут по-прежнему работать, а предупреждение времени компиляции будет сообщать, в каком пространстве имен определена соответствующая операция.  

* Пространство имен Microsoft.Quantum.Arithmetic нормализовано для использования определяемого пользователем типа <xref:microsoft.quantum.arithmetic.littleendian>. Используйте функцию [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian), если нужно преобразовать значение в прямой порядок байтов.  

* Имена нескольких вызываемых сущностей (функций и операций) изменены в соответствии с [руководством по стилю Q#](xref:microsoft.quantum.contributing.style).  Старые имена этих сущностей объявлены устаревшими.  Программы, в которых используются старые сущности, будут работать с предупреждением времени компиляции. 

### <a name="new-samples"></a>Новые примеры

Мы добавили [пример использования Q# с драйвером F#](https://github.com/Microsoft/Quantum/pull/164).  

**Благодарим** следующего участника открытой базы кода на http://github.com/Microsoft/Quantum. Эти вклады стали важным дополнением к богатому набору примеров кода Q#:

* Матиас Соекен (Mathias Soeken, [@msoeken](https://github.com/msoeken)). Синтез функций Oracle. [PR №135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Миграция существующих проектов в 0.6.1905.

Для обновления Quantum Development Kit воспользуйтесь [руководством по установке](xref:microsoft.quantum.install).
  
Если у вас есть проекты Q#, созданные в Quantum Development Kit версии 0.5, выполните следующие действия для переноса этих проектов в свежую версию.

    1. Проекты необходимо обновлять по порядку.  Если у вас есть решение с несколькими проектами, обновляйте их в том порядке, в котором они указываются.
    2. В командной строке запустите `dotnet clean`, чтобы удалить все существующие двоичные файлы и промежуточные данные.
    3. В текстовом редакторе измените CSPROJ-файл, указав для всех упоминаний Microsoft.Quantum `PackageReference` версию 0.6.1904, а имя пакета Microsoft.Quantum.Canon измените на Microsoft.Quantum.Standard, как показано ниже:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. В командной строке выполните команду `dotnet msbuild`.  
    5. После этого действия может потребоваться вручную устранить ошибки, возникающие из-за перечисленных выше изменений.  Во многих случаях сообщения об этих ошибках будут возвращаться системой IntelliSense в Visual Studio или Visual Studio Code.
        - Откройте корневую папку проекта или решения в Visual Studio 2019 либо Visual Studio Code.
        - Открыв в редакторе QS-файл, вы увидите выходные данные расширения языка Q# в окне вывода.
        - После успешной загрузки проекта (отображается в окне вывода) откройте каждый файл и вручную устраните все сохранившиеся проблемы.

> [!NOTE]
> * В выпуске 0.6 языковой сервер из пакета Quantum Development Kit не поддерживает несколько рабочих областей.
> * Чтобы работать с проектом в Visual Studio Code, откройте корневую папку с самим проектом и всеми проектами, на которые он ссылается.   
> * Для работы с решением в Visual Studio все проекты, включенные в решение, нужно разместить в той же папке, что и решение, или в одной из вложенных в нее папок.  
> * Ссылки между проектами, перенесенными на версию 0.6 и более поздние версии из старых версий пакета, **не поддерживаются**.

## <a name="version-051904"></a>Версия 0.5.1904

*Дата выпуска: 15 апреля 2019 г.*

Этот выпуск содержит исправления ошибок.


## <a name="version-051903"></a>Версия 0.5.1903

*Дата выпуска: 27 марта 2019 г.*

Этот выпуск включает следующие обновления:

- Добавлена поддержка Jupyter Notebook, что позволяет изучать Q#.  [Ознакомьтесь с новыми примерами для Jupyter Notebook и узнайте, как создавать собственные записные книжки](xref:microsoft.quantum.install). 

- Добавлена арифметика целочисленного сложения в библиотеку Quantum Canon.  См. сведения в записной книжке Jupyter, где [описано применение нового блока целочисленного сложения](https://github.com/Microsoft/Quantum/blob/master/Samples/src/Arithmetic/Adder%20Example.ipynb).

- Исправлена ошибка, приводящая к проблеме с DumpRegister, о которой сообщило сообщество ([#148](https://github.com/Microsoft/Quantum/issues/148)).

- Добавлена возможность возврата из [оператора using](xref:microsoft.quantum.language.statements).

- Переработано [руководство по началу работы](xref:microsoft.quantum.install).


## <a name="version-051902"></a>Версия 0.5.1902

*Дата выпуска: 27 февраля 2019 г.*

Этот выпуск включает следующие обновления:

- Добавлена поддержка кросс-платформенного узла Python.  Пакет `qsharp` для Python позволяет легко имитировать операции и функции Q# в Python. См. сведения о [взаимодействии с Python](xref:microsoft.quantum.install). 

- Расширения Visual Studio и Visual Studio Code теперь поддерживают переименование символов (например, функций и операций).

- Теперь расширение Visual Studio можно установить в Visual Studio 2019.

## <a name="version-041901"></a>Версия 0.4.1901

*Дата выпуска: 30 января 2019 г.*

Этот выпуск включает следующие обновления:

- Добавлена поддержка нового примитивного типа BigInt, который представляет целое число со знаком произвольного размера.  См. сведения о [типе BigInt](xref:microsoft.quantum.language.type-model).
- Добавлен новый специализированный симулятор Тоффоли, который может имитировать квантовые операции X, CNOT и X с несколькими элементами управления для очень большого числа кубитов.  См. сведения о [симуляторе Тоффоли](xref:microsoft.quantum.machines.toffoli-simulator).
- Добавлен простой оценщик ресурсов, который оценивает потребность в ресурсах для выполнения определенного экземпляра операции Q# на квантовом компьютере.  См. сведения об [оценщике ресурсов](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Версия 0.3.1811.2802

*Дата выпуска: 28 ноября 2018 г.*

Наше расширение VS Code было помечено и удалено из Marketplace при [очистке расширений](https://code.visualstudio.com/blogs/2018/11/26/event-stream), связанных с пакетом NPM `event-stream`, хотя оно и не использовало этот пакет. В этой версии удалены все зависимости среды выполнения, которые могут привести к срабатыванию любых систем защиты.

Если вы ранее установили расширение, его придется установить его еще раз, посетив страницу расширения [Microsoft Quantum Development Kit для Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) на сайте Visual Studio Marketplace и нажав кнопку "Установить". Приносим извинения за причиненные неудобства.


## <a name="version-0318111511"></a>Версия 0.3.1811.1511

*Дата выпуска: 20 ноября 2018 г.*

В этом выпуске исправлена ошибка, которая мешала некоторым пользователям успешно загружать расширение Visual Studio.

Если вы обновляете Quantum Development Kit с версии 0.2, см. сведения об [изменениях в языке Q# и миграции программ Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-031811203"></a>Версия 0.3.1811.203

*Дата выпуска: 2 ноября 2018 г.*

Этот выпуск включает несколько исправлений ошибок, в том числе следующие:

* Вызов `DumpMachine` в некоторых случаях мог изменять состояние симулятора.
* Удалены предупреждения времени компиляции, возникавшие при сборке проектов в .NET Core версии ниже 2.1.403.
* Очищена документация, в частности убраны всплывающие подсказки от наведения курсора мыши в Visual Studio Code и Visual Studio.

Если вы обновляете Quantum Development Kit с версии 0.2, см. сведения об [изменениях в языке Q# и миграции программ Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-0318102508"></a>Версия 0.3.1810.2508

*Дата выпуска: 29 октября 2018 г.*

В этот выпуск включены новые функции языка и улучшенный интерфейс для разработчиков:

* Этот выпуск включает языковой сервер для Q# и поддерживает интеграцию клиентов для Visual Studio и Visual Studio Code. Это позволяет использовать дополнительный набор функций IntelliSense, а также получать в реальном времени обратную связь по вводимому коду в виде волнистых линий, подчеркивающих ошибки и предупреждения. 
* В этом обновлении в целом значительно улучшены диагностические сообщения, упрощена навигация и указание диапазонов для диагностических и других сведений во всплывающих подсказках.
* Язык Q# расширен так, чтобы разработчики смогли более согласованно выполнять распространенные операции, а дополнения функций языка позволяют еще эффективнее выражать квантовые вычисления.  В этом выпуске внесено несколько критических изменений языка Q#.   

См. сведения об [изменениях языка Q# и миграции программ Q#](xref:microsoft.quantum.relnotes.migration-0-3).

В этот выпуск также входит новая квантовая библиотека для химической отрасли.

* Библиотека для химической отрасли содержит новые гамильтоновы функции моделирования, в том числе следующие.
    - Интеграторы Троттера-Сузуки для произвольного четного порядка, позволяющие повысить точность моделирования.
    - Методика моделирования кубитизации с оптимизацией для химических вычислений, позволяющая снизить сложность вентилей $T$.
* Добавлена новая схема с открытым исходным кодом — схема Брумбриджа (с отсылкой на [расположение](https://en.wikipedia.org/wiki/Broom_Bridge), знаменитое как место открытия гамильтоновых функций), предназначенная для импорта представлений молекул и их моделирования.
* Определено несколько химических представлений с использованием новой схемы Брумбриджа.  Эти модели были созданы с помощью высокопроизводительного средства для химических вычислений [NWChem](http://www.nwchem-sw.org/) с открытым исходным кодом.
* В руководствах и примерах описывается, как с помощью библиотеки для химии и моделей данных по схеме Брумбриджа выполнять следующие действия:
    - Создание простых гамильтоновых функций на основе библиотеки для химической отрасли.
    - Визуализация базового и возбужденного энергетических состояний гидрида лития на основе фазовой оценки.
    - Выполнение оценки ресурсов для квантового моделирования химических процессов.
    - Оценка энергетических уровней для молекул, представленных в формате схемы Брумбриджа.
* В документации описано, как использовать NWChem для создания других химических моделей для квантового моделирования на языке Q#.

См. сведения о [библиотеке для химической отрасли, входящей в Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

С появлением новой библиотеки для химической отрасли мы вынесли библиотеки в отдельный новый репозиторий [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) на сайте GitHub.  Примеры остаются в репозитории [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Мы будем рады вашим вкладам в разработку всех решений!

Этот выпуск включает исправления ошибок и функции для решения проблем, о которых сообщило сообщество:

* IntelliSense для Q#? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* QS-файлы ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Улучшение сообщений об ошибках для ситуации, когда фигурные скобки сокращаются в операторе if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Поддержка деконструирования кортежа в изменяемой (повторной) привязке ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Ошибка при выполнении предоставленной операции BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* H2SimulationGUI иногда отображает большие пиковые значения ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Вклады членов сообщества

**Благодарим** следующих участников открытой базы кода на http://github.com/Microsoft/Quantum. Эти вклады стали важным дополнением к богатому набору примеров кода Q#:

* Рольф Хуисман (Rolf Huisman, [@RolfHuisman](https://github.com/RolfHuisman)): Упрощена работа разработчиков на QASM и Q# благодаря созданию транслятора из QASM в Q#. [PR №58](https://github.com/Microsoft/Quantum/pull/58).

* Эндрю Хелвер (Andrew Helwer, [@ahelwer](https://github.com/ahelwer)):  Добавлен пример с реализацией квантовой игры CHSH, в которой используется свойство нелокальности.  [PR №84](https://github.com/Microsoft/Quantum/pull/84).

Также выражаем благодарность следующим участникам: Рохит Гупта (Rohit Gupta, [@guptarohit](https://github.com/guptarohit),[PR №90](https://github.com/Microsoft/quantum/pull/90)), Танака Такайоши (Tanaka Takayoshi, [@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR №289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), Ли Джеймс Ориордан (Lee James O'Riordan, [@mlxd](https://github.com/mlxd),[PR №96](https://github.com/Microsoft/Quantum/pull/96)) за вклад в улучшение содержимого документации, исправления ошибок и опечаток! 

## <a name="version-021809701"></a>Версия 0.2.1809.701

*Дата выпуска: 10 сентября 2018 г.*

Этот выпуск включает исправления ошибок для решения проблем, о которых сообщило сообщество. Сюда входит следующее.

* Не удается использовать оператор сдвига ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* Сбой в `DumpMachine` / `DumpRegister` в `QCTraceSimulator` при печати в консоль ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Допускается выделение 0 кубитов ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` требует явного вызова Complex() ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* Операция `Measure` всегда возвращает `One` в macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Спасибо! 

## <a name="version-0218063001"></a>Версия 0.2.1806.3001

*Дата выпуска: 30 июня 2018 г.*

Этот выпуск включает только быстрое исправление для [проблемы #48, опубликованной на GitHub](https://github.com/Microsoft/Quantum/issues/48) (Компиляция Q# завершается ошибкой, если имя пользователя содержит пробел). Выполните те же инструкции по обновлению, что и для `0.2.1806.1503`, используя новую версию (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Версия 0.2.1806.1503

*Дата выпуска: 22 июня 2018 г.*

Этот выпуск включает несколько вкладов сообщества, а также улучшенные возможности для отладки и оптимизации производительности.  В частности:

* Повышение производительности моделирования разного масштаба на целевом компьютере QuantumSimulator.
* Усовершенствованы функции отладки.
* Вклады сообщества в виде исправлений ошибок, новых вспомогательных функций, операций и примеров.

### <a name="performance-improvements"></a>Повышение производительности.

Это обновление включает значительные улучшения производительности для моделирования большого и малого количества кубитов на всех целевых компьютерах.  Это улучшение хорошо заметно в моделировании H<sub>2</sub>, стандартном примере из Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Усовершенствованы функции отладки.

В этом обновлении добавлены новые функции отладки:
* Добавлены две новые операции @"microsoft.quantum.extensions.diagnostics.dumpmachine" и @"microsoft.quantum.extensions.diagnostics.dumpregister", которые выводят в виде волновой функции сведения о целевом квантовом компьютере на определенный момент времени.  
* В Visual Studio теперь для целевого компьютера QuantumSimulator в окне отладки автоматически отображается вероятность измерения $\ket{1}$ для одного кубита.
* В Visual Studio улучшено отображение свойств переменных в окнах отладки **Видимые** и **Локальные**. 

См. сведения о [тестировании и отладке](xref:microsoft.quantum.techniques.testing-and-debugging).

### <a name="community-contributions"></a>Вклады членов сообщества

Сообщество программистов Q# постоянно растет и мы очень рады получить первые библиотеки и примеры, предоставленные пользователями через нашу открытую базу кода на сайте http://github.com/Microsoft/quantum.  **Огромная благодарность** следующим участникам:
* Матиас Соекен (Mathias Soeken, [@msoeken](https://github.com/msoeken)): предоставил пример, который определяет метод синтеза логики на основе преобразования и конструирует сети Тоффоли для реализации заданной перестановки. В коде используются только функции и операции Q#.  [PR №41](https://github.com/Microsoft/Quantum/pull/41).
* Рольф Хуисман (Rolf Huisman, [@RolfHuisman](https://github.com/RolfHuisman)): партнер Microsoft MVP Рольф Хуисман предоставил пример, который создает плоский код QASM на основе кода Q# для ограниченного класса программ, которые не используют классический поток управления, и ограниченного числа квантовых операций. [PR №59](https://github.com/Microsoft/Quantum/pull/59)
* Сара Касиер (Sarah Kasier, [@crazy4pi314](https://github.com/crazy4pi314)): помогла улучшить базу кода, предоставив библиотечную функцию для контролируемых операций. [PR №53](https://github.com/Microsoft/Quantum/pull/53)
* Джессика Лемье (Jessica Lemieux, [@Lemj3111](https://github.com/Lemj3111)): исправила @"microsoft.quantum.canon.quantumphaseestimation" и создала новые модульные тесты.  [PR №54](https://github.com/Microsoft/Quantum/pull/54)
* Тама Макглинн (Tama McGlinn, [@TamaHobbit](https://github.com/TamaHobbit)): очистка кода в примере Teleportation путем удаления экземпляра QuantumSimulator. [PR №20](https://github.com/Microsoft/Quantum/pull/20)

Кроме того, **огромная благодарность** следующим инженерам программного обеспечения Майкрософт из группы коммерческих инженерных служб, которые внесли значительные изменения в нашу документацию на очередном хакатоне.  Их изменения значительно улучшили удобство чтения и понимания для всех нас:
* Саша Корти (Sascha Corti)
* Михаэла Курмеи (Mihaela Curmei)
* Джон Доннелли (John Donnelly)
* Кирилл Логачев (Kirill Logachev)
* Ян Поспишил (Jan Pospisil)
* Анита Раманан (Anita Ramanan)
* Френсис Тиббл (Frances Tibble)
* Алессандро Воцца (Alessandro Vozza)

### <a name="update-existing-projects"></a>Обновление существующих проектов

Этот выпуск сохраняет полную обратную совместимость. Просто обновите пакеты NuGet в ваших проектах до версии `0.2.1806.1503-preview` и выполните **полное перестроение**, чтобы восстановить все промежуточные файлы.

Для Visual Studio выполните обычные инструкции по [обновлению пакета](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Чтобы обновить шаблоны проекта из командной строки, выполните следующую команду:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

После выполнения этой команды все новые проекты, созданные в `dotnet new <project-type> -lang Q#`, будут автоматически использовать новую версию Quantum Development Kit.

Чтобы обновить существующий проект для использования последней версии, выполните следующую команду в каталоге каждого проекта:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Если существующий проект также использует интеграцию с XUnit для модульного тестирования, аналогичная команда позволит обновить и этот пакет:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

В зависимости от используемой в тестовом проекте версии XUnit может потребоваться еще и обновление XUnit до версии 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

После этого обновления не забудьте удалить все временные файлы, которые были созданы предыдущей версией, выполнив следующие действия:
```
dotnet clean 
```

### <a name="known-issues"></a>Известные проблемы

Не появилось известных проблем для отчета.


## <a name="version-0218022202"></a>Версия 0.2.1802.2202

*Дата выпуска: 26 февраля 2018 г.*

В этом выпуске добавлена поддержка разработки на других платформах, улучшены взаимодействие языков и производительность. В частности:

- Добавлена поддержка разработки на платформах macOS и Linux. 
- Добавлена совместимость с .NET Core, включая поддержку Visual Studio Code на разных платформах.
- Добавлена полная лицензия с открытым кодом для библиотек Quantum Development Kit.
- Улучшена производительность моделирования в проектах с 20 и более кубитами.
- Добавлено взаимодействие с языком Python (предварительная версия доступна в ОС Windows).

### <a name="net-editions"></a>Выпуски .NET

Платформа .NET доступна в двух разных выпусках: .NET Framework поставляется вместе с Windows, а .NET Core с открытым кодом доступна для установки на Windows, macOS и Linux.
В этом выпуске большая часть пакета Quantum Development Kit предоставляется в виде библиотек для .NET Standard. Этот набор классов является общим для выпусков Framework и Core.
Это означает, что библиотеки совместимы с последними версиями как .NET Framework, так и .NET Core.

Чтобы обеспечить максимальную переносимость проектов, созданных с помощью Quantum Development Kit, мы рекомендуем нацеливать проекты библиотек, написанные с помощью Quantum Development Kit, на .NET Standard, а консольные приложения — на .NET Core.
Так как предыдущие выпуски Quantum Development Kit поддерживали только .NET Framework, может потребоваться миграция существующих проектов. Ниже описано, как ее выполнить.

### <a name="project-migration"></a>Миграция проекта

Проекты, созданные на основе предыдущих версий Quantum Development Kit, будут и далее работать, пока вы не обновите используемые в них пакеты NuGet. Чтобы перенести существующий код на новую версию, выполните следующие шаги.
1. Создайте новый проект .NET Core, используя правильный вариант шаблона проекта Q# (приложение, библиотека или тестовый проект).
2. Скопируйте все существующие файлы с расширением .qs, .cs и .fs из старого проекта в новый, щелкнув "Добавить" > "Существующий элемент". Не копируйте файл AssemblyInfo.cs.
3. Скомпилируйте и запустите новый проект.

Обратите внимание, что операция RandomWalkPhaseEstimation из пространства имен Microsoft.Quantum.Canon была перемещена в пространство имен Microsoft.Research.Quantum.RandomWalkPhaseEstimation в репозитории [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Известные проблемы

- Параметр `--filter` для `dotnet test` работает неправильно для тестов, написанных на Q#.
  Это означает, что в Visual Studio Code невозможно выполнять модульные тесты по отдельности. Мы рекомендуем выполнить в командной строке команду `dotnet test`, чтобы запустить все тесты сразу.

## <a name="version-0118011707"></a>Версия 0.1.1801.1707

*Дата выпуска: 18 января 2018 г.*

Этот выпуск исправляет несколько ошибок, о которых сообщило сообщество. А именно:

- Симулятор теперь работает с ранними процессорами, не поддерживающими AVX.
- Региональные настройки для десятичных чисел теперь не приводят к сбою синтаксического анализатора Q#.
- Операция примитива `SignD` теперь возвращает `Int`, а не `Double`.


## <a name="version-011712901"></a>Версия 0.1.1712.901

*Дата выпуска: 11 декабря 2017 г.*

### <a name="known-issues"></a>Известные проблемы

#### <a name="hardware-and-software-requirements"></a>Требования к аппаратному и программному обеспечению

- Для работы симулятора из комплекта поставки Quantum Development Kit требуется 64-разрядная версия Microsoft Windows.
- Квантовый симулятор Майкрософт, который устанавливается вместе с Quantum Development Kit, использует технологию AVX (Advance Vector Extensions) и работает только на ЦП с поддержкой AVX. Технологию AVX поддерживают все процессоры Intel, выпущенные в 1-м квартале 2011 г. (Sandy Bridge) или позднее. Мы рассматриваем возможность добавить поддержку более ранних процессоров, о чем будет сообщено позднее.

#### <a name="project-creation"></a>Создание проекта

- При создании решения (SLN-файла), в котором будет использоваться Q#, это решение нужно размещать на один каталог выше в иерархии, чем каждый из входящих в него проектов (CSPROJ-файлы). Чтобы обеспечить такую конфигурацию при создании нового решения, установите флажок "Создать каталог для решения" в диалоговом окне "Создание проекта". В противном случае потребуется вручную устанавливать пакеты NuGet для Quantum Development Kit.

#### <a name="q"></a>Q#

- IntelliSense неправильно отображает ошибки для кода на Q#. Чтобы получить правильные сведения об ошибках, обязательно включите отображение ошибок сборки в списке ошибок Visual Studio. Также учтите, что ошибки Q# не отображаются до выполнения сборки.
- Использование изменяемого массива в частичном приложении может привести к непредвиденному поведению.
- Привязка неизменяемого массива к изменяемому массиву (let a = b, где b является изменяемым массивом) может привести к непредвиденному поведению.
- Подключаемые модули VS для профилирования, объема протестированного кода и некоторые другие могут не всегда точно отображать количество строк и блоков Q#.
- Компилятор Q # не проверяет интерполированные строки. Ошибки в именах переменных или выражения в интерполированных строках Q# могут привести к ошибкам компиляции С#.

#### <a name="simulation"></a>Моделирование

- Quantum Simulator использует OpenMP для параллелизации необходимой линейной алгебры. По умолчанию OpenMP использует все доступные аппаратные потоки, что приводит к медленному выполнению программ с небольшим количеством кубитов, так как затраты на координацию потоков превышают фактический объем работы. Это можно исправить, задав для переменной среды OMP_NUM_THREADS небольшое число. Для грубого приближения можно считать, что 1-го потока достаточно примерно для 4-х кубитов, а сверх этого добавляйте по одному потоку на кубит. Впрочем, реальные показатели сильно зависят от конкретного алгоритма.

#### <a name="debugging"></a>Отладка

- F11 (шаг с заходом) не работает в коде Q#.
- Подсветка кода Q# может быть неточной при срабатывании точки останова и в режиме паузы при пошаговом выполнении. Строка будет выделена правильно, но позиции начала и завершения подсветки в строке могут оказаться неверными.

#### <a name="testing"></a>Тестирование

- Тесты должны выполняться в 64-разрядном режиме. Если тесты завершаются сбоем с исключением BadImageFormatException, перейдите в меню "Тест" и выберите элементы "Параметры теста" > "Архитектура процессора по умолчанию" > X64.
- Выполнение некоторых тестов занимает много времени (иногда до 5 минут, в зависимости от характеристик компьютера). Это вполне нормально, так как в некоторых из них используется более двадцати кубитов. В самом масштабном тесте на данный момент выполняется 23 кубита.

#### <a name="samples"></a>Примеры

- На некоторых компьютерах небольшие примеры могут выполняться медленно, если переменной среды OMP_NUM_THREADS не присвоено значение 1. Подробнее см. примечание о выпуске в разделе "Моделирование".

#### <a name="libraries"></a>Библиотеки

- Существует неявное предположение, что кубиты являются разными, если они передаются в операцию в разных аргументах. Например, все библиотечные операции (и все симуляторы) предполагают, что в контролируемую операцию NOT всегда передаются два разных кубита. Нарушение этого условия может привести к непредсказуемым последствиям. Для проверки можно использовать моделирование трассировки квантового компьютера.
- Функция Microsoft.Quantum.Bind может не во всех случаях действовать должным образом.
- В пространстве имен Microsoft.Quantum.Extensions.Math функция SignD возвращает значение с типом Double вместо Int, хотя базовая функция System.Math.Sign всегда возвращает целое число. Вполне допустимо сравнивать полученный результат со значениями 1,0, -1,0 и 0,0, так как все эти значения Double имеют точные двоичные представления.