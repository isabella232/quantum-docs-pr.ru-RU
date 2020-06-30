---
title: Обновление Quantum Development Kit (QDK)
description: Описание процесса обновления проектов Q# и Microsoft Quantum Development Kit до текущей версии.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274142"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7a9e2-103">Обновление пакета средств разработки Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7a9e2-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7a9e2-104">Узнайте, как обновить Microsoft Quantum Development Kit (QDK) до новейшей версии.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="7a9e2-105">В этой статье предполагается, что у вас уже установлен пакет QDK.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="7a9e2-106">Если вы устанавливаете его в первый раз, обратитесь к [руководству по установке](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="7a9e2-107">Мы рекомендуем следить за выпуском новых версий QDK.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="7a9e2-108">Следуйте этому руководству по обновлению, чтобы выполнить обновление до последней версии QDK.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="7a9e2-109">Процесс состоит из двух частей:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="7a9e2-110">Обновление имеющихся файлов Q# и проектов для согласования кода с обновленным синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="7a9e2-111">Обновление самого пакета QDK для выбранной среды разработки.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="7a9e2-112">Обновление проектов Q#</span><span class="sxs-lookup"><span data-stu-id="7a9e2-112">Updating Q# Projects</span></span> 

<span data-ttu-id="7a9e2-113">Следуйте этим инструкциям по обновлению проектов Q#, независимо от того, на каком языке написана основная программа для выполнения операций Q#: C# или Python.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="7a9e2-114">Сначала убедитесь, что у вас установлена последняя версия [пакета SDK для .NET Core 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="7a9e2-115">Запустите выполнение следующей команды в командной строке:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="7a9e2-116">Убедитесь, что в результате получена версия `3.1.100` или более новая.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="7a9e2-117">В противном случае установите [последнюю версию](https://dotnet.microsoft.com/download) и повторите проверку снова.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="7a9e2-118">Затем следуйте приведенным ниже инструкциям в зависимости от настроек (в Visual Studio, Visual Studio Code или непосредственно в командной строке).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="7a9e2-119">Обновление проектов Q# в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7a9e2-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="7a9e2-120">Обновите Visual Studio 2019 до последней версии. Инструкции см. [здесь](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="7a9e2-121">Откройте решение в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="7a9e2-122">В меню выберите **Сборка** -> **Очистить решение**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="7a9e2-123">В каждом из CSPROJ-файлов обновите требуемую версию .NET Framework до `netcoreapp3.1` (или `netstandard2.1`, если это проект библиотеки).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="7a9e2-124">То есть измените такого рода строки:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="7a9e2-125">Дополнительные сведения о том, как указать требуемую версию .NET Framework, см. [здесь](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="7a9e2-126">В каждом из CSPROJ-файлов задайте в качестве пакета SDK `Microsoft.Quantum.Sdk`, как показано в строке ниже.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="7a9e2-127">Обратите внимание, что в качестве номера версии следует указать последний доступный. Его можно узнать из [заметок о выпуске](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="7a9e2-128">Сохраните и закройте все файлы в решении.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="7a9e2-129">Выберите **Сервис** -> **Командная строка** -> **Командная строка разработчика**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="7a9e2-130">Кроме того, в Visual Studio можно воспользоваться консолью диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="7a9e2-131">Чтобы **удалить** все пакеты, воспользуйтесь для каждого проекта в решении следующей командой:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="7a9e2-132">Если в проектах используются другие пакеты Microsoft.Quantum или Microsoft.Azure.Quantum (например, Microsoft.Quantum.Numerics), запустите для них выполнение команды **add**, чтобы обновить используемую версию.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="7a9e2-133">Закройте командную строку и выберите **Сборка** -> **Собрать решение** (*не* выбирайте "Пересобрать решение").</span><span class="sxs-lookup"><span data-stu-id="7a9e2-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="7a9e2-134">Теперь вы можете сразу перейти к [обновлению расширения QDK для Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="7a9e2-135">Обновление проектов Q# в Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7a9e2-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="7a9e2-136">В Visual Studio Code откройте папку с проектом, который необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="7a9e2-137">Выберите **Терминал** -> **Создать терминал**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="7a9e2-138">Выполните инструкции по обновлению с помощью командной строки (приведены ниже).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="7a9e2-139">Обновление проектов Q# с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="7a9e2-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="7a9e2-140">Перейдите к папке, содержащей основной файл проекта.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="7a9e2-141">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="7a9e2-142">Определите текущую версию QDK.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="7a9e2-143">Ее можно узнать из [заметок о выпуске](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="7a9e2-144">Формат версии будет аналогичен следующему: `0.11.2006.207`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="7a9e2-145">В каждом из файлов `.csproj` выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="7a9e2-146">Обновите требуемую версию .NET Framework до `netcoreapp3.1` (или `netstandard2.1`, если это проект библиотеки).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="7a9e2-147">То есть измените такого рода строки:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="7a9e2-148">Дополнительные сведения о том, как указать требуемую версию .NET Framework, см. [здесь](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="7a9e2-149">Замените ссылку на пакет SDK в определении проекта.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="7a9e2-150">Убедитесь, что номер версии соответствует значению, определенному на **шаге 3**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="7a9e2-151">Удалите ссылку на пакет `Microsoft.Quantum.Development.Kit` (если таковая имеется). Она будет указана в следующей записи:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="7a9e2-152">Обновите версию всех пакетов Microsoft Quantum до последней выпущенной версии QDK (определяется на **шаге 3**).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="7a9e2-153">Имена этих пакетов соответствуют следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="7a9e2-154">Ссылки на пакеты задаются в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="7a9e2-155">Сохраните обновленный файл.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-155">Save the updated file.</span></span>

    - <span data-ttu-id="7a9e2-156">Восстановите зависимости проекта с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="7a9e2-157">Вернитесь к папке, содержащей основной файл проекта, и воспользуйтесь следующей командой:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="7a9e2-158">После обновления проектов Q# следуйте приведенным ниже инструкциям, чтобы обновить сам пакет QDK.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="7a9e2-159">Обновление пакета QDK</span><span class="sxs-lookup"><span data-stu-id="7a9e2-159">Updating the QDK</span></span>

<span data-ttu-id="7a9e2-160">Процесс обновления QDK зависит от языка и среды разработки.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="7a9e2-161">Выберите среду разработки ниже.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-161">Select your development environment below.</span></span>

* [<span data-ttu-id="7a9e2-162">Python: обновление расширения IQ#</span><span class="sxs-lookup"><span data-stu-id="7a9e2-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="7a9e2-163">Записные книжки Jupyter Notebook: обновление расширения IQ#</span><span class="sxs-lookup"><span data-stu-id="7a9e2-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="7a9e2-164">Visual Studio: обновление расширения QDK</span><span class="sxs-lookup"><span data-stu-id="7a9e2-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="7a9e2-165">VS Code: обновление расширения QDK</span><span class="sxs-lookup"><span data-stu-id="7a9e2-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="7a9e2-166">Командная строка и C#: обновление шаблонов проектов</span><span class="sxs-lookup"><span data-stu-id="7a9e2-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="7a9e2-167">Обновление IQ# для Python</span><span class="sxs-lookup"><span data-stu-id="7a9e2-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="7a9e2-168">Обновите ядро `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="7a9e2-169">Проверьте версию `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7a9e2-170">Вы должны увидеть следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="7a9e2-171">Не волнуйтесь, если версия `iqsharp` выше, она должна быть [новейшей](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="7a9e2-172">Обновите пакет `qsharp`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="7a9e2-173">Проверьте версию `qsharp`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="7a9e2-174">Вы должны увидеть следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="7a9e2-175">Запустите выполнение следующей команды из расположения файлов `.qs`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="7a9e2-176">Теперь вы можете использовать обновленную версию QDK для выполнения имеющихся квантовых программ.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="7a9e2-177">Обновление IQ# для записных книжек Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="7a9e2-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="7a9e2-178">Обновите ядро `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="7a9e2-179">Проверьте версию `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="7a9e2-180">Вывод приложения должен быть аналогичен приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="7a9e2-181">Не волнуйтесь, если версия `iqsharp` выше, она должна быть [новейшей](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="7a9e2-182">Запустите выполнение следующей команды в ячейке Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="7a9e2-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="7a9e2-183">Теперь можно открыть имеющуюся записную книжку Jupyter Notebook и запустить ее выполнение с помощью обновленного пакета QDK.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="7a9e2-184">Обновление расширения QDK для Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7a9e2-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="7a9e2-185">Обновите расширение Q# для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="7a9e2-186">Visual Studio предложит принять обновления [расширения Quantum для Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="7a9e2-187">Примите обновление.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="7a9e2-188">Шаблоны проектов обновляются с помощью расширения.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="7a9e2-189">Обновленные шаблоны применяются только к новым проектам.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="7a9e2-190">При обновлении расширения код имеющихся проектов не обновляется.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="7a9e2-191">Обновление расширения QDK для VS Code</span><span class="sxs-lookup"><span data-stu-id="7a9e2-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="7a9e2-192">Обновите расширение Quantum для VS Code.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="7a9e2-193">Перезапустите VS Code.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-193">Restart VS Code</span></span>
    - <span data-ttu-id="7a9e2-194">Перейдите на вкладку **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="7a9e2-195">Выберите расширение **Microsoft Quantum Development Kit для Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="7a9e2-196">Перезагрузите расширение.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-196">Reload the extension</span></span>

2. <span data-ttu-id="7a9e2-197">Обновите шаблоны проектов Quantum.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="7a9e2-198">Выберите **Представление** -> **Палитра команд**.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="7a9e2-199">Выберите **Q#: Install project templates** (Q#: установить шаблоны проектов).</span><span class="sxs-lookup"><span data-stu-id="7a9e2-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="7a9e2-200">Через несколько секунд должно появиться всплывающее окно с подтверждением успешной установки шаблонов проектов.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="7a9e2-201">C# с использованием программы командной строки `dotnet`</span><span class="sxs-lookup"><span data-stu-id="7a9e2-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="7a9e2-202">Обновите шаблоны проектов Quantum для .NET.</span><span class="sxs-lookup"><span data-stu-id="7a9e2-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```