---
title: Редактор диспетчера соединений с кэшем | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cacheconnection.f1
ms.assetid: 0d8f9324-0c35-4eea-b06d-da3cc2426d2c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 38a858217925496d8dd937d684368bdb2e061b14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667851"
---
# <a name="cache-connection-manager-editor"></a><span data-ttu-id="9352f-102">Редактор диспетчера соединений с кэшем</span><span class="sxs-lookup"><span data-stu-id="9352f-102">Cache Connection Manager Editor</span></span>
  <span data-ttu-id="9352f-103">Диспетчер соединений с кэшем читает эталонный набор данных из преобразования кэша или из файла кэша (CAW) и может сохранить эти данные в файле кэша.</span><span class="sxs-lookup"><span data-stu-id="9352f-103">The Cache connection manager reads a reference dataset from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="9352f-104">Данные всегда сохраняются в памяти.</span><span class="sxs-lookup"><span data-stu-id="9352f-104">The data is always stored in memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9352f-105">Диспетчер соединений с кэшем не поддерживает типы данных больших двоичных объектов: DT_TEXT, DT_NTEXT и DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="9352f-105">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="9352f-106">Если ссылочный набор данных содержит данные типа BLOB, то при попытке выполнения пакета компонент завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="9352f-106">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="9352f-107">**Редактор диспетчера соединений с кэшем** можно использовать для изменения типов данных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9352f-107">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span>  
  
 <span data-ttu-id="9352f-108">Преобразование «Уточняющий запрос» выполняет уточняющие запросы применительно к эталонному набору данных.</span><span class="sxs-lookup"><span data-stu-id="9352f-108">The Lookup transformation performs lookups on the reference dataset.</span></span>  
  
 <span data-ttu-id="9352f-109">В диалоговом окне **Редактор диспетчера соединений с кэшем** находятся следующие вкладки.</span><span class="sxs-lookup"><span data-stu-id="9352f-109">The **Cache Connection ManagerEditor** dialog box includes the following tabs:</span></span>  
  
-   [<span data-ttu-id="9352f-110">Вкладка "Общие"</span><span class="sxs-lookup"><span data-stu-id="9352f-110">General tab</span></span>](#generaltab)  
  
-   [<span data-ttu-id="9352f-111">Вкладка "столбцы"</span><span class="sxs-lookup"><span data-stu-id="9352f-111">Columns tab</span></span>](#columnstab)  
  
 <span data-ttu-id="9352f-112">Дополнительные сведения о диспетчере соединений с кэшем см. в разделе [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9352f-112">To learn more about the Cache Connection Manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
##  <a name="general-tab"></a><a name="generaltab"></a><span data-ttu-id="9352f-113">Вкладка "Общие"</span><span class="sxs-lookup"><span data-stu-id="9352f-113">General Tab</span></span>  
 <span data-ttu-id="9352f-114">Используйте вкладку **Общие** диалогового окна **Редактор диспетчера соединений с кэшем** , чтобы указать, должно ли содержимое кэша быть прочитано из файла или сохранено в файле.</span><span class="sxs-lookup"><span data-stu-id="9352f-114">Use the **General** tab of the **Cache Connection ManagerEditor** dialog box to indicate whether to read the cache from a file or save the cache to a file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="9352f-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="9352f-115">Options</span></span>  
 <span data-ttu-id="9352f-116">**Имя диспетчера подключений**</span><span class="sxs-lookup"><span data-stu-id="9352f-116">**Connection manager name**</span></span>  
 <span data-ttu-id="9352f-117">Предоставьте уникальное имя для соединения с кэшем в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="9352f-117">Provide a unique name for the cache connection in the workflow.</span></span> <span data-ttu-id="9352f-118">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9352f-118">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="9352f-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9352f-119">**Description**</span></span>  
 <span data-ttu-id="9352f-120">Опишите соединение.</span><span class="sxs-lookup"><span data-stu-id="9352f-120">Describe the connection.</span></span> <span data-ttu-id="9352f-121">Рекомендуется описать цель соединения, чтобы пакеты самодокументировались и их проще было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="9352f-121">As a best practice, describe the connection according to its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="9352f-122">**Использование файлового кэша**</span><span class="sxs-lookup"><span data-stu-id="9352f-122">**Use file cache**</span></span>  
 <span data-ttu-id="9352f-123">Указать, следует ли использовать файл кэша.</span><span class="sxs-lookup"><span data-stu-id="9352f-123">Indicate whether to use a cache file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9352f-124">Уровень защиты пакета не применяется к кэшируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="9352f-124">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="9352f-125">Если кэшируемый файл содержит важные данные, используйте список управления доступом (ACL), чтобы запретить доступ к расположению или папке, в которой хранится файл.</span><span class="sxs-lookup"><span data-stu-id="9352f-125">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="9352f-126">Доступ следует разрешать только определенным учетным записям.</span><span class="sxs-lookup"><span data-stu-id="9352f-126">You should enable access only to certain accounts.</span></span> <span data-ttu-id="9352f-127">Дополнительные сведения см. в разделе [Доступ к файлам, используемым пакетами](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="9352f-127">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="9352f-128">Если выполнена настройка диспетчера соединений с кэшем для использования файла кэша, то диспетчер соединений выполняет одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9352f-128">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
-   <span data-ttu-id="9352f-129">Сохранить данные в файле, если преобразование «Конвертация данных кэш» настроено на запись данных из источника данных в потоке данных в диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="9352f-129">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span> <span data-ttu-id="9352f-130">Дополнительные сведения см. в разделе [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="9352f-130">For more information, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="9352f-131">Считать данные из файла кэша.</span><span class="sxs-lookup"><span data-stu-id="9352f-131">Read data from the cache file.</span></span>  
  
 <span data-ttu-id="9352f-132">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="9352f-132">**File name**</span></span>  
 <span data-ttu-id="9352f-133">Введите путь и имя файла кэша.</span><span class="sxs-lookup"><span data-stu-id="9352f-133">Type the path and file name of the cache file.</span></span>  
  
 <span data-ttu-id="9352f-134">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="9352f-134">**Browse**</span></span>  
 <span data-ttu-id="9352f-135">Найдите файл кэша.</span><span class="sxs-lookup"><span data-stu-id="9352f-135">Locate the cache file.</span></span>  
  
 <span data-ttu-id="9352f-136">**Обновление метаданных**</span><span class="sxs-lookup"><span data-stu-id="9352f-136">**Refresh Metadata**</span></span>  
 <span data-ttu-id="9352f-137">Удалите столбец метаданных в диспетчере соединений с кэшем и повторно заполните диспетчер соединений с кэшем метаданными столбца из выбранного файла кэша.</span><span class="sxs-lookup"><span data-stu-id="9352f-137">Delete the column metadata in the Cache connection manager and repopulate the Cache connection manager with column metadata from a selected cache file.</span></span>  
  
##  <a name="columns-tab"></a><a name="columnstab"></a><span data-ttu-id="9352f-138">Вкладка "столбцы"</span><span class="sxs-lookup"><span data-stu-id="9352f-138">Columns Tab</span></span>  
 <span data-ttu-id="9352f-139">Вкладка **Столбцы** диалогового окна **Редактор диспетчера соединений с кэшем** используется для настройки свойств каждого из столбцов в кэше.</span><span class="sxs-lookup"><span data-stu-id="9352f-139">Use the **Columns** tab of the **Cache Connection Manager Editor** dialog box to configure the properties of each column in the cache.</span></span>  
  
### <a name="options"></a><span data-ttu-id="9352f-140">Параметры</span><span class="sxs-lookup"><span data-stu-id="9352f-140">Options</span></span>  
 <span data-ttu-id="9352f-141">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9352f-141">**Column**</span></span>  
 <span data-ttu-id="9352f-142">Указывает имя столбца.</span><span class="sxs-lookup"><span data-stu-id="9352f-142">Specify the column name.</span></span>  
  
 <span data-ttu-id="9352f-143">**Значение индекса**</span><span class="sxs-lookup"><span data-stu-id="9352f-143">**Index Position**</span></span>  
 <span data-ttu-id="9352f-144">Указывает, какие столбцы являются индексными столбцами, задавая позицию в индексе каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="9352f-144">Specify which columns are index columns by specifying the index position of each column.</span></span> <span data-ttu-id="9352f-145">Индекс представляет собой коллекцию из одного или нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="9352f-145">The index is a collection of one or more columns.</span></span>  
  
 <span data-ttu-id="9352f-146">Для неиндексированных столбцов позиция индекса равна 0.</span><span class="sxs-lookup"><span data-stu-id="9352f-146">For non-index columns, the index position is 0.</span></span>  
  
 <span data-ttu-id="9352f-147">Для индексированных столбцов позиция индекса является положительным порядковым номером.</span><span class="sxs-lookup"><span data-stu-id="9352f-147">For index columns, the index position is a sequential, positive number.</span></span> <span data-ttu-id="9352f-148">Этот номер указывает порядок, в котором преобразование «Уточняющий запрос» сравнивает строки в ссылочном наборе данных со строками в источнике входных данных.</span><span class="sxs-lookup"><span data-stu-id="9352f-148">This number indicates the order in which the Lookup transformation compares rows in the reference dataset to rows in the input data source.</span></span> <span data-ttu-id="9352f-149">Столбец с самыми уникальными значениями должен иметь наименьшую позицию индекса.</span><span class="sxs-lookup"><span data-stu-id="9352f-149">The column with the most unique values should have the lowest index position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9352f-150">Если преобразование «Уточняющий запрос» настроено для использования диспетчера соединений с кэшем, то только индексированные столбцы в ссылочном наборе данных могут быть сопоставлены с входными столбцами.</span><span class="sxs-lookup"><span data-stu-id="9352f-150">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="9352f-151">Кроме того, все столбцы индекса должны быть сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="9352f-151">Also, all index columns must be mapped.</span></span>  
  
 <span data-ttu-id="9352f-152">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9352f-152">**Type**</span></span>  
 <span data-ttu-id="9352f-153">Задает тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="9352f-153">Specify the data type of the column.</span></span>  
  
 `Length`  
 <span data-ttu-id="9352f-154">Указывает тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="9352f-154">Specifies the column data type.</span></span> <span data-ttu-id="9352f-155">Параметр `Length` можно изменить, если он применим к типу данных.</span><span class="sxs-lookup"><span data-stu-id="9352f-155">If applicable to the data type, you can update `Length`.</span></span>  
  
 `Precision`  
 <span data-ttu-id="9352f-156">Задает точность для определенных типов данных столбца.</span><span class="sxs-lookup"><span data-stu-id="9352f-156">Specifies the precision for certain column data types.</span></span> <span data-ttu-id="9352f-157">Точность представляет собой количество цифр в числе.</span><span class="sxs-lookup"><span data-stu-id="9352f-157">Precision is the number of digits in a number.</span></span> <span data-ttu-id="9352f-158">Параметр `Precision` можно изменить, если он применим к типу данных.</span><span class="sxs-lookup"><span data-stu-id="9352f-158">If applicable to the data type, you can update `Precision`.</span></span>  
  
 `Scale`  
 <span data-ttu-id="9352f-159">Задает масштаб для определенных типов данных столбца.</span><span class="sxs-lookup"><span data-stu-id="9352f-159">Specifies the scale for certain column data types.</span></span> <span data-ttu-id="9352f-160">Масштаб представляет собой количество цифр справа от десятичной запятой в числе.</span><span class="sxs-lookup"><span data-stu-id="9352f-160">Scale is the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="9352f-161">Параметр `Scale` можно изменить, если он применим к типу данных.</span><span class="sxs-lookup"><span data-stu-id="9352f-161">If applicable to the data type, you can update `Scale`.</span></span>  
  
 `Code Page`  
 <span data-ttu-id="9352f-162">Задает кодовую страницу для столбца этого типа.</span><span class="sxs-lookup"><span data-stu-id="9352f-162">Specifies the code page for the column type.</span></span> <span data-ttu-id="9352f-163">Параметр `Code Page` можно изменить, если он применим к типу данных.</span><span class="sxs-lookup"><span data-stu-id="9352f-163">If applicable to the data type, you can update `Code Page`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9352f-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="9352f-164">See Also</span></span>  
 [<span data-ttu-id="9352f-165">Преобразование "Уточняющий запрос"</span><span class="sxs-lookup"><span data-stu-id="9352f-165">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
