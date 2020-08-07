---
title: Руководство. Отладка пользовательских сборок | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services], debugging
- debugging custom assemblies [Reporting Services]
- troubleshooting [Reporting Services], custom assemblies
ms.assetid: 3a3215b3-548c-4474-81ba-3a98dd3912bf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b5f9f5a4595d59cce98da4f753422cd07529926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733665"
---
# <a name="how-to-debug-custom-assemblies"></a><span data-ttu-id="69985-102">Руководство. Отладка пользовательских сборок</span><span class="sxs-lookup"><span data-stu-id="69985-102">How to: Debug Custom Assemblies</span></span>
  <span data-ttu-id="69985-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Предоставляет несколько средств отладки, которые могут помочь в анализе кода пользовательской сборки и обнаружении ошибок в нем.</span><span class="sxs-lookup"><span data-stu-id="69985-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your custom assembly code and locate errors in it.</span></span> <span data-ttu-id="69985-104">Выбор наиболее подходящего средства отладки зависит от того, какая цель должна быть достигнута.</span><span class="sxs-lookup"><span data-stu-id="69985-104">The best tool to use will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="69985-105">В этом примере используется [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69985-105">This example uses [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span>  
  
 <span data-ttu-id="69985-106">Рекомендуемый способ проектирования, разработки и тестирования пользовательских сборок для службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] состоит в создании решения, содержащего не только пользовательскую сборку, но и тестовые отчеты.</span><span class="sxs-lookup"><span data-stu-id="69985-106">The recommended way to design, develop, and test custom assemblies for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is to create a solution that contains both your test reports and your custom assembly.</span></span>  
  
### <a name="to-debug-assemblies-using-a-single-instance-of-visual-studio"></a><span data-ttu-id="69985-107">Отладка сборок с помощью одного экземпляра Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69985-107">To debug assemblies using a single instance of Visual Studio</span></span>  
  
1.  <span data-ttu-id="69985-108">Создание нового проекта отчета с помощью [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69985-108">Create a new report project using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
     <span data-ttu-id="69985-109">При создании проекта отчета в среде [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] создается также содержащее его решение.</span><span class="sxs-lookup"><span data-stu-id="69985-109">At the time you create a report project, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] also creates a solution to contain it.</span></span>  
  
2.  <span data-ttu-id="69985-110">Добавьте в существующее решение проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="69985-110">Add a new Class Library project to the existing solution.</span></span> <span data-ttu-id="69985-111">Убедитесь, что проект отчета задан в качестве автоматически запускаемого.</span><span class="sxs-lookup"><span data-stu-id="69985-111">Make sure that the report project is set as the startup project.</span></span> <span data-ttu-id="69985-112">Дополнительные сведения о выполнении этого действия см. в документации по среде [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69985-112">For more information about how to accomplish this, see your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
3.  <span data-ttu-id="69985-113">Выберите решение в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="69985-113">In Solution Explorer, select the solution.</span></span>  
  
4.  <span data-ttu-id="69985-114">В меню **Вид** выберите команду **Страницы свойств**.</span><span class="sxs-lookup"><span data-stu-id="69985-114">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="69985-115">Откроется диалоговое окно **Страницы свойств решения**.</span><span class="sxs-lookup"><span data-stu-id="69985-115">The **Solution Property Pages** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="69985-116">В панели слева разверните при необходимости пункт **Общие свойства**, затем нажмите кнопку **Зависимости проекта**.</span><span class="sxs-lookup"><span data-stu-id="69985-116">In the left pane, expand **Common Properties** if necessary, and click **Project Dependencies**.</span></span> <span data-ttu-id="69985-117">Выберите проект отчета в раскрывающемся списке **Проект**.</span><span class="sxs-lookup"><span data-stu-id="69985-117">Select the report project from the **Project** drop-down list.</span></span> <span data-ttu-id="69985-118">Выберите проект сборки в списке **Зависит от**.</span><span class="sxs-lookup"><span data-stu-id="69985-118">Select your assembly project in the **Depends On** list.</span></span>  
  
6.  <span data-ttu-id="69985-119">Нажмите кнопку **ОК**, чтобы сохранить изменения и выйти из диалогового окна **Страницы свойств**.</span><span class="sxs-lookup"><span data-stu-id="69985-119">Click **OK** to save the changes, and close the **Property Pages** dialog.</span></span>  
  
7.  <span data-ttu-id="69985-120">В обозревателе решений выберите проект пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="69985-120">In Solution Explorer, select your custom assembly project.</span></span>  
  
8.  <span data-ttu-id="69985-121">В меню **Вид** выберите команду **Страницы свойств**.</span><span class="sxs-lookup"><span data-stu-id="69985-121">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="69985-122">Откроется диалоговое окно **Страницы свойств проекта**.</span><span class="sxs-lookup"><span data-stu-id="69985-122">The **Project Property Pages** dialog box opens.</span></span>  
  
9. <span data-ttu-id="69985-123">Щелкните вкладку **Сборка**, если это проект C#, или вкладку **Компиляция**, если это проект [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69985-123">Click the **Build** tab if you're in a C# project or the **Compile** tab if you're in a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] project.</span></span>  
  
10. <span data-ttu-id="69985-124">На странице **Build** / **Компиляция** сборки введите путь к папке конструктор отчетов.</span><span class="sxs-lookup"><span data-stu-id="69985-124">On the **Build**/**Compile** page, enter the path to the Report Designer folder.</span></span> <span data-ttu-id="69985-125">По умолчанию это путь C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) в текстовом поле **Выходной путь**.</span><span class="sxs-lookup"><span data-stu-id="69985-125">By default, this is C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) in the **Output Path** text box.</span></span> <span data-ttu-id="69985-126">В результате перед выполнением отчета произойдет построение и развертывание обновленной версии пользовательской сборки непосредственно в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="69985-126">This builds and deploys an updated version of your custom assembly directly to Report Designer before your report is executed.</span></span>  
  
11. <span data-ttu-id="69985-127">После того как будет сконструирован отчет и разработана пользовательская сборка, задайте точки останова в коде пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="69985-127">Once you have designed your report and developed your custom assembly, set breakpoints in your custom assembly code.</span></span>  
  
12. <span data-ttu-id="69985-128">Запустите отчет в режиме **DebugLocal**. Для этого нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="69985-128">Run the report under **DebugLocal** mode by pressing the F5 key.</span></span> <span data-ttu-id="69985-129">После того как отчет запустится во всплывающем окне предварительного просмотра, отладчик будет обрабатывать все точки останова, соответствующие исполняемому коду в сборке.</span><span class="sxs-lookup"><span data-stu-id="69985-129">When the report executes in the pop-up preview window, the debugger hits any breakpoints that correspond to executable code in your assembly.</span></span> <span data-ttu-id="69985-130">Для пошагового выполнения кода пользовательской сборки воспользуйтесь клавишей F11.</span><span class="sxs-lookup"><span data-stu-id="69985-130">Use F11 to step through your custom assembly code.</span></span>  
  
### <a name="to-debug-assemblies-using-two-instances-of-visual-studio"></a><span data-ttu-id="69985-131">Отладка сборок с помощью двух экземпляров Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69985-131">To debug assemblies using two instances of Visual Studio</span></span>  
  
1.  <span data-ttu-id="69985-132">Запустите среду [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] и откройте проект пользовательской сборки.</span><span class="sxs-lookup"><span data-stu-id="69985-132">Start [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] and open your custom assembly project.</span></span>  
  
2.  <span data-ttu-id="69985-133">В конструкторе отчетов постройте проект и выполните развертывание пользовательской сборки и сопутствующего файла PDB.</span><span class="sxs-lookup"><span data-stu-id="69985-133">Build the project, and deploy your custom assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="69985-134">Дополнительные сведения о развертывании см. в разделе [Развертывание пользовательской сборки](deploying-a-custom-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="69985-134">For more information about deployment, see [Deploying a Custom Assembly](deploying-a-custom-assembly.md).</span></span>  
  
3.  <span data-ttu-id="69985-135">Откройте проект отчета, в котором используется сборка, после чего оставьте ее код открытым в отдельном экземпляре [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69985-135">Open up a report project that uses your custom assembly while leaving your custom assembly code open in a separate instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="69985-136">Перейдите к экземпляру [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], который содержит проект пользовательской сборки, и задайте в коде необходимые точки останова.</span><span class="sxs-lookup"><span data-stu-id="69985-136">Navigate to the instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] that contains your custom assembly project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="69985-137">Оставив активным окно проекта пользовательской сборки, выберите **Присоединить к процессу** в меню **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="69985-137">With the custom assembly project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="69985-138">Откроется диалоговое окно **Присоединение к процессу**.</span><span class="sxs-lookup"><span data-stu-id="69985-138">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="69985-139">Выберите из списка процессов devenv.exe, который соответствует проекту отчета, и нажмите кнопку **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="69985-139">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="69985-140">Определите выражения из пользовательской сборки, которые будут использоваться в отчете, и создайте отчет.</span><span class="sxs-lookup"><span data-stu-id="69985-140">Define the expressions that you will use in your report from your custom assembly and design your report.</span></span>  
  
8.  <span data-ttu-id="69985-141">После завершения проектирования отчета щелкните вкладку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="69985-141">When you are finished designing your report, click the **Preview** tab.</span></span>  
  
     <span data-ttu-id="69985-142">Отчет запустится, и выполнение кода пользовательской сборки будет прерываться в ранее заданных точках останова.</span><span class="sxs-lookup"><span data-stu-id="69985-142">The report executes, and the custom assembly code should break at your predefined break points.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="69985-143">Вкладка **Просмотр** не позволяет принудительно применять разрешения кода для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="69985-143">Using the **Preview** tab does not enforce code permissions for the assembly.</span></span> <span data-ttu-id="69985-144">Для полного тестирования, которое затрагивает все ошибки безопасности при управлении доступом для кода, запустите проект отчета с параметром конфигурации **DebugLocal**.</span><span class="sxs-lookup"><span data-stu-id="69985-144">For a complete test, which includes any code access security errors, start the report project under the **DebugLocal** configuration setting.</span></span>  
  
9. <span data-ttu-id="69985-145">Перемещайтесь по шагам кода с помощью клавиши F11.</span><span class="sxs-lookup"><span data-stu-id="69985-145">Step through your code using the F11 key.</span></span> <span data-ttu-id="69985-146">Дополнительные сведения об отладке с помощью среды [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] см. в документации по [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69985-146">For more information about debugging using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69985-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="69985-147">See Also</span></span>  
 [<span data-ttu-id="69985-148">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="69985-148">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
