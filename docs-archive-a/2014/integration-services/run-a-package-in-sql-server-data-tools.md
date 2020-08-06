---
title: Запуск пакета в SQL Server Data Tools | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
ms.assetid: 318e6beb-5540-4101-82a5-18c9d47f0570
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31ca2390ef6bb04b63e4de9978193aed8884da36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729561"
---
# <a name="run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="28551-102">Запуск пакета с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="28551-102">Run a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="28551-103">Обычно пакеты исполняются в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] во время разработки, отладки и тестирования пакетов.</span><span class="sxs-lookup"><span data-stu-id="28551-103">You typically run packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] during the development, debugging, and testing of packages.</span></span> <span data-ttu-id="28551-104">Когда пакет запускается из конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , его запуск происходит немедленно.</span><span class="sxs-lookup"><span data-stu-id="28551-104">When you run a package from [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the package always runs immediately.</span></span>  
  
 <span data-ttu-id="28551-105">Во время выполнения пакета конструктор служб [!INCLUDE[ssIS](../includes/ssis-md.md)] отображает ход выполнения пакета на вкладке **Выполнение** . Можно видеть время начала и завершения выполнения пакета, его задачи и контейнеры — наряду с данными о задачах или контейнерах пакета, завершившегося ошибкой.</span><span class="sxs-lookup"><span data-stu-id="28551-105">While a package is running, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer displays the progress of package execution on the **Progress** tab. You can view the start and finish time of the package and its tasks and containers, in addition to information about any tasks or containers in the package that failed.</span></span> <span data-ttu-id="28551-106">По завершении выполнения пакета на вкладке **Результаты выполнения** сохраняются сведения о ходе выполнения. Дополнительные сведения см. в подразделе "Отчет о состоянии" раздела [Отладка потока управления](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="28551-106">After the package finishes running, the run-time information remains available on the **Execution Results** tab. For more information, see the section, "Progress Reporting," in the topic, [Debugging Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="28551-107">**Развертывание времени проектирования**.</span><span class="sxs-lookup"><span data-stu-id="28551-107">**Design-time deployment**.</span></span> <span data-ttu-id="28551-108">Когда запуск пакета произведен в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], происходит построение пакета и затем его развертывание в папку.</span><span class="sxs-lookup"><span data-stu-id="28551-108">When you run a package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the package is built and then deployed to a folder.</span></span> <span data-ttu-id="28551-109">Перед запуском пакета можно указать папку, в которой будет производиться развертывание пакета.</span><span class="sxs-lookup"><span data-stu-id="28551-109">Before you run the package, you can specify the folder to which the package is deployed.</span></span> <span data-ttu-id="28551-110">Если папка не указана, то по умолчанию используется папка **bin** .</span><span class="sxs-lookup"><span data-stu-id="28551-110">If you do not specify a folder, the **bin** folder is used by default.</span></span> <span data-ttu-id="28551-111">Этот тип развертывания называется развертыванием времени разработки.</span><span class="sxs-lookup"><span data-stu-id="28551-111">This type of deployment is called design-time deployment.</span></span>  
  
### <a name="to-run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="28551-112">Запуск пакета с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="28551-112">To run a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="28551-113">Если решение содержит несколько проектов, щелкните в обозревателе решений правой кнопкой мыши папку проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащую пакет, и задайте стартовый проект, выбрав пункт **Установить в качестве автоматически запускаемого объекта** .</span><span class="sxs-lookup"><span data-stu-id="28551-113">In Solution Explorer, if your solution contains multiple projects, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package, and then click **Set as StartUp Object** to set the startup project.</span></span>  
  
2.  <span data-ttu-id="28551-114">Если проект содержит несколько пакетов, щелкните в обозревателе решений правой кнопкой мыши пакет и задайте стартовый пакет, выбрав пункт **Установить в качестве автоматически запускаемого объекта** .</span><span class="sxs-lookup"><span data-stu-id="28551-114">In Solution Explorer, if your project contains multiple packages, right-click a package, and then click **Set as StartUp Object** to set the startup package.</span></span>  
  
3.  <span data-ttu-id="28551-115">Чтобы запустить пакет, выполните одну из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="28551-115">To run a package, use one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="28551-116">Откройте пакет, который необходимо запустить, затем выберите пункт **Начать отладку** в меню или нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="28551-116">Open the package that you want to run and then click **Start Debugging** on the menu bar, or press F5.</span></span> <span data-ttu-id="28551-117">После исполнения пакета нажмите клавиши Shift+F5 для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="28551-117">After the package finishes running, press Shift+F5 to return to design mode.</span></span>  
  
    -   <span data-ttu-id="28551-118">В обозревателе решений щелкните правой кнопкой мыши пакет, после чего выберите пункт **Выполнить пакет**.</span><span class="sxs-lookup"><span data-stu-id="28551-118">In Solution Explorer, right-click the package, and then click **Execute Package**.</span></span>  
  
### <a name="to-specify-a-different-folder-for-design-time-deployment"></a><span data-ttu-id="28551-119">Задание каталога для развертывания времени разработки</span><span class="sxs-lookup"><span data-stu-id="28551-119">To specify a different folder for design-time deployment</span></span>  
  
1.  <span data-ttu-id="28551-120">В обозревателе решений щелкните правой кнопкой мыши папку проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащую запускаемый пакет, затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="28551-120">In Solution Explorer, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project folder that contains the package you want to run, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="28551-121">В диалоговом окне **Страницы свойств \<project name>** выберите элемент **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="28551-121">In the **\<project name> Property Pages** dialog box, click **Build**.</span></span>  
  
3.  <span data-ttu-id="28551-122">Обновите значения свойства OutputPath для указания папки, которую необходимо использовать для развертывания времени разработки, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28551-122">Update the value in the OutputPath property to specify the folder you want to use for design-time deployment, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28551-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="28551-123">See Also</span></span>  
 <span data-ttu-id="28551-124">[Запуск проектов и пакетов](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="28551-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="28551-125">Пакеты служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="28551-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
