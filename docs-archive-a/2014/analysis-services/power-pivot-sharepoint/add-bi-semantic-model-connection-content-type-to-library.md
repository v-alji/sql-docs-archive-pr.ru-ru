---
title: Добавление типа содержимого соединения семантической модели бизнес-аналитики в библиотеку (PowerPivot для SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 145505ed-50bc-4528-912b-2a5cd2566011
author: minewiskan
ms.author: owend
ms.openlocfilehash: ecd40193b382aa692beeadd55ab8f9388c328620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667439"
---
# <a name="add-a-bi-semantic-model-connection-content-type-to-a-library-powerpivot-for-sharepoint"></a><span data-ttu-id="cee59-102">Добавление типа содержимого соединения семантической модели бизнес-аналитики в библиотеку (PowerPivot для SharePoint)</span><span class="sxs-lookup"><span data-stu-id="cee59-102">Add a BI Semantic Model Connection Content Type to a Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="cee59-103">Соединение с семантической моделью бизнес-аналитики создается в SharePoint и позволяет обеспечить перенаправление к данным семантической модели бизнес-аналитики в книге PowerPivot или в табличном шаблоне базы данных служб Analysis Services, работающей на сетевом сервере.</span><span class="sxs-lookup"><span data-stu-id="cee59-103">A BI semantic model connection is created in SharePoint and provides redirection to business intelligence semantic model data in a PowerPivot workbook or Analysis Services tabular model database on a network server.</span></span> <span data-ttu-id="cee59-104">Прежде чем приступать к созданию соединения с семантической моделью бизнес-аналитики в SharePoint, необходимо расширить библиотеку документов для создания BISM-файла.</span><span class="sxs-lookup"><span data-stu-id="cee59-104">Before you can create a BI semantic model connection in SharePoint, you must extend a document library to allow the creation of a .bism file.</span></span> <span data-ttu-id="cee59-105">Этот шаг должен выполняться только один раз для каждой библиотеки, однако его придется повторить для всех библиотек, из которых требуется создать файл BISM.</span><span class="sxs-lookup"><span data-stu-id="cee59-105">This step only needs to be performed once for each library, but you will need to repeat it for any library from which you want to create .bism files.</span></span> <span data-ttu-id="cee59-106">Рекомендуется создать централизованную библиотеку для хранения файлов BISM, чтобы разрешениями можно было управлять в одном месте.</span><span class="sxs-lookup"><span data-stu-id="cee59-106">Best practices recommend that you create a centralized library for storing .bism files so that you can manage permissions in one place.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cee59-107">Если библиотека подключения к данным SharePoint уже используется, то тип содержимого «Соединение семантической модели бизнес-аналитики» будет автоматически добавлен в шаблон этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="cee59-107">If you already use SharePoint Data Connection Libraries, the BI Semantic Model Connection content type is automatically added to that library template.</span></span> <span data-ttu-id="cee59-108">Описанное в этом разделе действие можно пропустить, если используется библиотека подключения к данным, которая уже позволяет создавать новые документы соединений семантической модели бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="cee59-108">You can skip the steps in this section if you use a data connection library that already lets you create new BI semantic model connection documents.</span></span>  
  
##  <a name="add-the-content-type-to-a-document-library"></a><a name="bkmk_addtype"></a> <span data-ttu-id="cee59-109">Добавление типа содержимого в библиотеку документов</span><span class="sxs-lookup"><span data-stu-id="cee59-109">Add the content type to a document library</span></span>  
 <span data-ttu-id="cee59-110">Чтобы добавлять и настраивать тип содержимого, необходимо разрешение не ниже «Управление списками».</span><span class="sxs-lookup"><span data-stu-id="cee59-110">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="cee59-111">Это разрешение встроено в разрешения уровня «Создание» и выше.</span><span class="sxs-lookup"><span data-stu-id="cee59-111">This permission is built into the Design permission level and above.</span></span>  
  
 <span data-ttu-id="cee59-112">Веб-сайт, содержащий библиотеку документов, должен иметь активацию компонентов PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cee59-112">The site that contains the document library must have feature activation for PowerPivot for SharePoint.</span></span> <span data-ttu-id="cee59-113">Дополнительные сведения см. [в разделе Активация интеграции функций PowerPivot для семейств веб-сайтов в центре администрирования](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="cee59-113">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>  
  
1.  <span data-ttu-id="cee59-114">Откройте библиотеку документов, для которой необходимо включить тип содержимого «Соединение семантической модели бизнес-аналитики».</span><span class="sxs-lookup"><span data-stu-id="cee59-114">Open the document library for which you want to enable the BI Semantic Model Connection content type.</span></span>  
  
2.  <span data-ttu-id="cee59-115">На ленте SharePoint в разделе «Средства библиотеки» выберите пункт **Библиотека**.</span><span class="sxs-lookup"><span data-stu-id="cee59-115">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>  
  
3.  <span data-ttu-id="cee59-116">Нажмите кнопку **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="cee59-116">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="cee59-117">В разделе «Общие параметры» нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="cee59-117">In General Settings, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="cee59-118">В группе "Разрешить управление типами содержимого?" раздела "Типы содержимого"</span><span class="sxs-lookup"><span data-stu-id="cee59-118">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="cee59-119">выберите вариант **Да**.</span><span class="sxs-lookup"><span data-stu-id="cee59-119">section, click **Yes**.</span></span>  
  
6.  <span data-ttu-id="cee59-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cee59-120">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="cee59-121">В разделе «Типы содержимого» выберите пункт **Добавить из существующих типов содержимого сайта**.</span><span class="sxs-lookup"><span data-stu-id="cee59-121">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="cee59-122">Если эта страница не отображается, вернитесь на сайт, выберите в средствах библиотеки **Библиотека** , а затем выберите **Параметры библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="cee59-122">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>  
  
8.  <span data-ttu-id="cee59-123">В разделе «Типы содержимого» выберите пункт **Добавить из существующих типов содержимого сайта**.</span><span class="sxs-lookup"><span data-stu-id="cee59-123">In Content Types, click **Add from existing site content types**.</span></span>  
  
9. <span data-ttu-id="cee59-124">В разделе «Выберите типы содержимого сайта из списка» выберите элемент **Бизнес-аналитика**.</span><span class="sxs-lookup"><span data-stu-id="cee59-124">In Select site content types from:, select **Business Intelligence**.</span></span>  
  
10. <span data-ttu-id="cee59-125">В разделе «Доступные типы содержимого сайта» выберите **Файл соединения семантической модели бизнес-аналитики**и нажмите **Добавить** , чтобы переместить выбранный тип содержимого в список «Типы содержимого для добавления».</span><span class="sxs-lookup"><span data-stu-id="cee59-125">In Available Site Content Types, click **BI Semantic Model Connection File**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>  
  
11. <span data-ttu-id="cee59-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cee59-126">Click **OK**.</span></span>  
  
12. <span data-ttu-id="cee59-127">Чтобы проверить тип добавляемого содержимого, вернитесь к библиотеке и щелкните **Создать документ** в области «Документы» на ленте библиотеки.</span><span class="sxs-lookup"><span data-stu-id="cee59-127">To verify you added the content type, go back to the library and click **New Document** on the Documents area of the library ribbon.</span></span> <span data-ttu-id="cee59-128">В списке «Создать документ» будет пункт **Файл соединения семантической модели бизнес-аналитики** .</span><span class="sxs-lookup"><span data-stu-id="cee59-128">You should see **BI Semantic Model Connection File** in the New Documents list.</span></span>  
  
     <span data-ttu-id="cee59-129">![Подменю «Создать документ» в библиотеке SharePoint](../media/ssas-bismconnection-new.gif "Подменю «Создать документ» в библиотеке SharePoint")</span><span class="sxs-lookup"><span data-stu-id="cee59-129">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
 <span data-ttu-id="cee59-130">После включения типа файла соединения семантической модели бизнес-аналитики в библиотеке можно будет создать соединение, которое будет перенаправлять подключение к данным семантической модели, и использовать его в отчетах Excel или [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cee59-130">After you enable the BI semantic model connection content type for a library, you can create a connection that provides redirection to business semantic model data that can be used by Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="cee59-131">Выберите одну из следующих ссылок, чтобы узнать подробнее о следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="cee59-131">Choose from the following links to learn more about this next step:</span></span>  
  
 [<span data-ttu-id="cee59-132">Создание соединения семантической модели бизнес-аналитики с книгой PowerPivot</span><span class="sxs-lookup"><span data-stu-id="cee59-132">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="cee59-133">Create a BI Semantic Model Connection to a Tabular Model Database</span><span class="sxs-lookup"><span data-stu-id="cee59-133">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="cee59-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="cee59-134">See Also</span></span>  
 <span data-ttu-id="cee59-135">[Соединение семантической модели бизнес-аналитики PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="cee59-135">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="cee59-136">Использование соединения семантической модели бизнес-аналитики в службах Excel или Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cee59-136">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
  
