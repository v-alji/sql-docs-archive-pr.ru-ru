---
title: Переименование многомерной базы данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- renaming databases
ms.assetid: 15fdaec7-f3e4-44d9-9b78-1a1d78c484e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3974e7671aff5d1cba22b10563bbc85a129a1dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665623"
---
# <a name="rename-a-multidimensional-database-analysis-services"></a><span data-ttu-id="32402-102">Переименование многомерной базы данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="32402-102">Rename a Multidimensional Database (Analysis Services)</span></span>
  <span data-ttu-id="32402-103">Способ изменения имени [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных зависит от способа подключения к [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="32402-103">The manner in which you change the name of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database depends upon how you connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="32402-104">Чтобы изменить имя существующей базы данных, необходимо подключиться к ней в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="32402-104">To change the name of an existing database, you must connect in online mode.</span></span> <span data-ttu-id="32402-105">Чтобы изменить имя базы данных, в которой будут создаваться экземпляры объектов проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , необходимо подключиться к ней в режиме проекта.</span><span class="sxs-lookup"><span data-stu-id="32402-105">To change the name of the database into which objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project will be instantiated, you must connect in project mode.</span></span>  
  
### <a name="to-change-the-database-name-in-online-mode"></a><span data-ttu-id="32402-106">Изменение имени базы данных в режиме в сети</span><span class="sxs-lookup"><span data-stu-id="32402-106">To change the database name in online mode</span></span>  
  
1.  <span data-ttu-id="32402-107">Используя среду [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], подключитесь напрямую к базе данных [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32402-107">Using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], connect directly to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="32402-108">В обозревателе решений щелкните правой кнопкой мыши базу данных, после чего выберите пункт **Изменить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="32402-108">In Solution Explorer, right-click the database and then click **Edit Database**.</span></span>  
  
3.  <span data-ttu-id="32402-109">В текстовом поле **Имя базы данных** измените имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="32402-109">In the **Database name** text box, change the database name.</span></span>  
  
4.  <span data-ttu-id="32402-110">На панели инструментов щелкните **Сохранить** или **Сохранить все** , щелкните **Сохранить выбранные элементы** или **Сохранить все** в меню **Файл** , или закройте **Конструктор баз данных** и при появлении запроса нажмите кнопку **Сохранить** .</span><span class="sxs-lookup"><span data-stu-id="32402-110">Click **Save** or **Save All** on the toolbar, click **Save Selected Items** or **Save All** on the **File** menu, or close the **Database Designer** and then click **Save** when prompted.</span></span>  
  
     <span data-ttu-id="32402-111">Имя базы данных обновится в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , а объекты базы данных обновятся в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="32402-111">The database name is updated in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the database object in Solution Explorer is refreshed.</span></span>  
  
### <a name="to-change-the-database-name-in-project-mode"></a><span data-ttu-id="32402-112">Изменение имени базы данных в проектном режиме</span><span class="sxs-lookup"><span data-stu-id="32402-112">To change the database name in project mode</span></span>  
  
1.  <span data-ttu-id="32402-113">Откройте проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32402-113">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="32402-114">В обозревателе решений щелкните правой кнопкой мыши проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="32402-114">In Solution Explorer, right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="32402-115">В диалоговом окне **Страницы свойств** в разделе **Свойства конфигурации** выберите пункт **Развертывание** .</span><span class="sxs-lookup"><span data-stu-id="32402-115">In the **Property Pages** dialog box, click **Deployment** in the **Configuration Properties** section.</span></span>  
  
4.  <span data-ttu-id="32402-116">Измените свойство **База данных** на новое имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="32402-116">Change the **Database** property to the new database name.</span></span>  
  
     <span data-ttu-id="32402-117">В следующий раз при развертывании проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] он будет развернут с новым именем базы данных.</span><span class="sxs-lookup"><span data-stu-id="32402-117">The next time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is deployed, it will be deployed to this new database name.</span></span> <span data-ttu-id="32402-118">Если база данных уже существует, она будет перезаписана.</span><span class="sxs-lookup"><span data-stu-id="32402-118">If this database already exists, it will be overwritten.</span></span>  
  
### <a name="to-change-the-database-name-using-sql-server-management-studio"></a><span data-ttu-id="32402-119">Изменение имени базы данных с помощью среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="32402-119">To change the database name using SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="32402-120">Щелкните правой кнопкой базу данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и измените свойство "Имя".</span><span class="sxs-lookup"><span data-stu-id="32402-120">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and edit the Name property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32402-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="32402-121">See Also</span></span>  
 <span data-ttu-id="32402-122">[Настройка свойств сервера в Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="32402-122">[Configure Server Properties in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span></span>  
 <span data-ttu-id="32402-123">[Задание свойств многомерной базы данных &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="32402-123">[Set Multidimensional Database Properties &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="32402-124">[Настройка Analysis Services свойств проекта &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="32402-124">[Configure Analysis Services Project Properties &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span></span>  
 [<span data-ttu-id="32402-125">Развертывание проектов служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="32402-125">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  
