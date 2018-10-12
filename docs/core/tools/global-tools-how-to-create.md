---
title: Создание глобального средства .NET Core
description: Сведения о том, как создать глобальное средство. Глобальное средство — это консольное приложение, которое устанавливается с помощью интерфейса командной строки .NET Core.
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 3860aad5e2c13714298d50bb9ac10daec3aadf01
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47231225"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="4df8f-104">Создание глобального средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="4df8f-104">Create a .NET Core Global Tool using the .NET Core CLI</span></span>

<span data-ttu-id="4df8f-105">В этой статье объясняется, как создать и упаковать глобальное средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4df8f-105">This article teaches you how to create and package a .NET Core Global Tool.</span></span> <span data-ttu-id="4df8f-106">Интерфейс командной строки .NET Core позволяет создавать консольное приложение в качестве глобального средства, которое смогут установить и запустить другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="4df8f-106">The .NET Core CLI allows you to create a console application as a Global Tool, which others can easily install and run.</span></span> <span data-ttu-id="4df8f-107">Глобальные средства .NET Core представляют собой пакеты NuGet, которые устанавливаются из командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4df8f-107">.NET Core Global Tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="4df8f-108">См. дополнительные сведения о [глобальных средствах .NET Core][global-tool-info].</span><span class="sxs-lookup"><span data-stu-id="4df8f-108">For more information about Global Tools, see [.NET Core Global Tools overview][global-tool-info].</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a><span data-ttu-id="4df8f-109">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4df8f-109">Create a project</span></span>

<span data-ttu-id="4df8f-110">В этой статье для создания и управления проектом используется .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="4df8f-110">This article uses the .NET Core CLI to create and manage a project.</span></span>

<span data-ttu-id="4df8f-111">Наш пример средства будет содержать консольное приложение, которое позволяет создать текстовый бот и выводит сообщение.</span><span class="sxs-lookup"><span data-stu-id="4df8f-111">Our example tool will be a console application that generates an ASCII bot and prints a message.</span></span> <span data-ttu-id="4df8f-112">Сначала создайте консольное приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4df8f-112">First, create a new .NET Core Console Application.</span></span>

```console
dotnet new console -o botsay
```

<span data-ttu-id="4df8f-113">Перейдите к каталогу `botsay`, который вы создали с помощью предыдущей команды.</span><span class="sxs-lookup"><span data-stu-id="4df8f-113">Navigate to the `botsay` directory created by the previous command.</span></span>

## <a name="add-the-code"></a><span data-ttu-id="4df8f-114">Добавление кода</span><span class="sxs-lookup"><span data-stu-id="4df8f-114">Add the code</span></span>

<span data-ttu-id="4df8f-115">Откройте файл `Program.cs` в любом текстовом редакторе, например `vim` или [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="4df8f-115">Open the `Program.cs` file with your favorite text editor, such as `vim` or [Visual Studio Code](https://code.visualstudio.com/).</span></span>

<span data-ttu-id="4df8f-116">Добавьте в начало файла приведенную ниже директиву `using`, которая помогает сократить код отображения сведений о версии приложения.</span><span class="sxs-lookup"><span data-stu-id="4df8f-116">Add the following `using` directive to the top of the file, this helps shorten the code to display the version information of the application.</span></span>

```csharp
using System.Reflection;
```

<span data-ttu-id="4df8f-117">Затем перейдите вниз к методу `Main`.</span><span class="sxs-lookup"><span data-stu-id="4df8f-117">Next, move down to the `Main` method.</span></span> <span data-ttu-id="4df8f-118">Замените этот метод приведенным ниже кодом, который будет обрабатывать аргументы командной строки для приложения.</span><span class="sxs-lookup"><span data-stu-id="4df8f-118">Replace the method with the following code to process the command-line arguments for your application.</span></span> <span data-ttu-id="4df8f-119">Если аргументы не переданы, отображается короткое справочное сообщение.</span><span class="sxs-lookup"><span data-stu-id="4df8f-119">If no arguments were passed, a short help message is displayed.</span></span> <span data-ttu-id="4df8f-120">В противном случае все полученные аргументы преобразуются в строку и передаются на выход бота.</span><span class="sxs-lookup"><span data-stu-id="4df8f-120">Otherwise, all of those arguments are transformed into a string and printed with the bot.</span></span>

```csharp
static void Main(string[] args)
{
    if (args.Length == 0)
    {
        var versionString = Assembly.GetEntryAssembly()
                                .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                .InformationalVersion
                                .ToString();
                                
        Console.WriteLine($"botsay v{versionString}");
        Console.WriteLine("-------------");
        Console.WriteLine("\nUsage:");
        Console.WriteLine("  botsay <message>");
        return;
    }

    ShowBot(string.Join(' ', args));
}
```

### <a name="create-the-bot"></a><span data-ttu-id="4df8f-121">Создание бота</span><span class="sxs-lookup"><span data-stu-id="4df8f-121">Create the bot</span></span>

<span data-ttu-id="4df8f-122">Теперь добавьте новый метод с именем `ShowBot`, который принимает один строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="4df8f-122">Next, add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="4df8f-123">Этот метод позволяет вывести сообщение и бот ASCII.</span><span class="sxs-lookup"><span data-stu-id="4df8f-123">This method prints out the message and the ASCII bot.</span></span> <span data-ttu-id="4df8f-124">Код текстового бота взят из примера [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs).</span><span class="sxs-lookup"><span data-stu-id="4df8f-124">The ASCII bot code was taken from the [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) sample.</span></span>

```csharp
static void ShowBot(string message)
{
    string bot = $"\n        {message}";
    bot += @"
    __________________
                      \
                       \
                          ....
                          ....'
                           ....
                        ..........
                    .............'..'..
                 ................'..'.....
               .......'..........'..'..'....
              ........'..........'..'..'.....
             .'....'..'..........'..'.......'.
             .'..................'...   ......
             .  ......'.........         .....
             .    _            __        ......
            ..    #            ##        ......
           ....       .                 .......
           ......  .......          ............
            ................  ......................
            ........................'................
           ......................'..'......    .......
        .........................'..'.....       .......
     ........    ..'.............'..'....      ..........
   ..'..'...      ...............'.......      ..........
  ...'......     ...... ..........  ......         .......
 ...........   .......              ........        ......
.......        '...'.'.              '.'.'.'         ....
.......       .....'..               ..'.....
   ..       ..........               ..'........
          ............               ..............
         .............               '..............
        ...........'..              .'.'............
       ...............              .'.'.............
      .............'..               ..'..'...........
      ...............                 .'..............
       .........                        ..............
        .....
";
    Console.WriteLine(bot);
}
```

### <a name="test-the-tool"></a><span data-ttu-id="4df8f-125">Тестирование средства</span><span class="sxs-lookup"><span data-stu-id="4df8f-125">Test the tool</span></span>

<span data-ttu-id="4df8f-126">Запустите проект и просмотрите выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4df8f-126">Run the project and see the output.</span></span> <span data-ttu-id="4df8f-127">Поработайте с разными вариантами командной строки и сравните результаты:</span><span class="sxs-lookup"><span data-stu-id="4df8f-127">Try these variations of the command-line to see different results:</span></span>

```csharp
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

<span data-ttu-id="4df8f-128">Все аргументы после разделителя `--` передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="4df8f-128">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="setup-the-global-tool"></a><span data-ttu-id="4df8f-129">Настройка глобального средства</span><span class="sxs-lookup"><span data-stu-id="4df8f-129">Setup the global tool</span></span>

<span data-ttu-id="4df8f-130">Прежде чем упаковать и распространять приложение в качестве глобального средства, измените файл проекта.</span><span class="sxs-lookup"><span data-stu-id="4df8f-130">Before you can pack and distribute the application as a Global Tool, you need to modify the project file.</span></span> <span data-ttu-id="4df8f-131">Откройте файл `botsay.csproj` и добавьте три новых узла XML в узел `<Project><PropertyGroup>`:</span><span class="sxs-lookup"><span data-stu-id="4df8f-131">Open the `botsay.csproj` file and add three new XML nodes to the `<Project><PropertyGroup>` node:</span></span>

- `<PackAsTool>`  
<span data-ttu-id="4df8f-132">ОБЯЗАТЕЛЬНО. Указывает, что приложение будет упаковано для установки в качестве глобального средства.</span><span class="sxs-lookup"><span data-stu-id="4df8f-132">[REQUIRED] Indicates that the application will be packaged for install as a Global Tool.</span></span>

- `<ToolCommandName>`  
<span data-ttu-id="4df8f-133">НЕОБЯЗАТЕЛЬНО. Альтернативное имя для средства. Если не указано, имя команды для этого средства будет совпадать с именем файла проекта.</span><span class="sxs-lookup"><span data-stu-id="4df8f-133">[OPTIONAL] An alternative name for the tool, otherwise the command name for the tool will be named after the project file.</span></span> <span data-ttu-id="4df8f-134">Вы можете поместить в пакет несколько средств и выбрать для каждого из них уникальное и понятное имя, чтобы различать средства в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="4df8f-134">You can have multiple tools in a package, choosing a unique and friendly name helps differentiate from other tools in the same package.</span></span>

- `<PackageOutputPath>`  
<span data-ttu-id="4df8f-135">НЕОБЯЗАТЕЛЬНО. Расположение для создания пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="4df8f-135">[OPTIONAL] Where the NuGet package will be produced.</span></span> <span data-ttu-id="4df8f-136">Пакет NuGet будет использоваться платформой глобальных средств в интерфейсе командной строки .NET Core для установки созданного средства.</span><span class="sxs-lookup"><span data-stu-id="4df8f-136">The NuGet package is what the .NET Core CLI Global Tools uses to install your tool.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

<span data-ttu-id="4df8f-137">Параметр `<PackageOutputPath>` является необязательным, но используется в этом примере.</span><span class="sxs-lookup"><span data-stu-id="4df8f-137">Even though `<PackageOutputPath>` is optional, use it in this example.</span></span> <span data-ttu-id="4df8f-138">Следует задать для него значение `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span><span class="sxs-lookup"><span data-stu-id="4df8f-138">Make sure you set it: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span></span>

<span data-ttu-id="4df8f-139">Теперь создайте пакет NuGet для приложения.</span><span class="sxs-lookup"><span data-stu-id="4df8f-139">Next, create a NuGet package for your application.</span></span>

```console
dotnet pack
```

<span data-ttu-id="4df8f-140">Файл `botsay.1.0.0.nupkg` создается в папке, которую указывает значение XML `<PackageOutputPath>` из файла `botsay.csproj`. В нашем примере это папка `./nupkg`.</span><span class="sxs-lookup"><span data-stu-id="4df8f-140">The `botsay.1.0.0.nupkg` file is created in the folder identified by the `<PackageOutputPath>` XML value from the `botsay.csproj` file, which in this example is the `./nupkg` folder.</span></span> <span data-ttu-id="4df8f-141">Это упрощает установку и тестирование.</span><span class="sxs-lookup"><span data-stu-id="4df8f-141">This makes it easy to install and test.</span></span> <span data-ttu-id="4df8f-142">Если вы решите опубликовать это средство, передайте его в [https://www.nuget.org](https://www.nuget.org).</span><span class="sxs-lookup"><span data-stu-id="4df8f-142">When you want to release a tool publicly, upload it to [https://www.nuget.org](https://www.nuget.org).</span></span>

<span data-ttu-id="4df8f-143">Теперь у вас готов пакет и вы можете установить средство с его помощью:</span><span class="sxs-lookup"><span data-stu-id="4df8f-143">Now that you have a package, install the tool from that package:</span></span> 

```console
dotnet tool install --global --add-source ./nupkg botsay
```

<span data-ttu-id="4df8f-144">Параметр `--add-source` настраивает временное использование папки `./nupkg` в .NET Core CLI (папка `<PackageOutputPath>` в нашем примере) в качестве дополнительного источника пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="4df8f-144">The `--add-source` parameter tells the .NET Core CLI to temporarily use the `./nupkg` folder (our `<PackageOutputPath>` folder) as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="4df8f-145">См. дополнительные сведения [об установке глобальных средств .NET Core][global-tool-info].</span><span class="sxs-lookup"><span data-stu-id="4df8f-145">For more information about installing Global Tools, see [.NET Core Global Tools overview][global-tool-info].</span></span>

<span data-ttu-id="4df8f-146">Если установка выполнена успешно, отображается сообщение с командой, используемой для вызова средства, и установленной версией, аналогичное приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="4df8f-146">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

<span data-ttu-id="4df8f-147">Теперь вы можете получить ответ от созданного средства. Для этого введите команду `botsay`.</span><span class="sxs-lookup"><span data-stu-id="4df8f-147">You should now be able to type `botsay` and get a response from the tool.</span></span>

> [!NOTE]
> <span data-ttu-id="4df8f-148">Если установка прошла успешно, но команду `botsay` выполнить не удается, попробуйте открыть новое окно терминала, чтобы обновить значение PATH.</span><span class="sxs-lookup"><span data-stu-id="4df8f-148">If the install was successful, but you cannot use the `botsay` command, you may need to open a new terminal to refresh the PATH.</span></span>

## <a name="remove-the-tool"></a><span data-ttu-id="4df8f-149">Удаление средства</span><span class="sxs-lookup"><span data-stu-id="4df8f-149">Remove the tool</span></span>

<span data-ttu-id="4df8f-150">Закончив эксперименты с созданным средством, удалите его помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="4df8f-150">Once you're done experimenting with the tool, you can remove it with the following commnand:</span></span>

```console
dotnet tool uninstall -g botsay
```

[global-tool-info]: global-tools.md