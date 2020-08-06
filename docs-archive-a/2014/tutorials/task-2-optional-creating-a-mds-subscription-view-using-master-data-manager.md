---
title: 'Задача 2 (необязательно): создание представления подписки MDS с помощью диспетчер основных данных | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3da8219-e0cb-4848-95ca-285a76ec1ba9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 998436734ba5c3cf09cfe88f266a0908c0550abc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735598"
---
# <a name="task-2-optional-creating-a-mds-subscription-view-using-master-data-manager"></a><span data-ttu-id="23303-102">Задача 2 (необязательно). Создание представления подписки MDS с помощью диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="23303-102">Task 2 (Optional): Creating a MDS Subscription View using Master Data Manager</span></span>
  <span data-ttu-id="23303-103">В этой задаче вы создадите представление подписки, чтобы предоставить сущность **поставщик** в модели **поставщики** другим приложениям.</span><span class="sxs-lookup"><span data-stu-id="23303-103">In this task, you create a subscription view to expose the **Supplier** entity in the **Suppliers** model to other applications.</span></span> <span data-ttu-id="23303-104">Это представление в текущей версии учебника не используется.</span><span class="sxs-lookup"><span data-stu-id="23303-104">You do not consume this view in the current version of the tutorial.</span></span>  
  
1.  <span data-ttu-id="23303-105">Перейдите на главную страницу **Диспетчер основных данных** ( `http://localhost/MDS` ), щелкнув **SQL Server 2012 Master Data Services** сверху.</span><span class="sxs-lookup"><span data-stu-id="23303-105">Switch to the main page of **Master Data Manager** (`http://localhost/MDS`) by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
2.  <span data-ttu-id="23303-106">Щелкните **Управление интеграцией**.</span><span class="sxs-lookup"><span data-stu-id="23303-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="23303-107">В строке меню щелкните **создать представления** .</span><span class="sxs-lookup"><span data-stu-id="23303-107">Click **Create Views** on the menu bar.</span></span>  
  
     <span data-ttu-id="23303-108">![Кнопка «Добавить новое представление подписки»](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Кнопка «Добавить новое представление подписки»")</span><span class="sxs-lookup"><span data-stu-id="23303-108">![Add a New Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Add a New Subscription View Button")</span></span>  
  
4.  <span data-ttu-id="23303-109">Щелкните значок **+ (плюс)** на панели инструментов, чтобы создать представление подписки.</span><span class="sxs-lookup"><span data-stu-id="23303-109">Click **+ (Plus)** icon on the toolbar to create a subscription view.</span></span>  
  
5.  <span data-ttu-id="23303-110">В области **Создание представления подписки** введите **поставщики** для **имени представления подписки**.</span><span class="sxs-lookup"><span data-stu-id="23303-110">In the **Create Subscription View** pane, type **Suppliers** for **Subscription view name**.</span></span>  
  
6.  <span data-ttu-id="23303-111">Выберите **поставщики** для **модели**.</span><span class="sxs-lookup"><span data-stu-id="23303-111">Select **Suppliers** for **Model**.</span></span>  
  
7.  <span data-ttu-id="23303-112">Выберите **VERSION_1** для **версии**.</span><span class="sxs-lookup"><span data-stu-id="23303-112">Select **VERSION_1** for **Version**.</span></span>  
  
8.  <span data-ttu-id="23303-113">Выберите **поставщик** для **сущности**.</span><span class="sxs-lookup"><span data-stu-id="23303-113">Select **Supplier** for **Entity**.</span></span>  
  
9. <span data-ttu-id="23303-114">Выберите **конечные элементы** для **форматирования**.</span><span class="sxs-lookup"><span data-stu-id="23303-114">Select **Leaf members** for **Format**.</span></span>  
  
     <span data-ttu-id="23303-115">![Кнопка «Сохранить представление подписки»](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Кнопка «Сохранить представление подписки»")</span><span class="sxs-lookup"><span data-stu-id="23303-115">![Save Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Save Subscription View Button")</span></span>  
  
10. <span data-ttu-id="23303-116">Нажмите кнопку **сохранить** на панели инструментов, чтобы сохранить представление подписки.</span><span class="sxs-lookup"><span data-stu-id="23303-116">Click **Save** on the toolbar to save the subscription view.</span></span> <span data-ttu-id="23303-117">Это действие создает представление в SQL Server именованные **поставщики**.</span><span class="sxs-lookup"><span data-stu-id="23303-117">This action creates a view in SQL Server named **Suppliers**.</span></span> <span data-ttu-id="23303-118">Это можно проверить с помощью среды SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="23303-118">You can verify this using SQL Server Management Studio (SSMS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="23303-119">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="23303-119">Next Step</span></span>  
 [<span data-ttu-id="23303-120">Задача 3 &#40;необязательный&#41;: Просмотр представлений подписки</span><span class="sxs-lookup"><span data-stu-id="23303-120">Task 3 &#40;Optional&#41;: Reviewing the Subscription Views</span></span>](task-3-optional-reviewing-the-subscription-views.md)  
  
  
