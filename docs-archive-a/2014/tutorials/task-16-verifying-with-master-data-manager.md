---
title: Задача 16. Проверка с помощью диспетчер основных данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 57ad9d3e-8f95-4df6-af01-c291ccf49164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d1649582f97e9e08691726745e4ba14b2f8226bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732214"
---
# <a name="task-16-verifying-with-master-data-manager"></a><span data-ttu-id="b6632-102">Задача 16. Проверка с помощью диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="b6632-102">Task 16: Verifying with Master Data Manager</span></span>
  <span data-ttu-id="b6632-103">В этой задаче вы проверите состояние пакетного задания, отправленного пакетом служб SSIS, и убедитесь, что данные были переданы на сервер MDS с помощью диспетчера основных данных.</span><span class="sxs-lookup"><span data-stu-id="b6632-103">In this task, you check the status of the batch job submitted by the SSIS package and verify that the data was uploaded to MDS server by using Master Data Manager.</span></span>  
  
1.  <span data-ttu-id="b6632-104">Запуск **Диспетчер основных данных** ( `http://localhost/MDS` ).</span><span class="sxs-lookup"><span data-stu-id="b6632-104">Launch **Master Data Manager** (`http://localhost/MDS`).</span></span> <span data-ttu-id="b6632-105">Если она уже открыта, щелкните **Microsoft SQL Server Master Data Services** в верхней части, чтобы перейти на **домашнюю страницу**.</span><span class="sxs-lookup"><span data-stu-id="b6632-105">If it is already open, click **Microsoft SQL Server Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="b6632-106">Щелкните **Управление интеграцией**.</span><span class="sxs-lookup"><span data-stu-id="b6632-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="b6632-107">Обратите внимание, что существует пакет с именем **еимбатч** , отправленный в списке.</span><span class="sxs-lookup"><span data-stu-id="b6632-107">Notice that there is a batch with named **EIMBatch** that you submitted in the list.</span></span> <span data-ttu-id="b6632-108">Щелкните **Импорт данных** в строке меню, если не отображается следующий экран.</span><span class="sxs-lookup"><span data-stu-id="b6632-108">Click **Import Data** on the menu bar if you do not see the following screen.</span></span>  
  
     <span data-ttu-id="b6632-109">![Пакет EIM](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "Пакет EIM")</span><span class="sxs-lookup"><span data-stu-id="b6632-109">![EIM Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM Batch")</span></span>  
  
4.  <span data-ttu-id="b6632-110">Вернитесь на домашнюю страницу, щелкнув **SQL Server 2012 Master Data Services** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="b6632-110">Switch back to the home page by click **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
5.  <span data-ttu-id="b6632-111">Убедитесь, что для **model** выбрана модель **поставщики** и **VERSION_1** выбрана **версия**, и нажмите кнопку **Обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="b6632-111">Make sure that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**, and click **Explorer**.</span></span>  
  
6.  <span data-ttu-id="b6632-112">Вы можете просмотреть данные, импортированные пакетом служб SSIS в MDS.</span><span class="sxs-lookup"><span data-stu-id="b6632-112">You can see the data SSIS package imported into MDS.</span></span> <span data-ttu-id="b6632-113">Данные должны быть очищены и не иметь повторяющихся значений **кода** (Примечание: столбец « **КодПоставщика** » в Excel соответствует атрибуту **Code** сущности «поставщик» в MDS).</span><span class="sxs-lookup"><span data-stu-id="b6632-113">The data should be cleansed and have no duplicates **Code** values (Note: **SupplierID** column in Excel corresponds to **Code** attribute of Supplier entity in MDS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b6632-114">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b6632-114">Next Step</span></span>  
 [<span data-ttu-id="b6632-115">Задача 17. Проверка проекта очистки DQS, созданного пакетом SSIS</span><span class="sxs-lookup"><span data-stu-id="b6632-115">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>](../../2014/tutorials/task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package.md)  
  
  
