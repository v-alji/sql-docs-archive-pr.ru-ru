---
title: Создание InfoObject | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3587a633-1c0b-4d63-a22a-6b2b93923c3a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 022f2d1e3fe10ae037ea379a02a18845b3a36107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667832"
---
# <a name="create-new-infoobject"></a><span data-ttu-id="a7683-102">Создание InfoObject</span><span class="sxs-lookup"><span data-stu-id="a7683-102">Create New InfoObject</span></span>
  <span data-ttu-id="a7683-103">Используйте диалоговое окно **Создание нового InfoObject** для создания нового InfoObject в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a7683-103">Use the **Create New InfoObject** dialog box to create a new InfoObject in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="a7683-104">Диалоговое окно **Создать InfoObject** можно открыть на странице **Диспетчер соединений** **Редактора назначений SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="a7683-104">You can open the **Create InfoObject** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="a7683-105">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a7683-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7683-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a7683-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a7683-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="a7683-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a7683-108">**Открытие диалогового окна «Создание нового InfoObject»**</span><span class="sxs-lookup"><span data-stu-id="a7683-108">**To open the Create New InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="a7683-109">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a7683-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="a7683-110">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a7683-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="a7683-111">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="a7683-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="a7683-112">На странице **Диспетчер соединений** в поле группы **Создание объектов SAP BW** выполните одно из следующих действий для создания InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, do one of the following steps to create an InfoObject:</span></span>  
  
    1.  <span data-ttu-id="a7683-113">Для создания InfoObject напрямую выберите **InfoObject**и щелкните **Создать** , чтобы открыть диалоговое окно **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a7683-113">To create an InfoObject directly, select **InfoObject**, and then click **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
    2.  <span data-ttu-id="a7683-114">Для создания InfoObject во время создания InfoCube выберите **InfoCube**, а затем щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a7683-114">To create an InfoObject while creating an InfoCube, select **InfoCube**, and then click **Create**.</span></span> <span data-ttu-id="a7683-115">В диалоговом окне **Создание InfoCube для данных транзакции** в столбце **IObject** в одной из строк в списке выберите **Создать** , чтобы открыть диалоговое окно **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a7683-115">In the **Create InfoCube for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a7683-116">Каждая строка в таблице представляет столбец в потоке данных пакета.</span><span class="sxs-lookup"><span data-stu-id="a7683-116">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="a7683-117">Для создания InfoObject во время создания InfoSouce для данных транзакции выберите **InfoSource**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a7683-117">To create an InfoObject while creating an InfoSouce for transactional data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="a7683-118">В диалоговом окне **Создание InfoSource** выберите **Данные транзакции**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7683-118">In the **Create InfoSource** dialog box, select **Transaction Data**, and then click **OK**.</span></span> <span data-ttu-id="a7683-119">В диалоговом окне **Создание InfoSource для данных транзакции** в столбце **IObject** для одной из строк в списке выберите **Создать** , чтобы открыть диалоговое окно **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a7683-119">In the **Create InfoSource for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a7683-120">Каждая строка в таблице представляет столбец в потоке данных пакета.</span><span class="sxs-lookup"><span data-stu-id="a7683-120">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    4.  <span data-ttu-id="a7683-121">Для создания InfoObject во время создания InfoSouce для основных данных выберите **InfoSource**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a7683-121">To create an InfoObject while creating an InfoSource for master data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="a7683-122">В диалоговом окне **Создание InfoSource** выберите **Основные данные**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7683-122">In the **Create InfoSource** dialog box, select **Master Data**, and then click **OK**.</span></span> <span data-ttu-id="a7683-123">В диалоговом окне **Создание InfoSource для основных данных** нажмите кнопку **Создать** , чтобы открыть диалоговое окно **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a7683-123">In the **Create InfoSource for Master Data** dialog box, click **New** to open the **Create New InfoObject** dialog box.</span></span>  
  
 <span data-ttu-id="a7683-124">Также можно открыть диалоговое окно **Создание нового InfoObject** путем щелчка **Создать** в разделе **Атрибуты** диалогового окна **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a7683-124">You can also open the **Create New InfoObject** dialog box by clicking **New** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="a7683-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a7683-125">General Options</span></span>  
 <span data-ttu-id="a7683-126">**Характеристика**</span><span class="sxs-lookup"><span data-stu-id="a7683-126">**Characteristic**</span></span>  
 <span data-ttu-id="a7683-127">Создайте InfoObject, представляющий данные измерения.</span><span class="sxs-lookup"><span data-stu-id="a7683-127">Create an InfoObject that represents dimension data.</span></span>  
  
 <span data-ttu-id="a7683-128">**Ключевая цифра**</span><span class="sxs-lookup"><span data-stu-id="a7683-128">**Key figure**</span></span>  
 <span data-ttu-id="a7683-129">Создайте InfoObject, представляющий данные фактов.</span><span class="sxs-lookup"><span data-stu-id="a7683-129">Create an InfoObject that represents fact data.</span></span>  
  
 <span data-ttu-id="a7683-130">**Имя InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a7683-130">**InfoObject name**</span></span>  
 <span data-ttu-id="a7683-131">Введите имя InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-131">Enter a name for the InfoObject.</span></span>  
  
 <span data-ttu-id="a7683-132">**Краткое описание**</span><span class="sxs-lookup"><span data-stu-id="a7683-132">**Short description**</span></span>  
 <span data-ttu-id="a7683-133">Введите краткое описание InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-133">Enter a short description for the InfoObject.</span></span>  
  
 <span data-ttu-id="a7683-134">**Полное описание**</span><span class="sxs-lookup"><span data-stu-id="a7683-134">**Long description**</span></span>  
 <span data-ttu-id="a7683-135">Введите полное описание InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-135">Enter a long description for the InfoObject.</span></span>  
  
 <span data-ttu-id="a7683-136">**Содержит основные данные**</span><span class="sxs-lookup"><span data-stu-id="a7683-136">**Has master data**</span></span>  
 <span data-ttu-id="a7683-137">Указывает, что InfoObject содержит основные данные в форме атрибутов, текстов или иерархий.</span><span class="sxs-lookup"><span data-stu-id="a7683-137">Indicate that the InfoObject contains master data in the form of attributes, texts, or hierarchies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7683-138">Выберите этот параметр, если InfoObject представляет данные измерений и выбран параметр **Характеристика** .</span><span class="sxs-lookup"><span data-stu-id="a7683-138">Select this option if the InfoObject represents dimensional data and you have selected the **Characteristic** option.</span></span>  
  
 <span data-ttu-id="a7683-139">**Разрешить символы в нижнем регистре**</span><span class="sxs-lookup"><span data-stu-id="a7683-139">**Allow lower-case characters**</span></span>  
 <span data-ttu-id="a7683-140">Разрешить символы в нижнем регистре для данных InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-140">Allow lower-case characters in the InfoObject data.</span></span>  
  
 <span data-ttu-id="a7683-141">**Сохранить и активировать**</span><span class="sxs-lookup"><span data-stu-id="a7683-141">**Save & Activate**</span></span>  
 <span data-ttu-id="a7683-142">Сохранить и активировать новый InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-142">Save and active the new InfoObject.</span></span>  
  
## <a name="data-type-options"></a><span data-ttu-id="a7683-143">Параметры типа данных</span><span class="sxs-lookup"><span data-stu-id="a7683-143">Data Type Options</span></span>  
 <span data-ttu-id="a7683-144">**CHAR — символьная строка**</span><span class="sxs-lookup"><span data-stu-id="a7683-144">**CHAR - Character String**</span></span>  
 <span data-ttu-id="a7683-145">Указывает, что InfoObject содержит символьные данные.</span><span class="sxs-lookup"><span data-stu-id="a7683-145">Indicates that the InfoObject contains character data.</span></span>  
  
 <span data-ttu-id="a7683-146">**NUMC — числовая строка**</span><span class="sxs-lookup"><span data-stu-id="a7683-146">**NUMC - Numeric String**</span></span>  
 <span data-ttu-id="a7683-147">Указывает, что InfoObject содержит числовые данные.</span><span class="sxs-lookup"><span data-stu-id="a7683-147">Indicates that the InfoObject contains numeric data.</span></span>  
  
 <span data-ttu-id="a7683-148">**DATS — дата (ГГГГММДД)**</span><span class="sxs-lookup"><span data-stu-id="a7683-148">**DATS - Date (YYYYMMDD)**</span></span>  
 <span data-ttu-id="a7683-149">Указывает, что InfoObject содержит данные даты.</span><span class="sxs-lookup"><span data-stu-id="a7683-149">Indicates that the InfoObject contains date data.</span></span>  
  
 <span data-ttu-id="a7683-150">**TIMS — время (ЧЧММСС)**</span><span class="sxs-lookup"><span data-stu-id="a7683-150">**TIMS - Time (HHMMSS)**</span></span>  
 <span data-ttu-id="a7683-151">Указывает, что InfoObject содержит данные времени.</span><span class="sxs-lookup"><span data-stu-id="a7683-151">Indicates that the InfoObject contains time data.</span></span>  
  
 <span data-ttu-id="a7683-152">**Длина**</span><span class="sxs-lookup"><span data-stu-id="a7683-152">**Length**</span></span>  
 <span data-ttu-id="a7683-153">Введите длину данных.</span><span class="sxs-lookup"><span data-stu-id="a7683-153">Enter the length of the data.</span></span>  
  
## <a name="text-options"></a><span data-ttu-id="a7683-154">Параметры текста</span><span class="sxs-lookup"><span data-stu-id="a7683-154">Text Options</span></span>  
 <span data-ttu-id="a7683-155">**С текстами**</span><span class="sxs-lookup"><span data-stu-id="a7683-155">**With Texts**</span></span>  
 <span data-ttu-id="a7683-156">Указывает, что InfoObject содержит тексты.</span><span class="sxs-lookup"><span data-stu-id="a7683-156">Indicate that the InfoObject contains texts.</span></span>  
  
 <span data-ttu-id="a7683-157">**Краткий текст**</span><span class="sxs-lookup"><span data-stu-id="a7683-157">**Short Text**</span></span>  
 <span data-ttu-id="a7683-158">Указывает, что InfoObject содержит краткие тексты.</span><span class="sxs-lookup"><span data-stu-id="a7683-158">Indicates that the InfoObject contains short texts.</span></span>  
  
 <span data-ttu-id="a7683-159">**Средний текст**</span><span class="sxs-lookup"><span data-stu-id="a7683-159">**Medium Text**</span></span>  
 <span data-ttu-id="a7683-160">Указывает, что InfoObject содержит средние тексты.</span><span class="sxs-lookup"><span data-stu-id="a7683-160">Indicates that the InfoObject contains medium texts.</span></span>  
  
 <span data-ttu-id="a7683-161">**Длинный текст**</span><span class="sxs-lookup"><span data-stu-id="a7683-161">**Long Text**</span></span>  
 <span data-ttu-id="a7683-162">Указывает, что InfoObject содержит длинные тексты.</span><span class="sxs-lookup"><span data-stu-id="a7683-162">Indicates that the InfoObject contains long texts.</span></span>  
  
 <span data-ttu-id="a7683-163">**Зависит от языка текста**</span><span class="sxs-lookup"><span data-stu-id="a7683-163">**Text Language-Dependent**</span></span>  
 <span data-ttu-id="a7683-164">Указывает, что тексты зависят от языка.</span><span class="sxs-lookup"><span data-stu-id="a7683-164">Indicates that the texts are language-dependent.</span></span>  
  
 <span data-ttu-id="a7683-165">**Зависит от времени текста**</span><span class="sxs-lookup"><span data-stu-id="a7683-165">**Text Time-Dependent**</span></span>  
 <span data-ttu-id="a7683-166">Указывает, что тексты зависят от времени.</span><span class="sxs-lookup"><span data-stu-id="a7683-166">Indicates that the texts are time-dependent.</span></span>  
  
## <a name="attributes-section"></a><span data-ttu-id="a7683-167">Раздел атрибутов</span><span class="sxs-lookup"><span data-stu-id="a7683-167">Attributes Section</span></span>  
 <span data-ttu-id="a7683-168">Раздел **Атрибуты** содержит список атрибутов для InfoObject и параметры, позволяющие добавлять и удалять атрибуты из списка.</span><span class="sxs-lookup"><span data-stu-id="a7683-168">The **Attributes** section consists of a list of attributes for the InfoObject, and the options that let you add and remove attributes from the list.</span></span>  
  
### <a name="attributes-list"></a><span data-ttu-id="a7683-169">Список «Атрибуты»</span><span class="sxs-lookup"><span data-stu-id="a7683-169">Attributes List</span></span>  
 <span data-ttu-id="a7683-170">В списке **Атрибуты** отображаются атрибуты создаваемого InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-170">The **Attributes** list displays the attributes of the InfoObject that you are creating.</span></span> <span data-ttu-id="a7683-171">Список **Атрибуты** содержит следующие заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="a7683-171">The **Attributes** list has the following column headings:</span></span>  
  
 <span data-ttu-id="a7683-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a7683-172">**InfoObject**</span></span>  
 <span data-ttu-id="a7683-173">Просмотрите имя InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-173">View the name of the InfoObject.</span></span>  
  
 <span data-ttu-id="a7683-174">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a7683-174">**Description**</span></span>  
 <span data-ttu-id="a7683-175">Просмотрите описание InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-175">View the description of the InfoObject.</span></span>  
  
 <span data-ttu-id="a7683-176">**Тип InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a7683-176">**InfoObject Type**</span></span>  
 <span data-ttu-id="a7683-177">Просмотрите тип InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-177">View the type of the InfoObject.</span></span> <span data-ttu-id="a7683-178">В следующей таблице приводятся возможные значения типа.</span><span class="sxs-lookup"><span data-stu-id="a7683-178">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="a7683-179">Значение</span><span class="sxs-lookup"><span data-stu-id="a7683-179">Value</span></span>|<span data-ttu-id="a7683-180">Description</span><span class="sxs-lookup"><span data-stu-id="a7683-180">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7683-181">CHA</span><span class="sxs-lookup"><span data-stu-id="a7683-181">CHA</span></span>|<span data-ttu-id="a7683-182">Характеристики</span><span class="sxs-lookup"><span data-stu-id="a7683-182">Characteristics</span></span>|  
|<span data-ttu-id="a7683-183">KYF</span><span class="sxs-lookup"><span data-stu-id="a7683-183">KYF</span></span>|<span data-ttu-id="a7683-184">Ключевые цифры</span><span class="sxs-lookup"><span data-stu-id="a7683-184">Key figures</span></span>|  
|<span data-ttu-id="a7683-185">UNI</span><span class="sxs-lookup"><span data-stu-id="a7683-185">UNI</span></span>|<span data-ttu-id="a7683-186">Units</span><span class="sxs-lookup"><span data-stu-id="a7683-186">Units</span></span>|  
|<span data-ttu-id="a7683-187">TIM</span><span class="sxs-lookup"><span data-stu-id="a7683-187">TIM</span></span>|<span data-ttu-id="a7683-188">Характеристики времени</span><span class="sxs-lookup"><span data-stu-id="a7683-188">Time characteristics</span></span>|  
  
### <a name="attributes-options"></a><span data-ttu-id="a7683-189">Параметры атрибутов</span><span class="sxs-lookup"><span data-stu-id="a7683-189">Attributes Options</span></span>  
 <span data-ttu-id="a7683-190">Можно использовать следующие параметры для добавления и удаления атрибутов для создаваемого InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-190">Use the following options to add and remove attributes for the InfoObject that you are creating:</span></span>  
  
 <span data-ttu-id="a7683-191">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="a7683-191">**Add**</span></span>  
 <span data-ttu-id="a7683-192">Добавляет существующий InfoObject как атрибут.</span><span class="sxs-lookup"><span data-stu-id="a7683-192">Add an existing InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="a7683-193">Чтобы добавить существующий InfoObject, щелкните «Добавить» и затем используйте диалоговое окно **Поиск InfoObject** для поиска InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-193">To add an existing InfoObject, click Add, and then use the **Look Up InfoObject** dialog box to find the InfoObject.</span></span> <span data-ttu-id="a7683-194">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="a7683-194">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="a7683-195">**Создать**</span><span class="sxs-lookup"><span data-stu-id="a7683-195">**New**</span></span>  
 <span data-ttu-id="a7683-196">Добавляет новый InfoObject как атрибут.</span><span class="sxs-lookup"><span data-stu-id="a7683-196">Add a new InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="a7683-197">Для создания и добавления нового InfoObject выберите «Создать», а затем используйте новый экземпляр диалогового окна **Создание InfoObject** , чтобы создать новый InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a7683-197">To create and add a new InfoObject, click New, and then use a new instance of the **Create New InfoObject** dialog box to create the new InfoObject.</span></span>  
  
 <span data-ttu-id="a7683-198">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="a7683-198">**Remove**</span></span>  
 <span data-ttu-id="a7683-199">Удаляет выбранный InfoObject из списка **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="a7683-199">Remove the selected InfoObject from the **Attributes** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7683-200">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7683-200">See Also</span></span>  
 <span data-ttu-id="a7683-201">[Создание InfoCube для данных транзакции](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7683-201">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="a7683-202">[Создание InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="a7683-202">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="a7683-203">[Создание InfoSource для данных транзакции](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7683-203">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="a7683-204">[Создание InfoSource для основных данных](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="a7683-204">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 [<span data-ttu-id="a7683-205">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="a7683-205">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
