---
title: Определение источника данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5a3e83c9-8788-431e-85b0-a68c79377ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdf00b47360341e2b9a99654482d65be83b86503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654570"
---
# <a name="defining-a-data-source"></a><span data-ttu-id="85caf-102">Определение источника данных</span><span class="sxs-lookup"><span data-stu-id="85caf-102">Defining a Data Source</span></span>
  <span data-ttu-id="85caf-103">После создания проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] работа с проектом обычно начинается с определения одного или нескольких источников данных, которые будут использоваться в этом проекте.</span><span class="sxs-lookup"><span data-stu-id="85caf-103">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you generally start working with the project by defining one or more data sources that the project will use.</span></span> <span data-ttu-id="85caf-104">Для определения источника данных нужно задать строку соединения, которая будет использована для подключения к этому источнику данных.</span><span class="sxs-lookup"><span data-stu-id="85caf-104">When you define a data source, you are defining the connection string information that will be used to connect to the data source.</span></span> <span data-ttu-id="85caf-105">Дополнительные сведения см. в разделе [Создание источника данных (многомерные службы SSAS)](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="85caf-105">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="85caf-106">В следующей задаче предстоит определить образец базы данных AdventureWorksDWSQLServer2012 в качестве источника данных для проекта учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85caf-106">In the following task, you define the AdventureWorksDWSQLServer2012 sample database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="85caf-107">Хотя эта база данных в данном случае расположена на локальном компьютере, часто исходные базы данных размещаются на одном или нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="85caf-107">While this database is located on your local computer for the purposes of this tutorial, source databases are frequently hosted on one or more remote computers.</span></span>  
  
### <a name="to-define-a-new-data-source"></a><span data-ttu-id="85caf-108">Определение нового источника данных</span><span class="sxs-lookup"><span data-stu-id="85caf-108">To define a new data source</span></span>  
  
1.  <span data-ttu-id="85caf-109">В обозревателе решений (справа от окна Microsoft Visual Studio) щелкните правой кнопкой мыши папку **Источники данных**и выберите пункт **Создать источник данных**.</span><span class="sxs-lookup"><span data-stu-id="85caf-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Sources**, and then click **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="85caf-110">На странице **Мастер источников данных** в **мастере источников данных**нажмите кнопку **Далее** , чтобы открыть страницу **Выбор метода определения соединения** .</span><span class="sxs-lookup"><span data-stu-id="85caf-110">On the **Welcome to the Data Source Wizard** page of the **Data Source Wizard**, click **Next** to open the **Select how to define the connection** page.</span></span>  
  
3.  <span data-ttu-id="85caf-111">На странице **Выбор метода определения соединения** можно определить источник данных на основе нового соединения, существующего соединения или предварительно определенного объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="85caf-111">On the **Select how to define the connection** page, you can define a data source based on a new connection, based on an existing connection, or based on a previously defined data source object.</span></span> <span data-ttu-id="85caf-112">В этом учебнике будет определен источник данных на основе нового соединения.</span><span class="sxs-lookup"><span data-stu-id="85caf-112">In this tutorial, you define a data source based on a new connection.</span></span> <span data-ttu-id="85caf-113">Убедитесь в том, что выбран параметр **Создать источник данных, основанный на существующем или на новом соединении** , а затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="85caf-113">Verify that **Create a data source based on an existing or new connection** is selected, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="85caf-114">В диалоговом окне **Диспетчер соединений** определяются свойства соединения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="85caf-114">In the **Connection Manager** dialog box, you define connection properties for the data source.</span></span> <span data-ttu-id="85caf-115">Убедитесь в том, что в списке **Поставщик** выбран **Собственный поставщик данных OLE DB\Собственный клиент SQL Server 11.0** .</span><span class="sxs-lookup"><span data-stu-id="85caf-115">In the **Provider** list box, verify that **Native OLE DB\SQL Server Native Client 11.0** is selected.</span></span>  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="85caf-116">также поддерживают других поставщиков, которые доступны в списке **Поставщик** .</span><span class="sxs-lookup"><span data-stu-id="85caf-116">also supports other providers, which are displayed in the **Provider** list.</span></span>  
  
5.  <span data-ttu-id="85caf-117">В текстовом поле **имя сервера** введите `localhost` .</span><span class="sxs-lookup"><span data-stu-id="85caf-117">In the **Server name** text box, type `localhost`.</span></span>  
  
     <span data-ttu-id="85caf-118">Чтобы подключиться к именованному экземпляру на локальном компьютере, введите **localhost \\<\> имя экземпляра**.</span><span class="sxs-lookup"><span data-stu-id="85caf-118">To connect to a named instance on your local computer, type **localhost\\<instance name\>**.</span></span> <span data-ttu-id="85caf-119">Чтобы подключиться к конкретному компьютеру вместо локального, введите имя компьютера или его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="85caf-119">To connect to the specific computer instead of the local computer, type the computer name or IP address.</span></span>  
  
6.  <span data-ttu-id="85caf-120">Убедитесь в том, что выбран параметр **Использовать проверку подлинности Windows** .</span><span class="sxs-lookup"><span data-stu-id="85caf-120">Verify that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="85caf-121">В поле списка **Выберите или введите имя базы данных** выберите **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="85caf-121">In the **Select or enter a database name** list, select **AdventureWorksDW2012**.</span></span>  
  
7.  <span data-ttu-id="85caf-122">Нажмите кнопку **Проверить соединение** , чтобы проверить соединение с базой данных.</span><span class="sxs-lookup"><span data-stu-id="85caf-122">Click **Test Connection** to test the connection to the database.</span></span>  
  
8.  <span data-ttu-id="85caf-123">Нажмите кнопку **ОК** и затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85caf-123">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="85caf-124">На странице мастера **Сведения об олицетворении** определяются учетные данные безопасности, которые будут использованы в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="85caf-124">On the **Impersonation Information** page of the wizard, you define the security credentials for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use to connect to the data source.</span></span> <span data-ttu-id="85caf-125">Олицетворение влияет на учетную запись Windows, которая используется для подключения к источнику данных при выборе проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="85caf-125">Impersonation affects the Windows account used to connect to the data source when Windows Authentication is selected.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="85caf-126">не поддерживает олицетворение для обработки объектов OLAP.</span><span class="sxs-lookup"><span data-stu-id="85caf-126">does not support impersonation for processing OLAP objects.</span></span> <span data-ttu-id="85caf-127">Выберите параметр **Использовать учетную запись службы**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="85caf-127">Select **Use the service account**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="85caf-128">На странице **Завершение работы мастера** примите имя по умолчанию **Adventure Works DW 2012**, а затем нажмите кнопку **Готово** , чтобы создать источник данных.</span><span class="sxs-lookup"><span data-stu-id="85caf-128">On the **Completing the Wizard** page, accept the default name, **Adventure Works DW 2012**, and then click **Finish** to create the new data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85caf-129">Чтобы изменить свойства существующего источника данных, дважды щелкните этот источник в папке **Источники данных** , чтобы показать свойства источника данных в **конструкторе источников данных**.</span><span class="sxs-lookup"><span data-stu-id="85caf-129">To modify the properties of the data source after it has been created, double-click the data source in the **Data Sources** folder to display the data source properties in **Data Source Designer**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="85caf-130">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="85caf-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="85caf-131">Определение представления источников данных</span><span class="sxs-lookup"><span data-stu-id="85caf-131">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="85caf-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="85caf-132">See Also</span></span>  
 [<span data-ttu-id="85caf-133">Создание источника данных (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="85caf-133">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  
  
