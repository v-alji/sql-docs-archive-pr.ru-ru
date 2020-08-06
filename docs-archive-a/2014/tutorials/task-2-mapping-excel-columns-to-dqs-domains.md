---
title: Задача 2. Сопоставление столбцов Excel с доменами DQS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667506"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a><span data-ttu-id="30a9a-102">Задача 2. Сопоставление столбцов Excel с доменами DQS</span><span class="sxs-lookup"><span data-stu-id="30a9a-102">Task 2: Mapping Excel Columns to DQS Domains</span></span>
    
1.  <span data-ttu-id="30a9a-103">На странице **Сопоставление** выберите **Файл Excel** как **Источник данных**.</span><span class="sxs-lookup"><span data-stu-id="30a9a-103">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
2.  <span data-ttu-id="30a9a-104">Нажмите кнопку **Обзор**, выберите **Suppliers.xlsx**и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="30a9a-104">Click **Browse**, select **Suppliers.xlsx**, and click **Open**.</span></span>  
  
3.  <span data-ttu-id="30a9a-105">Выберите **инкомингсупплиерс $** для **листа**.</span><span class="sxs-lookup"><span data-stu-id="30a9a-105">Select **IncomingSuppliers$** for the **Worksheet**.</span></span>  
  
4.  <span data-ttu-id="30a9a-106">Сопоставьте столбцы, как показано в следующей таблице и на следующем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="30a9a-106">Map columns as shown in the following table and screenshot.</span></span> <span data-ttu-id="30a9a-107">При создании сопоставлений для домена **состояния** нажмите кнопку **Добавить сопоставление столбцов** на панели инструментов, расположенной непосредственно над списком.</span><span class="sxs-lookup"><span data-stu-id="30a9a-107">When creating mappings for the **State** domain, click **Add a column mapping** button on the toolbar located just above the list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="30a9a-108">Для очистки не используется **идентификатор поставщика** (столбец или домен).</span><span class="sxs-lookup"><span data-stu-id="30a9a-108">You are not using **Supplier ID** column/domain for cleansing.</span></span> <span data-ttu-id="30a9a-109">Домен с **идентификатором поставщика** будет использоваться позже в действии сопоставления.</span><span class="sxs-lookup"><span data-stu-id="30a9a-109">You will use the **Supplier ID** domain later in the matching activity.</span></span>  
  
    |<span data-ttu-id="30a9a-110">Столбец Excel</span><span class="sxs-lookup"><span data-stu-id="30a9a-110">Excel column</span></span>|<span data-ttu-id="30a9a-111">Домен DQS</span><span class="sxs-lookup"><span data-stu-id="30a9a-111">DQS Domain</span></span>|  
    |------------------|----------------|  
    |<span data-ttu-id="30a9a-112">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="30a9a-112">Supplier Name</span></span>|<span data-ttu-id="30a9a-113">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="30a9a-113">Supplier Name</span></span>|  
    |<span data-ttu-id="30a9a-114">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="30a9a-114">ContactEmailAddress</span></span>|<span data-ttu-id="30a9a-115">Контактный адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="30a9a-115">Contact Email</span></span>|  
    |<span data-ttu-id="30a9a-116">Строка адреса</span><span class="sxs-lookup"><span data-stu-id="30a9a-116">Address Line</span></span>|<span data-ttu-id="30a9a-117">Строка адреса</span><span class="sxs-lookup"><span data-stu-id="30a9a-117">Address Line</span></span>|  
    |<span data-ttu-id="30a9a-118">Город</span><span class="sxs-lookup"><span data-stu-id="30a9a-118">City</span></span>|<span data-ttu-id="30a9a-119">Город</span><span class="sxs-lookup"><span data-stu-id="30a9a-119">City</span></span>|  
    |<span data-ttu-id="30a9a-120">Состояние</span><span class="sxs-lookup"><span data-stu-id="30a9a-120">State</span></span>|<span data-ttu-id="30a9a-121">Состояние</span><span class="sxs-lookup"><span data-stu-id="30a9a-121">State</span></span>|  
    |<span data-ttu-id="30a9a-122">Страна (нажмите кнопку **+ (добавить сопоставление столбцов)** , чтобы добавить строку)</span><span class="sxs-lookup"><span data-stu-id="30a9a-122">Country (Click **+(Add a column mapping)** toolbar to add a row)</span></span>|<span data-ttu-id="30a9a-123">Страна или регион</span><span class="sxs-lookup"><span data-stu-id="30a9a-123">Country</span></span>|  
    |<span data-ttu-id="30a9a-124">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="30a9a-124">Zip Code</span></span>|<span data-ttu-id="30a9a-125">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="30a9a-125">Zip</span></span>|  
  
     <span data-ttu-id="30a9a-126">![Сопоставление столбцов Excel с доменами](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Сопоставление столбцов Excel с доменами")</span><span class="sxs-lookup"><span data-stu-id="30a9a-126">![Mappings of Excel Columns to Domains](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappings of Excel Columns to Domains")</span></span>  
  
5.  <span data-ttu-id="30a9a-127">После сопоставления всех отдельных доменов в составном домене **Проверка адреса** составной домен автоматически участвует в процессе очистки.</span><span class="sxs-lookup"><span data-stu-id="30a9a-127">As you have mapped all the individual domains within the **Address Validation** composite domain, the composite domain automatically participates in the cleansing process.</span></span> <span data-ttu-id="30a9a-128">Нажмите кнопку **Просмотр/выбор составных доменов** , чтобы увидеть, что автоматически выбран составной домен **Проверка адреса** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="30a9a-128">Click **View/Select Composite Domains** button to see that the **Address Validation** composite domain is automatically selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="30a9a-129">![Диалоговое окно «Просмотр или выбор составных доменов»](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Диалоговое окно «Просмотр или выбор составных доменов»")</span><span class="sxs-lookup"><span data-stu-id="30a9a-129">![View/Select Composite Domains Dialog Box](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "View/Select Composite Domains Dialog Box")</span></span>  
  
6.  <span data-ttu-id="30a9a-130">Нажмите кнопку **Далее** , чтобы перейти на страницу **Очистка** .</span><span class="sxs-lookup"><span data-stu-id="30a9a-130">Click **Next** to switch to the **Cleanse** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="30a9a-131">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="30a9a-131">Next Step</span></span>  
 [<span data-ttu-id="30a9a-132">Задача 3. Очистка данных в базе знаний о поставщиках</span><span class="sxs-lookup"><span data-stu-id="30a9a-132">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
