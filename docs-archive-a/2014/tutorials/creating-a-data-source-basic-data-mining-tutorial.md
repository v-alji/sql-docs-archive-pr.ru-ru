---
title: Создание источника данных (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658002"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a><span data-ttu-id="8257c-102">Создание источника данных (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="8257c-102">Creating a Data Source (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="8257c-103">*Источник данных* — это подключение к данным, которое сохраняется и управляется в проекте и развертывается в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="8257c-103">A *data source* is a data connection that is saved and managed in your project and deployed to your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="8257c-104">Источник данных содержит, кроме обязательных свойств соединения, имя сервера и базы данных, где находится этот источник.</span><span class="sxs-lookup"><span data-stu-id="8257c-104">The data source contains the names of the server and database where your source data resides, in addition to any other required connection properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8257c-105">Имя базы данных [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8257c-105">The name of the database is [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="8257c-106">Если вы еще не установили эту базу данных, см. страницу [образцов баз данных Microsoft SQL](https://go.microsoft.com/fwlink/?LinkId=88417) .</span><span class="sxs-lookup"><span data-stu-id="8257c-106">If you have not already installed this database, see the [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) page.</span></span>  
  
### <a name="to-create-a-data-source"></a><span data-ttu-id="8257c-107">Создание источника данных</span><span class="sxs-lookup"><span data-stu-id="8257c-107">To create a data source</span></span>  
  
1.  <span data-ttu-id="8257c-108">В **Обозреватель решений**щелкните правой кнопкой мыши папку **Источники данных** и выберите пункт **создать источник данных**.</span><span class="sxs-lookup"><span data-stu-id="8257c-108">In **Solution Explorer**, right-click the **Data Sources** folder and select **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="8257c-109">На странице **Мастер источников данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8257c-109">On the **Welcome to the Data Source Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="8257c-110">На странице **Выбор способа определения соединения** нажмите кнопку **создать** , чтобы добавить соединение с [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] базой данных.</span><span class="sxs-lookup"><span data-stu-id="8257c-110">On the **Select how to define the connection** page, click **New** to add a connection to the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="8257c-111">В списке **поставщик** в **диспетчере соединений**выберите **собственный OLE DB \ Server Native Client 11,0**.</span><span class="sxs-lookup"><span data-stu-id="8257c-111">In the **Provider** list in **Connection Manager**, select **Native OLE DB\SQL Server Native Client 11.0**.</span></span>  
  
5.  <span data-ttu-id="8257c-112">В поле **имя сервера** введите или выберите имя сервера, на котором установлен [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8257c-112">In the **Server name** box, type or select the name of the server on which you installed [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span>  
  
     <span data-ttu-id="8257c-113">Например, введите **localhost** , если база данных размещена на локальном сервере.</span><span class="sxs-lookup"><span data-stu-id="8257c-113">For example, type **localhost** if the database is hosted on the local server.</span></span>  
  
6.  <span data-ttu-id="8257c-114">В поле **Вход** в группу серверов выберите **использовать проверку подлинности Windows**.</span><span class="sxs-lookup"><span data-stu-id="8257c-114">In the **Log onto the server** group, select **Use Windows Authentication**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8257c-115">Во всех случаях, где возможно, следует использовать проверку подлинности Windows, которая обеспечивает более защищенный метод проверки подлинности, чем проверка подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8257c-115">Whenever possible, implementers should use Windows Authentication, as it provides a more secure authentication method than SQL Server Authentication.</span></span> <span data-ttu-id="8257c-116">Однако проверка подлинности SQL Server обеспечивается для поддержки обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="8257c-116">However, SQL Server Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="8257c-117">Дополнительные сведения о методах проверки подлинности см. в статье [Подготовка учетных записей в конфигурации ядро СУБД](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="8257c-117">For more information about authentication methods, see [Database Engine Configuration - Account Provisioning](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span></span>  
  
7.  <span data-ttu-id="8257c-118">В списке **выберите или введите имя базы данных** выберите [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8257c-118">In the **Select or enter a database name** list, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8257c-119">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8257c-119">Click **Next**.</span></span>  
  
9. <span data-ttu-id="8257c-120">На странице **сведения об олицетворении** щелкните **использовать учетную запись службы**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8257c-120">On the **Impersonation Information** page, click **Use the service account**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="8257c-121">На странице **Завершение работы мастера** Обратите внимание, что по умолчанию источник данных называется Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="8257c-121">On the **Completing the Wizard** page, notice that, by default, the data source is named Adventure Works DW 2012.</span></span>  
  
10. <span data-ttu-id="8257c-122">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8257c-122">Click **Finish**.</span></span>  
  
     <span data-ttu-id="8257c-123">Новый источник данных, Adventure Works DW 2012, появится в папке **Источники данных** в Обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="8257c-123">The new data source, Adventure Works DW 2012, appears in the **Data Sources** folder in Solution Explorer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8257c-124">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8257c-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8257c-125">Создание представления источника данных &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="8257c-125">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="8257c-126">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8257c-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="8257c-127">Учебник по созданию Analysis Services проекта &#40;Basic Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="8257c-127">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="8257c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="8257c-128">See Also</span></span>  
 <span data-ttu-id="8257c-129">[Создание источника данных &#40;многомерных&#41;SSAS](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="8257c-129">[Create a Data Source &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span></span>  
 <span data-ttu-id="8257c-130">[Определение источника данных](../analysis-services/lesson-1-2-defining-a-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="8257c-130">[Defining a Data Source](../analysis-services/lesson-1-2-defining-a-data-source.md) </span></span>  
 [<span data-ttu-id="8257c-131">Задание параметров олицетворения (службы SSAS — многомерные)</span><span class="sxs-lookup"><span data-stu-id="8257c-131">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
