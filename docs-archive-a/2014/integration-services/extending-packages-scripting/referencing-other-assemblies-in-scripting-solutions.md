---
title: Ссылки на другие сборки в решениях со скриптами | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, .NET Framework
- Script task [Integration Services], adding references
- referencing custom assemblies
- SSIS Script task, VisualBasic namespace
- assemblies [Integration Services]
- VisualBasic namespace
- Script task [Integration Services], VisualBasic namespace
- Microsoft.VisualBasic namespace
- Script task [Integration Services], .NET Framework
- .NET Framework [Integration Services]
- referencing Web services
ms.assetid: 9b655bcd-19f6-43d8-9f89-1b4d299c6380
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 685bbaa62da88e84cd848eb49dcf5bedb03d5390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656474"
---
# <a name="referencing-other-assemblies-in-scripting-solutions"></a><span data-ttu-id="153ef-102">Ссылки на другие сборки в решениях со сценариями</span><span class="sxs-lookup"><span data-stu-id="153ef-102">Referencing Other Assemblies in Scripting Solutions</span></span>
  <span data-ttu-id="153ef-103">Библиотека классов платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] предоставляет разработчику скриптов набор эффективных средств для реализации пользовательской функциональности в пакетах служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="153ef-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library provides the script developer with a powerful set of tools for implementing custom functionality in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="153ef-104">Задача «Скрипт» и компонент скрипта также могут использовать пользовательские управляемые сборки.</span><span class="sxs-lookup"><span data-stu-id="153ef-104">The Script task and the Script component can also use custom managed assemblies.</span></span>

> [!NOTE]
>  <span data-ttu-id="153ef-105">Чтобы разрешить пакетам использование объектов и методов из веб-службы, используйте команду **Добавить веб-ссылку**, доступную в средствах [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSTA).</span><span class="sxs-lookup"><span data-stu-id="153ef-105">To enable your packages to use the objects and methods from a Web service, use the **Add Web Reference** command available in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="153ef-106">В более ранних версиях служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], чтобы использовать веб-службу, приходилось формировать класс-посредник.</span><span class="sxs-lookup"><span data-stu-id="153ef-106">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you had to generate a proxy class to use a Web service.</span></span>

## <a name="using-a-managed-assembly"></a><span data-ttu-id="153ef-107">Использование управляемой сборки</span><span class="sxs-lookup"><span data-stu-id="153ef-107">Using a Managed Assembly</span></span>
 <span data-ttu-id="153ef-108">Чтобы во время разработки службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] могли найти управляемую сборку, нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="153ef-108">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find a managed assembly at design time, you must do the following steps:</span></span>

1.  <span data-ttu-id="153ef-109">Сохранить управляемую сборку в любой папке на компьютере.</span><span class="sxs-lookup"><span data-stu-id="153ef-109">Store the managed assembly in any folder on your computer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="153ef-110">В более ранних версиях служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] можно было добавлять ссылки только на управляемые сборки, хранящиеся в папке %windir%\Microsoft.NET\Framework\vx.x.xxxxx или %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies.</span><span class="sxs-lookup"><span data-stu-id="153ef-110">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you could only add a reference to a managed assembly that was stored in the %windir%\Microsoft.NET\Framework\vx.x.xxxxx folder or the %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies folder.</span></span>

2.  <span data-ttu-id="153ef-111">Добавить ссылку на управляемую сборку.</span><span class="sxs-lookup"><span data-stu-id="153ef-111">Add a reference to the managed assembly.</span></span>

     <span data-ttu-id="153ef-112">Чтобы добавить ссылку, в средствах VSTA в диалоговом окне **Добавление ссылки** на вкладке **Обзор** найдите и добавьте управляемую сборку.</span><span class="sxs-lookup"><span data-stu-id="153ef-112">To add the reference, in VSTA, in the **Add Reference** dialog box, on the **Browse** tab, locate and add the managed assembly.</span></span>

 <span data-ttu-id="153ef-113">Чтобы службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] могли найти управляемую сборку во время выполнения, необходимо выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="153ef-113">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find the managed assembly at run time, you must do the following steps:</span></span>

1.  <span data-ttu-id="153ef-114">Подписать управляемую сборку строгим именем.</span><span class="sxs-lookup"><span data-stu-id="153ef-114">Sign the managed assembly with a strong name.</span></span>

2.  <span data-ttu-id="153ef-115">Установить сборку в глобальный кэш сборок на компьютере, где выполняется пакет.</span><span class="sxs-lookup"><span data-stu-id="153ef-115">Install the assembly in the global assembly cache on the computer on which the package is run.</span></span>

     <span data-ttu-id="153ef-116">Дополнительные сведения см. в разделе [Сборка, развертывание и отладка пользовательских объектов](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="153ef-116">For more information, see [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span></span>

## <a name="using-the-microsoft-net-framework-class-library"></a><span data-ttu-id="153ef-117">Использование библиотеки классов платформы Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="153ef-117">Using the Microsoft .NET Framework Class Library</span></span>
 <span data-ttu-id="153ef-118">Задача «Скрипт» и компонент Script могут использовать преимущества всех остальных объектов и функциональность, которую обеспечивает библиотека классов платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="153ef-118">The Script task and the Script component can take advantage of all the other objects and functionality exposed by the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="153ef-119">Например, с помощью платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] можно извлекать сведения о среде и взаимодействовать с компьютером, на котором работает пакет.</span><span class="sxs-lookup"><span data-stu-id="153ef-119">For example, by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can retrieve information about your environment and interact with the computer that is running the package.</span></span>

 <span data-ttu-id="153ef-120">В следующем списке описываются некоторые из наиболее часто используемых классов платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="153ef-120">This list describes several of the more frequently used [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes:</span></span>

-   <span data-ttu-id="153ef-121">`System.Data`Содержит архитектуру ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="153ef-121">`System.Data` Contains the ADO.NET architecture.</span></span>

-   <span data-ttu-id="153ef-122">`System.IO`Предоставляет интерфейс для файловой системы и потоков.</span><span class="sxs-lookup"><span data-stu-id="153ef-122">`System.IO` Provides an interface to the file system and streams.</span></span>

-   <span data-ttu-id="153ef-123">`System.Windows.Forms`Обеспечивает создание форм.</span><span class="sxs-lookup"><span data-stu-id="153ef-123">`System.Windows.Forms` Provides form creation.</span></span>

-   <span data-ttu-id="153ef-124">`System.Text.RegularExpressions`Предоставляет классы для работы с регулярными выражениями.</span><span class="sxs-lookup"><span data-stu-id="153ef-124">`System.Text.RegularExpressions` Provides classes for working with regular expressions.</span></span>

-   <span data-ttu-id="153ef-125">`System.Environment`Возвращает сведения о локальном компьютере, текущем пользователе, а также о параметрах компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="153ef-125">`System.Environment` Returns information about the local computer, the current user, and computer and user settings.</span></span>

-   <span data-ttu-id="153ef-126">`System.Net`Обеспечивает сетевую связь.</span><span class="sxs-lookup"><span data-stu-id="153ef-126">`System.Net` Provides network communications.</span></span>

-   <span data-ttu-id="153ef-127">`System.DirectoryServices`Предоставляет Active Directory.</span><span class="sxs-lookup"><span data-stu-id="153ef-127">`System.DirectoryServices` Exposes Active Directory.</span></span>

-   <span data-ttu-id="153ef-128">`System.Drawing`Предоставляет обширные библиотеки управления образами.</span><span class="sxs-lookup"><span data-stu-id="153ef-128">`System.Drawing` Provides extensive image manipulation libraries.</span></span>

-   <span data-ttu-id="153ef-129">`System.Threading`Включает многопоточное программирование.</span><span class="sxs-lookup"><span data-stu-id="153ef-129">`System.Threading` Enables multithreaded programming.</span></span>

 <span data-ttu-id="153ef-130">Дополнительные сведения о платформе [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] см. в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="153ef-130">For more information about the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see the MSDN Library.</span></span>

<span data-ttu-id="153ef-131">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="153ef-131">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="153ef-132">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="153ef-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="153ef-133">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="153ef-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="153ef-134">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="153ef-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="153ef-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="153ef-135">See Also</span></span>
 [<span data-ttu-id="153ef-136">Расширение пакетов с помощью сценариев</span><span class="sxs-lookup"><span data-stu-id="153ef-136">Extending Packages with Scripting</span></span>](extending-packages-with-scripting.md)


