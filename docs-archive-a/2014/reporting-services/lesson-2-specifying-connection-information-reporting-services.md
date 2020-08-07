---
title: Занятие 2. Задание информации о соединении (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c187f0abdc4b277a5f1428407b5c42ca4fd6fee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731426"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a><span data-ttu-id="39454-102">Занятие 2. Задание информации о соединении (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="39454-102">Lesson 2: Specifying Connection Information (Reporting Services)</span></span>
  <span data-ttu-id="39454-103">После добавления отчета к проекту Tutorial следует задать *источник данных*, который представляет собой сведения о соединении, используемые отчетом для доступа к данным, которые располагаются в реляционной базе данных, многомерной базе данных или ином ресурсе.</span><span class="sxs-lookup"><span data-stu-id="39454-103">After you add a report to the Tutorial project, you need to define a *data source*, which is connection information the report uses to access data from either a relational database, multidimensional database, or other resource.</span></span>  
  
 <span data-ttu-id="39454-104">В этом занятии в качестве источника данных используется образец базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39454-104">In this lesson, you will use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database as your data source.</span></span> <span data-ttu-id="39454-105">В этом учебнике предполагается, что эта база данных находится в экземпляре по умолчанию [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] , установленном на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="39454-105">This tutorial assumes that this database is located in a default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed on your local computer.</span></span>  
  
### <a name="to-set-up-a-connection"></a><span data-ttu-id="39454-106">Настройка соединения</span><span class="sxs-lookup"><span data-stu-id="39454-106">To set up a connection</span></span>  
  
1.  <span data-ttu-id="39454-107">В области **данных отчета** нажмите кнопку **создать** , а затем выберите **источник данных..**..</span><span class="sxs-lookup"><span data-stu-id="39454-107">In the **Report Data** pane, click **New** and then click **Data Source...**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39454-108">Если область **Данные отчета** не отображается, в меню **Вид** выберите пункт **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="39454-108">If the **Report Data** pane is not visible, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="39454-109">В поле **Имя**введите [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39454-109">In **Name**, type [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span></span>  
  
3.  <span data-ttu-id="39454-110">Убедитесь в том, что выбран параметр **Внедренное соединение** .</span><span class="sxs-lookup"><span data-stu-id="39454-110">Make sure **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="39454-111">В поле **Тип**выберите **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="39454-111">In **Type**, select **Microsoft SQL Server**.</span></span>  
  
5.  <span data-ttu-id="39454-112">В поле **Строка подключения**введите следующее:</span><span class="sxs-lookup"><span data-stu-id="39454-112">In **Connection string**, type the following:</span></span>  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     <span data-ttu-id="39454-113">Эта строка соединения подразумевает, что на локальном компьютере установлены среда [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], сервер отчетов и база данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , а у пользователя имеется разрешение на подключение к базе данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39454-113">This connection string assumes that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the report server, and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database are all installed on the local computer and that you have permission to log on to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39454-114">В случае использования версии [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services или именованного экземпляра строка соединения должна включать сведения об экземпляре:</span><span class="sxs-lookup"><span data-stu-id="39454-114">If you are using [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services or a named instance, the connection string must include instance information:</span></span>  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  <span data-ttu-id="39454-115">Дополнительные сведения о строках подключения см. [в разделе подключения к данным, источники данных и строки подключения в Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) и [диалоговом окне Свойства источника данных — Общие](data-source-properties-dialog-box-general.md).</span><span class="sxs-lookup"><span data-stu-id="39454-115">For more information about connection strings, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) and [Data Source Properties Dialog Box, General](data-source-properties-dialog-box-general.md).</span></span>  
  
6.  <span data-ttu-id="39454-116">На панели слева щелкните **Учетные данные** и выберите **Использовать проверку подлинности Windows (встроенная безопасность)**.</span><span class="sxs-lookup"><span data-stu-id="39454-116">Click **Credentials** in the left pane and click **Use Windows Authentication (integrated security)**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="39454-117">Источник данных [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] добавляется в область **данных отчета** .</span><span class="sxs-lookup"><span data-stu-id="39454-117">data source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] is added to the **Report Data** pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="39454-118">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="39454-118">Next Task</span></span>  
 <span data-ttu-id="39454-119">Соединение с образцом базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] успешно создано.</span><span class="sxs-lookup"><span data-stu-id="39454-119">You have successfully defined a connection to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="39454-120">Далее предстоит создать отчет.</span><span class="sxs-lookup"><span data-stu-id="39454-120">Next, you will create the report.</span></span> <span data-ttu-id="39454-121">См. [Занятие 3. Определение набора данных для табличного отчета (службы Reporting Services)](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="39454-121">See [Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39454-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="39454-122">See Also</span></span>  
 [<span data-ttu-id="39454-123">Подключения данных, Источники данных и Строки подключения в службе Reporting Services</span><span class="sxs-lookup"><span data-stu-id="39454-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
