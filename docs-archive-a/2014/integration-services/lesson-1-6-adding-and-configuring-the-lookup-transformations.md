---
title: Шаг 6. Добавление и настройка преобразований «Уточняющий запрос» | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c59f723-9707-4407-80ae-f05f483cf65f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96b0a848508c19eb24cf1538244a39fcec57361a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664345"
---
# <a name="step-6-adding-and-configuring-the-lookup-transformations"></a><span data-ttu-id="65cb4-102">Шаг 6. Добавление и настройка преобразований «Уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="65cb4-102">Step 6: Adding and Configuring the Lookup Transformations</span></span>
  <span data-ttu-id="65cb4-103">После того как источник неструктурированных файлов настроен для извлечения данных из файла источника, следует определить преобразования «Уточняющий запрос», необходимые для получения значений **CurrencyKey** и **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-103">After you have configured the Flat File source to extract data from the source file, the next task is to define the Lookup transformations needed to obtain the values for the **CurrencyKey** and **DateKey**.</span></span> <span data-ttu-id="65cb4-104">Преобразование «Уточняющий запрос» выполняет поиск, соединяя данные указанного входного столбца со столбцом эталонного набора данных.</span><span class="sxs-lookup"><span data-stu-id="65cb4-104">A Lookup transformation performs a lookup by joining data in the specified input column to a column in a reference dataset.</span></span> <span data-ttu-id="65cb4-105">Эталонным набором данных может быть таблица или представление, новая таблица или результат инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="65cb4-105">The reference dataset can be an existing table or view, a new table, or the result of an SQL statement.</span></span> <span data-ttu-id="65cb4-106">В этом учебнике преобразование «Уточняющий запрос» использует диспетчер соединений OLE DB, чтобы подключиться к базе данных, содержащей данные, служащие источником для эталонного набора данных.</span><span class="sxs-lookup"><span data-stu-id="65cb4-106">In this tutorial, the Lookup transformation uses an OLE DB connection manager to connect to the database that contains the data that is the source of the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65cb4-107">Можно также настроить преобразование «Уточняющий запрос» для подключения к кэшу, который содержит эталонный набор данных.</span><span class="sxs-lookup"><span data-stu-id="65cb4-107">You can also configure the Lookup transformation to connect to a cache that contains the reference dataset.</span></span> <span data-ttu-id="65cb4-108">Дополнительные сведения см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="65cb4-108">For more information, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="65cb4-109">Этот учебник описывает добавление в пакет и настройку следующих двух компонентов преобразования «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="65cb4-109">For this tutorial, you will add and configure the following two Lookup transformation components to the package:</span></span>  
  
-   <span data-ttu-id="65cb4-110">Первое преобразование предназначено для уточняющего запроса значений в столбце **CurrencyKey** таблицы измерения **DimCurrency** , сопоставленных со значениями столбца **CurrencyID** неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="65cb4-110">One transformation to perform a lookup of values from the **CurrencyKey** column of the **DimCurrency** dimension table based on matching **CurrencyID** column values from the flat file.</span></span>  
  
-   <span data-ttu-id="65cb4-111">Второе преобразование предназначено для уточняющего запроса значений в столбце **DateKey** таблицы измерения **DimDate** , сопоставленных со значениями столбца **CurrencyDate** неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="65cb4-111">One transformation to perform a lookup of values from the **DateKey** column of the **DimDate** dimension table based on matching **CurrencyDate** column values from the flat file.</span></span>  
  
 <span data-ttu-id="65cb4-112">В обоих случаях в преобразовании «Уточняющий запрос» будет использоваться созданный ранее диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="65cb4-112">In both cases, the Lookup transformation will utilize the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-lookup-currency-key-transformation"></a><span data-ttu-id="65cb4-113">Добавление и настройка преобразования «Уточняющий запрос ключа валюты»</span><span class="sxs-lookup"><span data-stu-id="65cb4-113">To add and configure the Lookup Currency Key transformation</span></span>  
  
1.  <span data-ttu-id="65cb4-114">В **области элементов служб SSIS**разверните **узел Общие**и перетащите элемент **Поиск** в область конструктора на вкладке **поток данных** . Разместите Поиск непосредственно под источником данных " **Извлечение образца валюты** ".</span><span class="sxs-lookup"><span data-stu-id="65cb4-114">In the **SSIS Toolbox**, expand **Common**, and then drag **Lookup** onto the design surface of the **Data Flow** tab. Place Lookup directly below the **Extract Sample Currency Data** source.</span></span>  
  
2.  <span data-ttu-id="65cb4-115">Щелкните источник неструктурированного файла **Извлечь данные валют образца** и перетащите зеленую стрелку на вновь добавленное преобразование **Уточняющий запрос** , соединив эти два компонента.</span><span class="sxs-lookup"><span data-stu-id="65cb4-115">Click the **Extract Sample Currency Data** flat file source and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="65cb4-116">В области конструктора **Поток данных** щелкните элемент **Уточняющий запрос** в преобразовании **Уточняющий запрос** и измените имя на **Уточняющий запрос ключа валюты**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-116">On the **Data Flow** design surface, click **Lookup** in the **Lookup** transformation, and change the name to **Lookup Currency Key**.</span></span>  
  
4.  <span data-ttu-id="65cb4-117">Дважды щелкните преобразование **Поиск CurrencyKey** , чтобы открыть редактор преобразования "Уточняющий запрос".</span><span class="sxs-lookup"><span data-stu-id="65cb4-117">Double-click the **Lookup CurrencyKey** transformation to display the Lookup Transformation Editor.</span></span>  
  
5.  <span data-ttu-id="65cb4-118">На вкладке **Общие** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="65cb4-118">On the **General** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="65cb4-119">Выберите **Полное кэширование**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-119">Select **Full cache**.</span></span>  
  
    2.  <span data-ttu-id="65cb4-120">В области **Тип соединения** выберите **Диспетчер соединений OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-120">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
6.  <span data-ttu-id="65cb4-121">На вкладке **Соединение** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="65cb4-121">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="65cb4-122">Убедитесь, что в диалоговом окне **Диспетчер соединений OLE DB** отображается **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-122">In the **OLE DB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="65cb4-123">Выберите **Использовать результаты SQL-запроса**и введите или скопируйте следующую инструкцию SQL:</span><span class="sxs-lookup"><span data-stu-id="65cb4-123">Select **Use results of an SQL query**, and then type or copy the following SQL statement:</span></span>  
  
        ```  
        select * from (select * from [dbo].[DimCurrency]) as refTable  
        where [refTable].[CurrencyAlternateKey] = 'ARS'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'AUD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'BRL'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CAD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CNY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'DEM'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'EUR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'FRF'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'GBP'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'JPY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'MXN'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'SAR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'USD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'VEB'  
        ```  
  
7.  <span data-ttu-id="65cb4-124">На вкладке **Столбцы** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="65cb4-124">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="65cb4-125">На панели **Доступные входные столбцы** перетащите **CurrencyID** на панель **Доступные столбцы подстановки** и поместите его на элемент **CurrencyAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-125">In the **Available Input Columns** panel, drag **CurrencyID** to the **Available Lookup Columns** panel and drop it on **CurrencyAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="65cb4-126">В списке **Доступные столбцы подстановки** установите флажок слева от столбца **CurrencyKey**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-126">In the **Available Lookup Columns** list, select the check box to the left of **CurrencyKey**.</span></span>  
  
8.  <span data-ttu-id="65cb4-127">Нажмите **ОК** , чтобы вернуться в область конструктора **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-127">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
9. <span data-ttu-id="65cb4-128">Щелкните правой кнопкой мыши преобразование "Уточняющий запрос ключа валюты" и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-128">Right-click the Lookup Currency Key transformation, click **Properties**.</span></span>  
  
10. <span data-ttu-id="65cb4-129">В окно свойств убедитесь, что `LocaleID` свойство имеет значение **английский (США)** , а свойство **DefaultCodePage** имеет значение **1252**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-129">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
### <a name="to-add-and-configure-the--lookup-datekey-transformation"></a><span data-ttu-id="65cb4-130">Добавление и настройка преобразования «Уточняющий запрос ключа даты»</span><span class="sxs-lookup"><span data-stu-id="65cb4-130">To add and configure the  Lookup DateKey transformation</span></span>  
  
1.  <span data-ttu-id="65cb4-131">В окне **Область элементов служб SSIS**перетащите **Уточняющий запрос** в область конструктора **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-131">In the **SSIS Toolbox**, drag **Lookup** onto the **Data Flow** design surface.</span></span> <span data-ttu-id="65cb4-132">Поместите «Уточняющий запрос» прямо под преобразование **Уточняющий запрос ключа валюты** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-132">Place Lookup directly below the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="65cb4-133">Щелкните преобразование **Уточняющий запрос ключа валюты** и перетащите зеленую стрелку на вновь созданное преобразование **Уточняющий запрос** , соединив эти два компонента.</span><span class="sxs-lookup"><span data-stu-id="65cb4-133">Click the **Lookup Currency Key** transformation and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="65cb4-134">В диалоговом окне **Выбор входов и выходов** щелкните **Выход совпадающих строк преобразования «Уточняющий запрос»** в списке **Выходы** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-134">In the **Input Output Selection** dialog box, click **Lookup Match Output** in the **Output** list box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="65cb4-135">В области конструктора **Поток данных** щелкните элемент **Уточняющий запрос** в только что добавленном преобразовании **Уточняющий запрос** и измените имя на **Уточняющий запрос ключа даты**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-135">On the **Data Flow** design surface, click **Lookup** in the newly added **Lookup** transformation, and change the name to **Lookup Date Key**.</span></span>  
  
5.  <span data-ttu-id="65cb4-136">Дважды щелкните преобразование **Уточняющий запрос ключа даты** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-136">Double-click the **Lookup Date Key** transformation.</span></span>  
  
6.  <span data-ttu-id="65cb4-137">На вкладке **Общие** выберите **Частичное кэширование**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-137">On the **General** page, select **Partial cache**.</span></span>  
  
7.  <span data-ttu-id="65cb4-138">На вкладке **Соединение** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="65cb4-138">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="65cb4-139">Убедитесь в том, что в диалоговом окне **Диспетчер соединений OLE DB** отображается **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-139">In the **OLEDB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="65cb4-140">В поле **Использовать таблицу или представление** введите или выберите значение **[dbo].[DimDate]**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-140">In the **Use a table or view** box, type or select **[dbo].[DimDate]**.</span></span>  
  
8.  <span data-ttu-id="65cb4-141">На вкладке **Столбцы** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="65cb4-141">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="65cb4-142">На панели **Доступные входные столбцы** перетяните **CurrencyDate** на панель **Доступные столбцы подстановки** и поместите его на элемент **FullDateAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-142">In the **Available Input Columns** panel, drag **CurrencyDate** to the **Available Lookup Columns** panel and drop it on **FullDateAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="65cb4-143">В списке **Доступные столбцы подстановки** установите флажок слева от столбца **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-143">In the **Available Lookup Columns** list, select the check box to the left of **DateKey**.</span></span>  
  
9. <span data-ttu-id="65cb4-144">На странице **Дополнительно** просмотрите параметры кэширования.</span><span class="sxs-lookup"><span data-stu-id="65cb4-144">On the **Advanced** page, review the caching options.</span></span>  
  
10. <span data-ttu-id="65cb4-145">Нажмите **ОК** , чтобы вернуться в область конструктора **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="65cb4-145">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
11. <span data-ttu-id="65cb4-146">Щелкните правой кнопкой мыши преобразование "Уточняющий запрос ключа даты" и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-146">Right-click the Lookup Date Key transformation and click **Properties.**</span></span>  
  
12. <span data-ttu-id="65cb4-147">В окно свойств убедитесь, что `LocaleID` свойство имеет значение **английский (США)** , а свойство **DefaultCodePage** имеет значение **1252**.</span><span class="sxs-lookup"><span data-stu-id="65cb4-147">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="65cb4-148">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="65cb4-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="65cb4-149">Шаг 7. Добавление и настройка назначения OLE DB</span><span class="sxs-lookup"><span data-stu-id="65cb4-149">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
## <a name="see-also"></a><span data-ttu-id="65cb4-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="65cb4-150">See Also</span></span>  
 [<span data-ttu-id="65cb4-151">Преобразование "Уточняющий запрос"</span><span class="sxs-lookup"><span data-stu-id="65cb4-151">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
