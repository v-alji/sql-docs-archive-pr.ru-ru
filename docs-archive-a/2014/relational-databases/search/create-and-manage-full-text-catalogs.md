---
title: Создание полнотекстовых каталогов и управление ими | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs [SQL Server], creating
- full-text search [SQL Server], using SQL Server Management Studio
ms.assetid: 824b7131-44a6-4815-89e6-62b7bab060e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18efd79bc34beee94d4edc61e9165a986edba90b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668735"
---
# <a name="create-and-manage-full-text-catalogs"></a><span data-ttu-id="f5a40-102">Создание и управление полнотекстовыми каталогами</span><span class="sxs-lookup"><span data-stu-id="f5a40-102">Create and Manage Full-Text Catalogs</span></span>
  <span data-ttu-id="f5a40-103">Полнотекстовый каталог теперь является виртуальным объектом, не принадлежащим ни к одной файловой группе. Он является логическим понятием, ссылающимся на группу полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="f5a40-103">A full-text catalog is a virtual object that does not belong to any filegroup; it is a logical concept that refers to a group of full-text indexes.</span></span>  
  
##  <a name="creating-a-full-text-catalog"></a><a name="creating"></a><span data-ttu-id="f5a40-104">Создание полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f5a40-104">Creating a Full-Text Catalog</span></span>  
  
#### <a name="to-create-a-full-text-catalog"></a><span data-ttu-id="f5a40-105">Создание полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f5a40-105">To create a full-text catalog</span></span>  
  
1.  <span data-ttu-id="f5a40-106">В обозревателе объектов разверните сервер, затем узел **Базы данных**, а затем — базу данных, в которой необходимо создать полнотекстовый каталог.</span><span class="sxs-lookup"><span data-stu-id="f5a40-106">In Object Explorer, expand the server, expand **Databases**, and expand the database in which you want to create the full-text catalog.</span></span>  
  
2.  <span data-ttu-id="f5a40-107">Разверните узел **Хранилище**, затем щелкните правой кнопкой мыши **Полнотекстовые каталоги**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-107">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="f5a40-108">Выберите **Создание полнотекстового каталога**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-108">Select **New Full-Text Catalog**.</span></span>  
  
4.  <span data-ttu-id="f5a40-109">В диалоговом окне **Создание полнотекстового каталога** укажите сведения о вновь создаваемом каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5a40-109">In the **New Full-Text Catalog** dialog box, specify the information for the catalog that you are re-creating.</span></span> <span data-ttu-id="f5a40-110">Дополнительные сведения см. в разделе [Создание полнотекстового каталога (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="f5a40-110">For more information, see [New Full-Text Catalog &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5a40-111">Идентификаторы полнотекстовых каталогов начинаются с 00005 и увеличиваются на единицу для каждого вновь создаваемого каталога.</span><span class="sxs-lookup"><span data-stu-id="f5a40-111">Full-text catalog IDs begin at 00005 and are incremented by one for each new catalog created.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
  
##  <a name="viewing-the-properties-of-a-full-text-catalog"></a><a name="props"></a><span data-ttu-id="f5a40-112">Просмотр свойств полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f5a40-112">Viewing the Properties of a Full-Text Catalog</span></span>  
 <span data-ttu-id="f5a40-113">Для получения значений различных свойств полнотекстового индексирования можно использовать некоторые функции [!INCLUDE[tsql](../../includes/tsql-md.md)], например FULLTEXTCATALOGPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="f5a40-113">[!INCLUDE[tsql](../../includes/tsql-md.md)] functions such as FULLTEXTCATALOGPROPERTY can be used to obtain the value of various properties related to full-text indexing.</span></span> <span data-ttu-id="f5a40-114">Эти сведения полезны для администрирования и устранения нарушений в работе средств полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="f5a40-114">This information is useful for administering and troubleshooting full-text search.</span></span>  
  
 <span data-ttu-id="f5a40-115">В следующей таблице перечислены свойства, о которых сообщается в полнотекстовых каталогах.</span><span class="sxs-lookup"><span data-stu-id="f5a40-115">The following table lists the properties that are related to full-text catalogs.</span></span>  
  
|<span data-ttu-id="f5a40-116">Свойство</span><span class="sxs-lookup"><span data-stu-id="f5a40-116">Property</span></span>|<span data-ttu-id="f5a40-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f5a40-117">Description</span></span>|<span data-ttu-id="f5a40-118">Компонент</span><span class="sxs-lookup"><span data-stu-id="f5a40-118">Function</span></span>|  
|--------------|-----------------|--------------|  
|`AccentSensitivity`|<span data-ttu-id="f5a40-119">Настройка учета диакритических знаков:</span><span class="sxs-lookup"><span data-stu-id="f5a40-119">Accent-sensitivity setting.</span></span>|[<span data-ttu-id="f5a40-120">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-120">FULLTEXTCATALOGPROPERTY</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)|  
|`ImportStatus`|<span data-ttu-id="f5a40-121">Выполняется ли в настоящее время импорт полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="f5a40-121">Whether the full-text catalog is being imported.</span></span>|<span data-ttu-id="f5a40-122">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-122">FULLTEXTCATALOGPROPERTY</span></span>|  
|`IndexSize`|<span data-ttu-id="f5a40-123">Размер полнотекстового каталога в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="f5a40-123">Size of the full-text catalog in megabytes (MB).</span></span>|<span data-ttu-id="f5a40-124">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-124">FULLTEXTCATALOGPROPERTY</span></span>|  
|`ItemCount`|<span data-ttu-id="f5a40-125">Количество полнотекстовых индексированных элементов в полнотекстовом каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5a40-125">Number of full-text indexed items currently in the full-text catalog.</span></span>|<span data-ttu-id="f5a40-126">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-126">FULLTEXTCATALOGPROPERTY</span></span>|  
|`MergeStatus`|<span data-ttu-id="f5a40-127">Выполняется ли слияние в единый файл.</span><span class="sxs-lookup"><span data-stu-id="f5a40-127">Whether a master merge is in progress.</span></span>|<span data-ttu-id="f5a40-128">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-128">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateCompletionAge`|<span data-ttu-id="f5a40-129">Разница в секундах между завершением последнего заполнения полнотекстового индекса и 01/01/1990 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="f5a40-129">Difference in seconds between the completion of the last full-text index population and 01/01/1990 00:00:00.</span></span>|<span data-ttu-id="f5a40-130">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-130">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateStatus`|<span data-ttu-id="f5a40-131">Состояние заполнения.</span><span class="sxs-lookup"><span data-stu-id="f5a40-131">Populate status.</span></span><br /><br /> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]|<span data-ttu-id="f5a40-132">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-132">FULLTEXTCATALOGPROPERTY</span></span>|  
|`UniqueKeyCount`|<span data-ttu-id="f5a40-133">Количество уникальных ключей в полнотекстовом каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5a40-133">Number of unique keys in the full-text catalog.</span></span>|<span data-ttu-id="f5a40-134">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="f5a40-134">FULLTEXTCATALOGPROPERTY</span></span>|  
  
  
  
##  <a name="rebuilding-a-full-text-catalog"></a><a name="rebuildone"></a><span data-ttu-id="f5a40-135">Перестроение полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f5a40-135">Rebuilding a Full-Text Catalog</span></span>  
  
#### <a name="to-rebuild-a-full-text-catalog"></a><span data-ttu-id="f5a40-136">Перестроение полнотекстового каталога</span><span class="sxs-lookup"><span data-stu-id="f5a40-136">To rebuild a full-text catalog</span></span>  
  
1.  <span data-ttu-id="f5a40-137">В обозревателе объектов последовательно разверните узел сервера, затем **Базы данных**, а затем — базу данных, содержащую полнотекстовый каталог, который необходимо перестроить.</span><span class="sxs-lookup"><span data-stu-id="f5a40-137">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalog that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="f5a40-138">Разверните узел **Хранилище**, а затем **Полнотекстовые каталоги**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-138">Expand **Storage**, and then expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="f5a40-139">Щелкните правой кнопкой мыши имя полнотекстового каталога, который необходимо перестроить, и выберите **Перестроить**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-139">Right-click the name of the full-text catalog that you want to rebuild, and select **Rebuild**.</span></span>  
  
4.  <span data-ttu-id="f5a40-140">На вопрос **Удалить полнотекстовый каталог и перестроить его?** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-140">To the question **Do you want to delete the full-text catalog and rebuild it?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="f5a40-141">В диалоговом окне **Перестроить полнотекстовый каталог** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-141">In the **Rebuild Full-Text Catalog** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="rebuilding-all-full-text-catalogs-for-a-database"></a><a name="rebuildall"></a><span data-ttu-id="f5a40-142">Перестроение всех полнотекстовых каталогов для базы данных</span><span class="sxs-lookup"><span data-stu-id="f5a40-142">Rebuilding All Full-Text Catalogs for a Database</span></span>  
  
#### <a name="to-rebuild-the-full-text-catalogs-for-a-database"></a><span data-ttu-id="f5a40-143">Перестроение полнотекстовых каталогов базы данных</span><span class="sxs-lookup"><span data-stu-id="f5a40-143">To rebuild the full-text catalogs for a database</span></span>  
  
1.  <span data-ttu-id="f5a40-144">В обозревателе объектов последовательно разверните узел сервера, затем **Базы данных**, а затем базу данных, содержащую полнотекстовые каталоги, которые необходимо перестроить.</span><span class="sxs-lookup"><span data-stu-id="f5a40-144">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalogs that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="f5a40-145">Разверните узел **Хранилище**, затем щелкните правой кнопкой мыши **Полнотекстовые каталоги**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-145">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="f5a40-146">Выберите **Перестроить все**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-146">Select **Rebuild All**.</span></span>  
  
4.  <span data-ttu-id="f5a40-147">В ответ на запрос **Удалить все полнотекстовые каталоги и перестроить их?** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-147">To the question, **Do you want to delete all full-text catalogs and rebuild them?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="f5a40-148">В диалоговом окне **Перестроить все полнотекстовые каталоги** нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-148">In the **Rebuild All Full-Text Catalogs** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="removing-a-full-text-catalog-from-a-database"></a><a name="removing"></a><span data-ttu-id="f5a40-149">Удаление полнотекстового каталога из базы данных</span><span class="sxs-lookup"><span data-stu-id="f5a40-149">Removing a Full-Text Catalog from a Database</span></span>  
  
#### <a name="to-remove-a-full-text-catalog-from-a-database"></a><span data-ttu-id="f5a40-150">Удаление полнотекстового каталога из базы данных</span><span class="sxs-lookup"><span data-stu-id="f5a40-150">To remove a full-text catalog from a database</span></span>  
  
1.  <span data-ttu-id="f5a40-151">В обозревателе объектов разверните узел сервера, затем **Базы данных**, а затем — базу данных, содержащую полнотекстовый каталог, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="f5a40-151">In Object Explorer, expand the server, expand **Databases**, and expand the database that contains the full-text catalog you want to remove.</span></span>  
  
2.  <span data-ttu-id="f5a40-152">Разверните узел **Хранилище**, а затем **Полнотекстовые каталоги**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-152">Expand **Storage**, and expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="f5a40-153">Щелкните правой кнопкой мыши полнотекстовый каталог, который необходимо удалить, и выберите в меню пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-153">Right-click the full-text catalog that you want to remove, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="f5a40-154">В диалоговом окне **Удаление объектов** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5a40-154">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="f5a40-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5a40-155">See Also</span></span>  
 [<span data-ttu-id="f5a40-156">CREATE FULLTEXT CATALOG (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f5a40-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
  
