---
title: Занятие 1. Создание проекта клиента веб-службы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0070daa6-56b0-4663-83b2-44c96acafad8
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: eda9413867c4ca6d44a5cf98b82be9bddc04d0f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734710"
---
# <a name="lesson-1-creating-the-web-service-client-project"></a><span data-ttu-id="d9e95-102">Урок 1. Создание проекта клиентской веб-службы</span><span class="sxs-lookup"><span data-stu-id="d9e95-102">Lesson 1: Creating the Web Service Client Project</span></span>
  <span data-ttu-id="d9e95-103">В этом пошаговом руководстве предстоит создать простое приложение командной строки, которое обращается к веб-службе сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d9e95-103">For this walkthrough, you will create a simple console application that accesses the Report Server Web service.</span></span> <span data-ttu-id="d9e95-104">Предполагается, что разработка ведется в среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9e95-104">This walkthrough assumes you are developing in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="d9e95-105">Создание приложения командной строки</span><span class="sxs-lookup"><span data-stu-id="d9e95-105">To create a console application</span></span>  
  
1.  <span data-ttu-id="d9e95-106">В меню **Файл** выберите **Создать**, а затем **Проект** , чтобы открыть диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="d9e95-106">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="d9e95-107">В панели слева в разделе **Установленные шаблоны**щелкните узел **Visual Basic** или **Visual C#** и выберите категорию типов проекта из раскрывшегося списка.</span><span class="sxs-lookup"><span data-stu-id="d9e95-107">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="d9e95-108">Выберите тип проекта **Консольное приложение** .</span><span class="sxs-lookup"><span data-stu-id="d9e95-108">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="d9e95-109">В поле **Name** введите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e95-109">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="d9e95-110">Введите имя `GetPropertiesSample` .</span><span class="sxs-lookup"><span data-stu-id="d9e95-110">Type the name `GetPropertiesSample`.</span></span>  
  
5.  <span data-ttu-id="d9e95-111">В поле **Расположение** введите путь, по которому нужно сохранить проект, или нажмите кнопку **Обзор** , чтобы перейти к папке.</span><span class="sxs-lookup"><span data-stu-id="d9e95-111">In the **Location** box, enter the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="d9e95-112">В обозреватель решений отображается свернутое представление проекта.</span><span class="sxs-lookup"><span data-stu-id="d9e95-112">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
     <span data-ttu-id="d9e95-113">Раскройте узел проекта в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="d9e95-113">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="d9e95-114">В проект добавлен файл с именем по умолчанию Program.cs (Module1. vb для [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="d9e95-114">A file with the default name of Program.cs (Module1.vb for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e95-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9e95-115">See Also</span></span>  
 <span data-ttu-id="d9e95-116">[Занятие 2. Добавление веб-ссылки](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d9e95-116">[Lesson 2: Adding a Web Reference](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span></span>  
 [<span data-ttu-id="d9e95-117">Доступ к веб-службе сервера отчетов с помощью Visual Basic или учебника по Visual C&#35; &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d9e95-117">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
