---
title: Импорт значений проекта очистки в домен | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.importprojectvalues.f1
ms.assetid: f23e38e2-39e0-42d7-abd5-34d8fcca5d2a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 38616da5a0a8fb9c8f149d9f55a08b63dee5ff6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732042"
---
# <a name="import-cleansing-project-values-into-a-domain"></a><span data-ttu-id="c0fbe-102">Импорт значений проекта очистки в домен</span><span class="sxs-lookup"><span data-stu-id="c0fbe-102">Import Cleansing Project Values into a Domain</span></span>
  <span data-ttu-id="c0fbe-103">В службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) можно импортировать в домен знания о качестве данных, собранные в проекте очистки данных о качестве или в пакете служб Integration Services с компонентом DQS Cleansing.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), you can import data quality knowledge gathered during the cleansing process in a data quality cleansing project or an Integration Services package containing the DQS Cleansing component into a domain.</span></span> <span data-ttu-id="c0fbe-104">Это позволяет не допустить потери надежных знаний и обеспечить постоянное улучшение базы знаний.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-104">This ensures that trusted knowledge is not lost, and that the knowledge base is continually improved.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0fbe-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c0fbe-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c0fbe-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c0fbe-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="c0fbe-107">Чтобы импортировать значения из проекта очистки в домен, этот домен должен использоваться в проекте очистки в клиенте Data Quality Client или в пакете служб Integration Services с компонентом DQS Cleansing.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-107">To import cleansing project values into a domain, the domain must have been used in the cleansing project in Data Quality Client or in the Integration Services package containing a DQS Cleansing component.</span></span>  
  
-   <span data-ttu-id="c0fbe-108">Необходимо, чтобы проект очистки в клиенте Data Quality Client или пакете служб Integration Services с компонентом очистки DQS успешно завершился.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-108">The cleansing project in Data Quality Client or the Integration Services package containing the DQS Cleansing component must have successfully completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0fbe-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="c0fbe-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0fbe-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="c0fbe-110">Permissions</span></span>  
 <span data-ttu-id="c0fbe-111">Для импорта знаний служб DQS, собранных в процессе очистки, в домен необходимо быть членом роли dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import data quality knowledge gathered during the cleansing process into a domain.</span></span>  
  
##  <a name="import-cleansing-project-values"></a><a name="Import"></a><span data-ttu-id="c0fbe-112">Импорт значений проекта очистки</span><span class="sxs-lookup"><span data-stu-id="c0fbe-112">Import Cleansing Project Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="c0fbe-113">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="c0fbe-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="c0fbe-114">На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] откройте базу знаний в разделе управления доменами.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="c0fbe-115">При добавлении значений к существующему домену выберите домен в списке доменов.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-115">If adding values to an existing domain, select the domain in the domain list.</span></span>  
  
4.  <span data-ttu-id="c0fbe-116">Перейдите на вкладку **Значения домена** , щелкните значок **Импорт значений** на панели значков, а затем выберите пункт **Импорт значений проекта**.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-116">Click the **Domain Values** tab, click the **Import Values** icon in the icon bar, and then click **Import project values**.</span></span> <span data-ttu-id="c0fbe-117">Появляется диалоговое окно **Импорт значений проекта** со списком проектов качества данных и пакетов служб Integration Services, которые были очищены с помощью домена.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-117">The **Import Project Values** dialog box appears with a list of data quality projects and Integration Services packages that were cleansed using the domain.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0fbe-118"> Если никакие проекты не создавались с помощью этого домена или связанных с ним доменов или проект не был завершен, пункт **Импорт значений проекта** будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-118">If no project has been created using the domain or any of its linked domains, or the project was not finished, the **Import project values** option will not be available.</span></span>  
  
5.  <span data-ttu-id="c0fbe-119">В диалоговом окне **Импорт значений проекта** :</span><span class="sxs-lookup"><span data-stu-id="c0fbe-119">In the **Import Project Values** dialog box:</span></span>  
  
    -   <span data-ttu-id="c0fbe-120">Выберите **Все** в раскрывающемся списке **Импортировано** для вывода всех проектов или **Нет** , чтобы показать только проекты, значения которых еще не были импортированы.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-120">Select **All** in the **Imported** drop-down list to display all projects, or **No** to display only projects whose values have not been imported yet.</span></span>  
  
    -   <span data-ttu-id="c0fbe-121">Выберите проект, из которого хотите импортировать значения.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-121">Select the project that you want to import values from.</span></span>  
  
    -   <span data-ttu-id="c0fbe-122">Установите флажок **Добавить значения из вкладки «Новые»** , чтобы импортировать значения с вкладки «Новые», в дополнение к значениям на вкладках **Правильные** и **Исправленные** .</span><span class="sxs-lookup"><span data-stu-id="c0fbe-122">Select **Add values from New tab** to import values in the new tab, in addition to values in the **Correct** and **Corrected** tabs.</span></span>  
  
    -   <span data-ttu-id="c0fbe-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c0fbe-124">Вы возвращаетесь на вкладку **Значения домена** , и после успешного импорта выдается сообщение.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-124">You return to the **Domain Values** tab, and a message is displayed on successful import of the values.</span></span> <span data-ttu-id="c0fbe-125">Значения, которые были импортированы и, следовательно, являются новыми для домена, будет отображаться в таблице **Значения** .</span><span class="sxs-lookup"><span data-stu-id="c0fbe-125">Values that have been imported, and so are new to the domain, will be displayed in the **Values** table.</span></span>  
  
7.  <span data-ttu-id="c0fbe-126">Снимите флажок **Показывать только новые** , чтобы показывать все значения из домена.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-126">Deselect **Show Only New** to display all values that are in the domain.</span></span>  
  
8.  <span data-ttu-id="c0fbe-127">Установите флажок **Правильные**, **Неправильные**или **Недопустимые** для вывода значений только выбранного типа.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-127">Select **Correct**, **Error**, or **Invalid** to display only those values of the selected type.</span></span>  
  
9. <span data-ttu-id="c0fbe-128">Чтобы найти конкретную строку, введите ее в текстовом поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="c0fbe-128">To search for a specific string, enter the string in the **Find** text box.</span></span> <span data-ttu-id="c0fbe-129">Нажмите стрелку вниз или вверх для перехода по значениям, которые соответствуют критериям поиска.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-129">Click the up or down arrow to step through the values that meet the search criteria.</span></span> <span data-ttu-id="c0fbe-130">Они будут выделены желтым цветом.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-130">They will be highlighted in yellow.</span></span>  
  
10. <span data-ttu-id="c0fbe-131">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-131">Click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0fbe-132"> Дополнительные сведения о работе со значениями на вкладке **Значения домена** см. в разделе [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span><span class="sxs-lookup"><span data-stu-id="c0fbe-132">For more information on working with values in the **Domain Values** tab, see [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span></span>  
  
##  <a name="follow-up-after-importing-project-values-into-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="c0fbe-133">Дальнейшие действия. После импорта значений проекта в домен</span><span class="sxs-lookup"><span data-stu-id="c0fbe-133">Follow Up: After Importing Project Values into a Domain</span></span>  
 <span data-ttu-id="c0fbe-134">После импорта знаний служб DQS, собранных в процессе очистки, в домен вы можете приступать к другим задачам управления доменами с использованием этого домена и значений.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-134">After you import data quality knowledge gathered during the cleansing process into a domain, you can perform other domain management tasks on the domain and the values.</span></span> <span data-ttu-id="c0fbe-135">Дополнительные сведения см. в разделе [Управление доменом](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="c0fbe-135">For more information, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
##  <a name="values-that-will-be-imported"></a><a name="Values"></a> <span data-ttu-id="c0fbe-136">Значения, которые будут импортированы</span><span class="sxs-lookup"><span data-stu-id="c0fbe-136">Values that Will Be Imported</span></span>  
 <span data-ttu-id="c0fbe-137">Из проекта в домен будут импортированы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-137">The following values will be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="c0fbe-138">В домен импортируются только строковые значения.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-138">Only string values are imported to the domain.</span></span>  
  
-   <span data-ttu-id="c0fbe-139">Импортируются только значения со вкладок **Правильно**, **Исправлено**и **Создание** на странице **Управление и просмотр результатов** действия **Очистка** .</span><span class="sxs-lookup"><span data-stu-id="c0fbe-139">Only values from the **Correct**, **Corrected**, and **New** tabs on the **Manage and View results** page of the **Cleansing** activity will be imported.</span></span> <span data-ttu-id="c0fbe-140">Значения со вкладки **Создание** будут импортированы только в том случае, если установлен флажок **Добавить значения с вкладки «Создание»** в диалоговом окне **Импорт значений проекта** .</span><span class="sxs-lookup"><span data-stu-id="c0fbe-140">Values from the **New** tab will be imported only if the **Add values from New tab** check box in the **Import Project Values** dialog box has been selected.</span></span>  
  
-   <span data-ttu-id="c0fbe-141">Значения импортируются либо как верные, либо как ошибочные вместе со значением коррекции.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-141">Values will be imported as correct or as an error with its correction.</span></span> <span data-ttu-id="c0fbe-142">Будет импортировано только неправильное значение со значением коррекции.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-142">Only an error value with a correction value will be imported.</span></span>  
  
-   <span data-ttu-id="c0fbe-143">Значение коррекции будет либо новым значением, отсутствующим в базе знаний, либо существующим значением коррекции.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-143">The correction value will be either a new value that does not exist in the knowledge base or an existing correct value.</span></span>  
  
-   <span data-ttu-id="c0fbe-144">В базу знаний будут импортированы только исправления, выполненные на уровне значений, а не на уровне записей.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-144">Only corrections performed on the value level, not the record level, will be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="c0fbe-145">Если импортируемое значение противоречит правилу домена, будет создано недопустимое значение.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-145">Invalid values will be created if the imported value contradicts a domain rule.</span></span>  
  
-   <span data-ttu-id="c0fbe-146">При импорте значений из нескольких проектов одновременно значения импортируются последовательно.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-146">If you import values from several projects at once, the values are imported in a sequential order.</span></span>  
  
-   <span data-ttu-id="c0fbe-147">Исправление, выполненное в соответствии со связью на основе термина в домене, импортируется как правильное значение.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-147">A correction made as a result of a term-based relation in a domain is imported as a correct value (not as an error).</span></span>  
  
##  <a name="values-that-will-not-be-imported"></a><a name="ValuesNot"></a> <span data-ttu-id="c0fbe-148">Значения, которые не будут импортированы</span><span class="sxs-lookup"><span data-stu-id="c0fbe-148">Values that Will Not Be Imported</span></span>  
 <span data-ttu-id="c0fbe-149">Следующие значения не будут импортированы из проекта в домен:</span><span class="sxs-lookup"><span data-stu-id="c0fbe-149">The following values will not be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="c0fbe-150">Значения с вкладок **Предлагаемые** и **Недопустимые** на странице **Управление и просмотр результатов** в категории **Очистка** импортированы не будут.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-150">Values from the **Suggested** and **Invalid** tabs on the **Manage and View results** page of the **Cleansing** activity will not be imported.</span></span>  
  
-   <span data-ttu-id="c0fbe-151">Если значение в проекте очистки противоречит существующему значению в домене, то значение из проекта пропускается.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-151">If a value found in the cleansing project contradicts an existing value in the domain, the value found in the project is skipped.</span></span> <span data-ttu-id="c0fbe-152">Это относится и к конфликтам между значениями из проекта очистки и из базы знаний.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-152">This will include conflicts between cleansing and knowledge base values.</span></span>  
  
-   <span data-ttu-id="c0fbe-153">Исправления, выполненные на уровне записей, не будут импортированы в базу знаний.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-153">Corrections performed on the record level will not be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="c0fbe-154">Значения не будут импортированы в домен, если заменяемое значение было исправлено или определено как правильное службой ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-154">No value will be imported to a domain if the value that it would replace was corrected or approved as correct by a reference data service.</span></span>  
  
-   <span data-ttu-id="c0fbe-155">Если значение коррекции присутствует в базе знаний как недопустимое или неправильное значение, то ни ошибка, ни значение коррекции не импортируются.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-155">If a correction value appears in the knowledge base as an invalid or error value, neither the error nor the correction value will be imported.</span></span>  
  
-   <span data-ttu-id="c0fbe-156">Если домен является частью составного домена и очистка была проведена для составного домена, значения не импортируются.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-156">If the domain is part of a composite domain, and the cleansing was performed on the composite domain, no values will be imported.</span></span>  
  
-   <span data-ttu-id="c0fbe-157">Импортировать значения из проекта можно только тогда, когда база знаний имеет состояние «в обработке» и заблокирована пользователем, выполняющим импорт.</span><span class="sxs-lookup"><span data-stu-id="c0fbe-157">You can import values from a project only when the knowledge base has a state of in-work and the knowledge base is locked by the user who is importing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fbe-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0fbe-158">See Also</span></span>  
 <span data-ttu-id="c0fbe-159">[Очистка данных](../../2014/data-quality-services/data-cleansing.md) </span><span class="sxs-lookup"><span data-stu-id="c0fbe-159">[Data Cleansing](../../2014/data-quality-services/data-cleansing.md) </span></span>  
 [<span data-ttu-id="c0fbe-160">Преобразование "Очистка DQS"</span><span class="sxs-lookup"><span data-stu-id="c0fbe-160">DQS Cleansing Transformation</span></span>](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md)  
  
  
