---
title: Занятие 1. Создание образца базы данных подписчика | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6ee49f0858b28c0c4b00fd391b0db7b4d2c54b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751808"
---
# <a name="lesson-1-creating-a-sample-subscriber-database"></a><span data-ttu-id="e7e04-102">Занятие 1. Создание образца базы данных подписчика</span><span class="sxs-lookup"><span data-stu-id="e7e04-102">Lesson 1: Creating a Sample Subscriber Database</span></span>
  <span data-ttu-id="e7e04-103">Для определения управляемой данными подписки нужен источник данных, предоставляющий данные подписки.</span><span class="sxs-lookup"><span data-stu-id="e7e04-103">Before you can define a data-driven subscription, you must have a data source that provides subscription data.</span></span> <span data-ttu-id="e7e04-104">На этом этапе будет создана небольшая база данных для хранения данных подписки, используемых при работе с этим учебником.</span><span class="sxs-lookup"><span data-stu-id="e7e04-104">In this step, you will create a small database to store the subscription data used in this tutorial.</span></span> <span data-ttu-id="e7e04-105">Позже, после обработки подписки, сервер отчетов получит эти данные и использует их для настройки выходных данных отчетов, параметров доставки и формата представления отчетов.</span><span class="sxs-lookup"><span data-stu-id="e7e04-105">Later, when the subscription is processed, the report server retrieves this data and uses it to customize report output, delivery options, and report presentation format.</span></span>  
  
 <span data-ttu-id="e7e04-106">В этом занятии предполагается, что вы используете [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] для создания [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] базы данных.</span><span class="sxs-lookup"><span data-stu-id="e7e04-106">This lesson assumes you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to create a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span>  
  
### <a name="to-create-a-sample-subscriber-database"></a><span data-ttu-id="e7e04-107">Создание образца базы данных подписчика</span><span class="sxs-lookup"><span data-stu-id="e7e04-107">To create a sample Subscriber database</span></span>  
  
1.  <span data-ttu-id="e7e04-108">Запустите среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] и установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7e04-108">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and open a connection to a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7e04-109">Щелкните правой кнопкой мыши "Базы данных" и выберите команду **Создать базу данных...**</span><span class="sxs-lookup"><span data-stu-id="e7e04-109">Right-click on Databases, select **New Database...**.</span></span>  
  
3.  <span data-ttu-id="e7e04-110">В диалоговом окне Создание базы данных в поле Имя базы данных введите *Подписчики*.</span><span class="sxs-lookup"><span data-stu-id="e7e04-110">In the New Database dialog box, in Database Name, type *Subscribers*.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="e7e04-111">Нажмите кнопку **Создать запрос** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e7e04-111">Click the **New Query** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="e7e04-112">Скопируйте следующие инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] в пустой запрос:</span><span class="sxs-lookup"><span data-stu-id="e7e04-112">Copy the following [!INCLUDE[tsql](../includes/tsql-md.md)] statements into the empty query:</span></span>  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
6.  <span data-ttu-id="e7e04-113">Нажмите кнопку **! Выполнить** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e7e04-113">Click **! Execute** on the toolbar.</span></span>  
  
7.  <span data-ttu-id="e7e04-114">С помощью инструкции SELECT удостоверьтесь, что создано три строки данных.</span><span class="sxs-lookup"><span data-stu-id="e7e04-114">Use a SELECT statement to verify that you have three rows of data.</span></span> <span data-ttu-id="e7e04-115">Например: `select * from OrderInfo`</span><span class="sxs-lookup"><span data-stu-id="e7e04-115">For example: `select * from OrderInfo`</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e7e04-116">Next Steps</span><span class="sxs-lookup"><span data-stu-id="e7e04-116">Next Steps</span></span>  
 <span data-ttu-id="e7e04-117">Успешно завершено создание данных подписки, которые будут управлять распространением отчетов и изменять выходные данные отчетов в соответствии с параметрами настройки для каждого из подписчиков.</span><span class="sxs-lookup"><span data-stu-id="e7e04-117">You have successfully created the subscription data that will drive report distribution and vary the report output for each subscriber.</span></span> <span data-ttu-id="e7e04-118">Далее предстоит изменить свойства источника данных отчета, который будет распространяться среди подписчиков.</span><span class="sxs-lookup"><span data-stu-id="e7e04-118">Next, you will modify the data source properties of the report you will distribute to subscribers.</span></span> <span data-ttu-id="e7e04-119">Изменение свойств источника данных нужно, чтобы подготовить отчет для распространения управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="e7e04-119">Modifying the data source properties is done to prepare the report for data-driven subscription delivery.</span></span> <span data-ttu-id="e7e04-120">Вы также измените конструкцию отчета, включив в нее параметр, который будет использоваться подпиской с данными подписчика.</span><span class="sxs-lookup"><span data-stu-id="e7e04-120">You will also modify the report design to include a parameter that the subscription will use with the subscriber data.</span></span> <span data-ttu-id="e7e04-121">[Занятие 2. изменение свойств источника данных отчета](lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e7e04-121">[Lesson 2: Modifying the Report Data Source Properties](lesson-2-modifying-the-report-data-source-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e04-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="e7e04-122">See Also</span></span>  
 <span data-ttu-id="e7e04-123">[Создание управляемой данными подписки (учебник по службам SSRS)](create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="e7e04-123">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="e7e04-124">[Создание базы данных](../relational-databases/databases/create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="e7e04-124">[Create a Database](../relational-databases/databases/create-a-database.md) </span></span>  
 [<span data-ttu-id="e7e04-125">Создание простого табличного отчета (учебник по службам SSRS)</span><span class="sxs-lookup"><span data-stu-id="e7e04-125">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
