---
title: Задача 7. Добавление преобразования очистки DQS в поток данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0b749c71-dfb6-493a-804f-600290d46eef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 887bc361a51b61e9137404e054bd52e2b630ca5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656091"
---
# <a name="task-7-adding-dqs-cleansing-transform-to-the-data-flow"></a><span data-ttu-id="6c993-102">Задача 7. Добавление в поток данных преобразования "Очистка DQS"</span><span class="sxs-lookup"><span data-stu-id="6c993-102">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>
  <span data-ttu-id="6c993-103">В этой задаче вы добавите преобразование очистки DQS в поток данных для очистки входных данных о поставщиках с помощью служб DQS.</span><span class="sxs-lookup"><span data-stu-id="6c993-103">In this task, you add DQS Cleansing Transform to the data flow to cleanse the input supplier data by using DQS.</span></span> <span data-ttu-id="6c993-104">Дополнительные сведения о преобразовании см. в разделе **[Преобразование очистки DQS](https://msdn.microsoft.com/library/ee677619.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="6c993-104">See **[DQS Cleansing Transform](https://msdn.microsoft.com/library/ee677619.aspx)** for more details about the transform.</span></span>  
  
1.  <span data-ttu-id="6c993-105">Щелкните правой кнопкой мыши **Очистка DQS** на вкладке **поток данных** и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="6c993-105">Right-click **DQS Cleansing** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="6c993-106">Введите **Очистка данных поставщика**и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="6c993-106">Type **Cleanse Supplier Data**, and press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="6c993-107">Выберите **Чтение данных поставщика из файла Excel**. Перетащите синий соединитель, чтобы **Очистить данные поставщика**.</span><span class="sxs-lookup"><span data-stu-id="6c993-107">Select **Read Supplier Data from Excel File**; drag the blue connector to **Cleanse Supplier Data**.</span></span> <span data-ttu-id="6c993-108">Теперь компоненты соединены.</span><span class="sxs-lookup"><span data-stu-id="6c993-108">The components are now connected.</span></span>  
  
     <span data-ttu-id="6c993-109">![Чтение данных поставщика. > очистки данных поставщика](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Чтение данных поставщика —> очистка данных поставщика")</span><span class="sxs-lookup"><span data-stu-id="6c993-109">![Read Supplier Data -> Cleanse Supplier Data](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Read Supplier Data -> Cleanse Supplier Data")</span></span>  
  
3.  <span data-ttu-id="6c993-110">Дважды щелкните **Очистить данные поставщика**.</span><span class="sxs-lookup"><span data-stu-id="6c993-110">Double-click **Cleanse Supplier Data**.</span></span>  
  
4.  <span data-ttu-id="6c993-111">В **редакторе преобразования «Очистка DQS**» нажмите кнопку **создать** рядом с раскрывающимся **списком диспетчер соединений Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="6c993-111">In the **DQS Cleansing Transformation Editor**, click **New** next to the **Data Quality Connection Manager drop-down list**.</span></span>  
  
5.  <span data-ttu-id="6c993-112">В диалоговом окне **Диспетчер соединений "Очистка DQS** " введите **(local)** или **period** (.) для подключения к локальному серверу.</span><span class="sxs-lookup"><span data-stu-id="6c993-112">In the **DQS Cleansing Connection Manager** dialog box, type **(local)** or **period** (.) to connect to the local server.</span></span> <span data-ttu-id="6c993-113">В этом занятии предполагается, что службы DQS установлены на локальном сервере.</span><span class="sxs-lookup"><span data-stu-id="6c993-113">This lesson assumes that you have DQS installed on a local server.</span></span>  
  
6.  <span data-ttu-id="6c993-114">Нажмите кнопку **проверить подключение** , чтобы проверить подключение к серверу DQS.</span><span class="sxs-lookup"><span data-stu-id="6c993-114">Click **Test Connection** to test the connection to DQS server.</span></span>  
  
7.  <span data-ttu-id="6c993-115">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="6c993-115">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="6c993-116">Выберите **поставщики** для базы **знаний качества данных**.</span><span class="sxs-lookup"><span data-stu-id="6c993-116">Select **Suppliers** for the **Data Quality Knowledge Base**.</span></span>  
  
     <span data-ttu-id="6c993-117">![Редактор преобразования «Очистка DQS» — база знаний о поставщиках](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "Редактор преобразования «Очистка DQS» — база знаний о поставщиках")</span><span class="sxs-lookup"><span data-stu-id="6c993-117">![DQS Cleansing Transformation Editor - Suppliers KB](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "DQS Cleansing Transformation Editor - Suppliers KB")</span></span>  
  
9. <span data-ttu-id="6c993-118">Перейдите на вкладку **сопоставление** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="6c993-118">Switch to the **Mapping** tab at the top.</span></span>  
  
10. <span data-ttu-id="6c993-119">На странице **Доступные входные столбцы**выберите **имя поставщика**, **ContactEmailAddress**, **строку адреса**, **город**, **штат**, **страна**и **почтовый индекс** , установив флажки.</span><span class="sxs-lookup"><span data-stu-id="6c993-119">From **Available Input Columns**, select **Supplier Name**, **ContactEmailAddress**, **Address Line**, **City**, **State**, **Country**, and **Zip Code** by selecting the check boxes.</span></span>  
  
     <span data-ttu-id="6c993-120">![Редактор преобразования «Очистка DQS» — сопоставления](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "Редактор преобразования «Очистка DQS» — сопоставления")</span><span class="sxs-lookup"><span data-stu-id="6c993-120">![DQS Cleansing Transformation Editor - Mappings](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "DQS Cleansing Transformation Editor - Mappings")</span></span>  
  
11. <span data-ttu-id="6c993-121">В нижней области Сопоставьте эти столбцы с помощью раскрывающихся списков в столбце **домен** .</span><span class="sxs-lookup"><span data-stu-id="6c993-121">In the bottom pane, map these columns by using drop-down lists in the **Domain** column:</span></span>  
  
    |<span data-ttu-id="6c993-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="6c993-122">Column</span></span>|<span data-ttu-id="6c993-123">Домен</span><span class="sxs-lookup"><span data-stu-id="6c993-123">Domain</span></span>|  
    |------------|------------|  
    |<span data-ttu-id="6c993-124">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="6c993-124">Supplier Name</span></span>|<span data-ttu-id="6c993-125">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="6c993-125">Supplier Name</span></span>|  
    |<span data-ttu-id="6c993-126">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="6c993-126">ContactEmailAddress</span></span>|<span data-ttu-id="6c993-127">Контактный адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="6c993-127">Contact Email</span></span>|  
    |<span data-ttu-id="6c993-128">Строка адреса</span><span class="sxs-lookup"><span data-stu-id="6c993-128">Address Line</span></span>|<span data-ttu-id="6c993-129">Строка адреса</span><span class="sxs-lookup"><span data-stu-id="6c993-129">Address Line</span></span>|  
    |<span data-ttu-id="6c993-130">Город</span><span class="sxs-lookup"><span data-stu-id="6c993-130">City</span></span>|<span data-ttu-id="6c993-131">Город</span><span class="sxs-lookup"><span data-stu-id="6c993-131">City</span></span>|  
    |<span data-ttu-id="6c993-132">Состояние</span><span class="sxs-lookup"><span data-stu-id="6c993-132">State</span></span>|<span data-ttu-id="6c993-133">Состояние</span><span class="sxs-lookup"><span data-stu-id="6c993-133">State</span></span>|  
    |<span data-ttu-id="6c993-134">Страна или регион</span><span class="sxs-lookup"><span data-stu-id="6c993-134">Country</span></span>|<span data-ttu-id="6c993-135">Страна или регион</span><span class="sxs-lookup"><span data-stu-id="6c993-135">Country</span></span>|  
    |<span data-ttu-id="6c993-136">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="6c993-136">Zip Code</span></span>|<span data-ttu-id="6c993-137">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="6c993-137">Zip</span></span>|  
  
12. <span data-ttu-id="6c993-138">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор преобразования «Очистка DQS** ».</span><span class="sxs-lookup"><span data-stu-id="6c993-138">Click **OK** to close the **DQS Cleansing Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6c993-139">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="6c993-139">Next Step</span></span>  
 [<span data-ttu-id="6c993-140">Задача 8. Добавление преобразования "Условное разбиение" для выходных данных очистки</span><span class="sxs-lookup"><span data-stu-id="6c993-140">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>](../../2014/tutorials/task-8-adding-conditional-split-transform-to-split-cleansing-output.md)  
  
  
