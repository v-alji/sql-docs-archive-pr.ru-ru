---
title: Задача 6. Импорт значений из проекта очистки списка поставщиков | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fec0deef-a729-4ff1-b709-72d2b3f407ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b674cfb42ddf31c3b903a465d1be1b04e9a355ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656097"
---
# <a name="task-6-importing-values-from-the-cleanse-supplier-list-project"></a><span data-ttu-id="8dd6d-102">Задача 6. Импорт значений из проекта очистки списка поставщиков</span><span class="sxs-lookup"><span data-stu-id="8dd6d-102">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>
  <span data-ttu-id="8dd6d-103">В этой задаче вы импортируете наборы знаний служб DQS, полученные в процессе очистки.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-103">In this task, you import the data quality knowledge gathered during the cleansing process.</span></span> <span data-ttu-id="8dd6d-104">Дополнительные сведения см. в разделе [Импорт значений проекта очистки в домен](https://msdn.microsoft.com/library/hh479581.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8dd6d-104">See [Importing Cleansing Project Values into a Domain](https://msdn.microsoft.com/library/hh479581.aspx) topic for more details.</span></span> <span data-ttu-id="8dd6d-105">Вы также экспортируете базу знаний в файл служб DQS перед публикацией обновленной базы знаний **Поставщики** .</span><span class="sxs-lookup"><span data-stu-id="8dd6d-105">You also export the knowledge base into a DQS file before publishing the updated **Suppliers** knowledge base.</span></span>  
  
1.  <span data-ttu-id="8dd6d-106">На главной странице **клиента DQS**щелкните **правой кнопкой** рядом с элементом **Поставщики** в разделе **Последние базы знаний** и выберите команду **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** under **Recent Knowledge Bases** and click **Domain Management**.</span></span>  
  
2.  <span data-ttu-id="8dd6d-107">Выберите **Адрес электронной почты** в списке доменов и перейдите на вкладку **Значения домена** в правой области.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-107">Click **Contact Email** in the list of domains, and switch to the **Domain Values** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="8dd6d-108">Щелкните **стрелку вниз** рядом со значком **Импортировать значения** на панели инструментов и выберите команду **Импорт значений проекта**.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-108">Click **down arrow** next to the **Import Values** icon on the toolbar and click **Import Project Values**.</span></span>  
  
     <span data-ttu-id="8dd6d-109">![Кнопка панели инструментов «Импорт значений проекта»](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Кнопка панели инструментов «Импорт значений проекта»")</span><span class="sxs-lookup"><span data-stu-id="8dd6d-109">![Import Project Values Toolbar Button](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Import Project Values Toolbar Button")</span></span>  
  
4.  <span data-ttu-id="8dd6d-110">В диалоговом окне **Импорт значений проекта** выберите проект **Очистка списка поставщиков** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-110">In the **Import Project Values** dialog box, select the **Cleanse Supplier List** project, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="8dd6d-111">Обратите внимание, что все сообщения электронной почты импортируется вместе с двумя изменениями, внесенными во время интерактивной очистки.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-111">Notice that all the emails are imported along with the two corrections you did during interactive cleansing.</span></span> <span data-ttu-id="8dd6d-112">Прокрутите экран вниз, чтобы просмотреть исправления.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-112">Scroll to see the two corrections.</span></span>  
  
    |<span data-ttu-id="8dd6d-113">Значение</span><span class="sxs-lookup"><span data-stu-id="8dd6d-113">Value</span></span>|<span data-ttu-id="8dd6d-114">Исправить на</span><span class="sxs-lookup"><span data-stu-id="8dd6d-114">Correct To</span></span>|  
    |-----------|----------------|  
    |bobby0@adventure-work.com|bobby0@adventure-works.com|  
    |tad0@adventure-work.com|tad0@adventure-works.com|  
  
6.  <span data-ttu-id="8dd6d-115">Повторите предыдущий шаг импорта значений проекта для домена **Country** и обратите внимание, что добавлена новая запись для исправления **соединенных** Штатов в **США** (With ').</span><span class="sxs-lookup"><span data-stu-id="8dd6d-115">Repeat the previous step of importing project values for the **Country** domain and notice that a new entry is added for correcting **United State** to **United States** (with 's').</span></span>  
  
    |<span data-ttu-id="8dd6d-116">Значение</span><span class="sxs-lookup"><span data-stu-id="8dd6d-116">Value</span></span>|<span data-ttu-id="8dd6d-117">Исправить на</span><span class="sxs-lookup"><span data-stu-id="8dd6d-117">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="8dd6d-118">United State</span><span class="sxs-lookup"><span data-stu-id="8dd6d-118">United State</span></span>|<span data-ttu-id="8dd6d-119">США</span><span class="sxs-lookup"><span data-stu-id="8dd6d-119">United States</span></span>|  
  
7.  <span data-ttu-id="8dd6d-120">Чтобы увидеть старые значения домена, снимите флажок **Показать только новые** .</span><span class="sxs-lookup"><span data-stu-id="8dd6d-120">To see the old domain values, clear **Show Only New** checkbox.</span></span>  
  
8.  <span data-ttu-id="8dd6d-121">Повторите предыдущий шаг импорта значений проекта для домена **Имя поставщика** .</span><span class="sxs-lookup"><span data-stu-id="8dd6d-121">Repeat the previous step of importing project values for the **Supplier Name** domain.</span></span> <span data-ttu-id="8dd6d-122">По умолчанию после импорта вы увидите только новые значения.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-122">By default, after importing, you will only see the new values.</span></span> <span data-ttu-id="8dd6d-123">Чтобы увидеть все значения, снимите флажок **Показать только новые** .</span><span class="sxs-lookup"><span data-stu-id="8dd6d-123">To see all the values, clear **Show Only New** check box.</span></span> <span data-ttu-id="8dd6d-124">Вы обогатили базу знаний **Поставщики** информацией, которую получили после очистки.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-124">You have enriched the **Suppliers** knowledge base with what you learned from the cleansing activity.</span></span> <span data-ttu-id="8dd6d-125">Чем надежнее база знаний, тем лучше результаты очистки.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-125">The stronger the knowledge base is, the better the cleansing results are.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dd6d-126">Нельзя импортировать значения для составного домена.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-126">It is not possible import values for a composite domain.</span></span>  
  
9. <span data-ttu-id="8dd6d-127">Щелкните значок **Экспортировать базу знаний** на панели инструментов и нажмите кнопку **Экспортировать базу знаний**.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-127">Click **Export Knowledge Base** icon on the toolbar and then click **Export Knowledge Base**.</span></span>  
  
     <span data-ttu-id="8dd6d-128">![Меню «Экспортировать базу знаний»](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Меню «Экспортировать базу знаний»")</span><span class="sxs-lookup"><span data-stu-id="8dd6d-128">![Export Knowledge Base Menu](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Export Knowledge Base Menu")</span></span>  
  
10. <span data-ttu-id="8dd6d-129">Перейдите в папку Tutorial, введите **Suppliers.dqs** как **имя файла**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-129">Navigate to the Tutorial folder, type **Suppliers.dqs** for the **file name**, and click **Save**.</span></span> <span data-ttu-id="8dd6d-130">Этот DQS-файл можно использовать для создания новой базы знаний на его основе.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-130">You can use this DQS file to create a new knowledge base based on it.</span></span>  
  
11. <span data-ttu-id="8dd6d-131">Нажмите кнопку **ОК** , чтобы закрыть окно **экспортировать базу знаний — поставщики** .</span><span class="sxs-lookup"><span data-stu-id="8dd6d-131">Click **OK** to close the **Export Knowledge Base - Suppliers** message box.</span></span>  
  
12. <span data-ttu-id="8dd6d-132">Нажмите кнопку **Готово** , чтобы завершить работу.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-132">Click **Finish** to finish the activity.</span></span>  
  
13. <span data-ttu-id="8dd6d-133">Щелкните **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-133">Click **Publish**.</span></span>  
  
14. <span data-ttu-id="8dd6d-134">Нажмите кнопку **ОК** в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="8dd6d-134">Click **OK** on the message box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8dd6d-135">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8dd6d-135">Next Step</span></span>  
 [<span data-ttu-id="8dd6d-136">Урок 3. Сопоставление данных для удаления повторов из списка поставщиков</span><span class="sxs-lookup"><span data-stu-id="8dd6d-136">Lesson 3: Matching Data to Remove Duplicates from Supplier List</span></span>](../../2014/tutorials/lesson-3-matching-data-to-remove-duplicates-from-supplier-list.md)  
  
  
