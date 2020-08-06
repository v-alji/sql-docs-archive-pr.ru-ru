---
title: Импорт доменов из файла Excel при обнаружении набора знаний | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 4d3a3940-6c2a-4dc4-90eb-86f26012c165
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 332045466b95088523acda97a931168b0bb5c1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666222"
---
# <a name="import-domains-from-an-excel-file-in-knowledge-discovery"></a><span data-ttu-id="84009-102">Импорт доменов из файла Excel при обнаружении набора знаний</span><span class="sxs-lookup"><span data-stu-id="84009-102">Import Domains from an Excel File in Knowledge Discovery</span></span>
  <span data-ttu-id="84009-103">В этом разделе описывается, как импортировать один или несколько доменов из файла Excel в действие обнаружения знаний [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="84009-103">This topic describes how to import one or more domains from an Excel file in the [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) knowledge discovery activity.</span></span> <span data-ttu-id="84009-104">Процесс импорта упрощает процесс формирования набора знаний, экономя время и силы.</span><span class="sxs-lookup"><span data-stu-id="84009-104">The import process simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="84009-105">Это позволяет пользователям, у которых данные хранятся в файлах Excel или текстовых файлах, создавать базу знаний с применением этих данных.</span><span class="sxs-lookup"><span data-stu-id="84009-105">It enables people who have data in an Excel file or a text file to create a knowledge base with that data.</span></span> <span data-ttu-id="84009-106">(Дополнительные сведения об импорте значений в домен существующей базы знаний см. [в разделе Импорт значений из файла Excel в домен](../../2014/data-quality-services/import-values-from-an-excel-file-into-a-domain.md) .) Экспорт в файл Excel не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="84009-106">(See [Import Values from an Excel File into a Domain](../../2014/data-quality-services/import-values-from-an-excel-file-into-a-domain.md) for more information about importing values into a domain of an existing knowledge base.) Exporting to an Excel file is not supported.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="84009-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="84009-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="84009-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="84009-108">Prerequisites</span></span>  
 <span data-ttu-id="84009-109">Для импорта доменов из файла Excel необходимо установить Microsoft Excel на компьютер, на котором установлено приложение [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] . Необходимо создать файл Excel со значениями домена (см. раздел [How the import works](#How)). Кроме того, необходимо создать и открыть базу знаний, в которую будет импортироваться домен.</span><span class="sxs-lookup"><span data-stu-id="84009-109">To import domains from an Excel file, Excel must be installed on the computer that the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] is installed on; you must have created an Excel file with domain values (see [How the import works](#How)); and you must have created and opened a knowledge base to import the domain into.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="84009-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="84009-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="84009-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="84009-111">Permissions</span></span>  
 <span data-ttu-id="84009-112">Для импорта доменов из файла Excel необходимо иметь роль dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="84009-112">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import domains from an Excel file.</span></span>  
  
##  <a name="import-domains-from-an-excel-file-into-a-knowledge-base"></a><a name="Import"></a> <span data-ttu-id="84009-113">Импорт доменов из файла Excel в базу знаний</span><span class="sxs-lookup"><span data-stu-id="84009-113">Import domains from an Excel file into a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="84009-114">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="84009-114">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="84009-115">На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="84009-115">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, do one of the following:</span></span>  
  
    -   <span data-ttu-id="84009-116">Создайте новую базу знаний для импорта данных. Для этого нажмите кнопку **Создать базу знаний**, введите имя базы знаний, выберите **Нет** в поле **Создать базу знаний из**, выберите действие **Обнаружение набора знаний** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="84009-116">Create a new knowledge base to import into by clicking **New knowledge base**, entering a name for the knowledge base, selecting **None** for **Create knowledge base from**, selecting the **Knowledge Discovery** activity, and then clicking **Create**.</span></span>  
  
    -   <span data-ttu-id="84009-117">Откройте существующую базу знаний для импорта. Для этого нажмите кнопку **Открыть базу знаний**, выберите базу знаний, выберите **Обнаружение набора знаний**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84009-117">Open an existing knowledge base to import into by clicking **Open knowledge base**, selecting the knowledge base, selecting **Knowledge Discovery**, and then clicking **Next**.</span></span>  
  
3.  <span data-ttu-id="84009-118">На странице **Сопоставление** выберите **Файл Excel** как **Источник данных**.</span><span class="sxs-lookup"><span data-stu-id="84009-118">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
4.  <span data-ttu-id="84009-119">Нажмите кнопку **Обзор** в строке **Файл Excel** .</span><span class="sxs-lookup"><span data-stu-id="84009-119">Click **Browse** on the **Excel File** line.</span></span>  
  
5.  <span data-ttu-id="84009-120">В диалоговом окне **Выбрать файл Excel** перейдите в папку с файлом Excel, из которого будут импортироваться данные, выберите файл Excel и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="84009-120">In the **Select an Excel File** dialog box, move to the folder that contains the Excel file that you want to import from, select the Excel file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="84009-121">В раскрывающемся списке **Лист** выберите лист в файле Excel, откуда будет осуществляться импорт.</span><span class="sxs-lookup"><span data-stu-id="84009-121">From the **Worksheet** drop-down list, select the worksheet in the Excel file that you want to import from.</span></span>  
  
7.  <span data-ttu-id="84009-122">Выберите **Использовать первую строку как заголовок** , если следует рассматривать первую строку как заголовок данных, а значения в первой строке как имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="84009-122">Select **Use First Row as header** if you want the first row to be considered a data header, and if you want the values in the first row to be used as column names.</span></span> <span data-ttu-id="84009-123">Отмените выбор варианта **Использовать первую строку как заголовок** , если содержимое первой строки должно рассматриваться как значение данных. В этом случае службы DQS будут использовать в качестве заголовков имена столбцов Excel (буквы алфавита).</span><span class="sxs-lookup"><span data-stu-id="84009-123">Deselect **Use First Row as header** if you want the first row to be considered a data value, in which case DQS will use the Excel header names (alphabetical letters) for the column.</span></span>  
  
8.  <span data-ttu-id="84009-124">Выберите столбец, затем либо сопоставьте с ним существующий домен, либо создайте новый домен. Для этого щелкните значок **Создать домен** , в результате чего откроется диалоговое окно **Создать домен** , затем сопоставьте домен со столбцом.</span><span class="sxs-lookup"><span data-stu-id="84009-124">Select a column, and then either map an existing domain to the column, or create a new domain by clicking the **Create a Domain** icon, creating a domain in the **Create a domain** dialog box, and then mapping the domain to the column.</span></span> <span data-ttu-id="84009-125">Тип данных домена должен совпадать с типом данных столбца.</span><span class="sxs-lookup"><span data-stu-id="84009-125">The data type of the domain must match the data type of the column.</span></span> <span data-ttu-id="84009-126">Повторите эти действия для всех столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="84009-126">Repeat for all columns of the spreadsheet.</span></span>  
  
9. <span data-ttu-id="84009-127">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84009-127">Click **Next**.</span></span>  
  
10. <span data-ttu-id="84009-128">На странице **Обнаружение** выберите **Пуск** , чтобы запустить анализ данных в электронной таблице Excel.</span><span class="sxs-lookup"><span data-stu-id="84009-128">In the **Discover** page, click **Start** to analyze the data in the Excel spreadsheet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84009-129">Если вы выйдете из этой страницы до того, как будут переданы данные, процесс передачи файла будет прерван.</span><span class="sxs-lookup"><span data-stu-id="84009-129">If you leave the page before the data has been uploaded, the file upload process will be terminated.</span></span>  
  
11. <span data-ttu-id="84009-130">Убедитесь, что анализ завершен успешно, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84009-130">Verify that the analysis completed successfully, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="84009-131">На странице **Управление значениями домена** проверьте правильность списка **Домены** , а также наличие значений в таблице доменов.</span><span class="sxs-lookup"><span data-stu-id="84009-131">In the **Manage Domain Values** page, verify that the correct domains are listed in the **Domains** list and that values are entered in the domain table.</span></span>  
  
13. <span data-ttu-id="84009-132">Нажмите кнопку **Готово**, затем кнопку **Опубликовать** , чтобы опубликовать базу знаний, либо **Нет** , чтобы не публиковать.</span><span class="sxs-lookup"><span data-stu-id="84009-132">Click **Finish**, and then click **Publish** to publish the knowledge base, or **No** not to publish.</span></span>  
  
14. <span data-ttu-id="84009-133">Убедитесь, что база знаний опубликована, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="84009-133">Verify that the knowledge base was published, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-importing-domains-from-an-excel-file"></a><a name="FollowUp"></a><span data-ttu-id="84009-134">Дальнейшие действия. После импорта доменов из файла Excel</span><span class="sxs-lookup"><span data-stu-id="84009-134">Follow Up: After Importing Domains from an Excel File</span></span>  
 <span data-ttu-id="84009-135">После импорта доменов из файла Excel можно добавить наборы знаний в домены или использовать домены в проекте очистки данных или сопоставления в зависимости от содержания доменов.</span><span class="sxs-lookup"><span data-stu-id="84009-135">After you import domains from an Excel file, you can add knowledge to the domains or use the domains in a cleansing or matching project, depending on the contents of the domains.</span></span> <span data-ttu-id="84009-136">Дополнительные сведения см. в разделах [Обнаружение знаний](../../2014/data-quality-services/perform-knowledge-discovery.md), [Управление доменом](../../2014/data-quality-services/managing-a-domain.md), [Управление составным доменом](../../2014/data-quality-services/managing-a-composite-domain.md), [Создание политики сопоставления](../../2014/data-quality-services/create-a-matching-policy.md), [Очистка данных](../../2014/data-quality-services/data-cleansing.md) и [Сопоставление данных](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="84009-136">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
##  <a name="how-the-import-works"></a><a name="How"></a><span data-ttu-id="84009-137">Принцип работы импорта</span><span class="sxs-lookup"><span data-stu-id="84009-137">How the import works</span></span>  
 <span data-ttu-id="84009-138">В ходе операции импорта служба DQS интерпретирует файл Excel следующим образом:</span><span class="sxs-lookup"><span data-stu-id="84009-138">In the import operation, DQS interprets an Excel file as follows:</span></span>  
  
-   <span data-ttu-id="84009-139">Столбец представляет домен</span><span class="sxs-lookup"><span data-stu-id="84009-139">A column represents a domain</span></span>  
  
-   <span data-ttu-id="84009-140">Строка представляет запись данных</span><span class="sxs-lookup"><span data-stu-id="84009-140">A row represents a data record</span></span>  
  
-   <span data-ttu-id="84009-141">Первая строка представляет имена доменов либо первое значение или запись данных, в зависимости от того, установлен ли флажок **Использовать первую строку в качестве заголовка** .</span><span class="sxs-lookup"><span data-stu-id="84009-141">The first row either represents domain names or is the first data value or record, depending upon the setting of the **Use First Row as header** checkbox.</span></span>  
  
 <span data-ttu-id="84009-142">Для операции импорта действуют следующие правила.</span><span class="sxs-lookup"><span data-stu-id="84009-142">The following rules apply to the import operation:</span></span>  
  
-   <span data-ttu-id="84009-143">Эта операция импортирует значения домена в базу знаний.</span><span class="sxs-lookup"><span data-stu-id="84009-143">This operation imports domain values into a knowledge base.</span></span> <span data-ttu-id="84009-144">Правила домена или политика сопоставления не импортируются.</span><span class="sxs-lookup"><span data-stu-id="84009-144">It does not import domain rules or a matching policy.</span></span>  
  
-   <span data-ttu-id="84009-145">Файл Excel может иметь расширение .xlsx, .xls или .csv.</span><span class="sxs-lookup"><span data-stu-id="84009-145">The Excel file can have the extension .xlsx, .xls, or .csv.</span></span> <span data-ttu-id="84009-146">Чтобы можно было импортировать значения домена или весь домен, на компьютере c [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] необходимо установить Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="84009-146">Microsoft Excel must be installed on the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] computer to import domain values or a complete domain.</span></span> <span data-ttu-id="84009-147">Поддерживаются Excel 2003 и более поздние версии.</span><span class="sxs-lookup"><span data-stu-id="84009-147">Excel versions 2003 and later are supported.</span></span> <span data-ttu-id="84009-148">При использовании 64-разрядной версии Excel поддерживаются только файлы Excel 2003; файлы Excel 2007 и 2010 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="84009-148">If the 64-bit version of Excel is used, only Excel 2003 files will be supported; Excel 2007 or 2010 files will not be supported.</span></span>  
  
-   <span data-ttu-id="84009-149">Файлы Excel с расширением .xlsx не поддерживаются для 64-разрядной версии Excel.</span><span class="sxs-lookup"><span data-stu-id="84009-149">Excel files of type .xlsx are not supported for an Excel 64-bit installation.</span></span> <span data-ttu-id="84009-150">Если вы используете 64-разрядный Excel, сохраните файл электронной таблицы в виде XLS-файла.</span><span class="sxs-lookup"><span data-stu-id="84009-150">If you are using 64-bit Excel, save the spreadsheet file as an .xls file.</span></span>  
  
-   <span data-ttu-id="84009-151">В XLSX- и XLS-файлах тип данных столбца определяется по преобладающему типу данных в первых восьми строках.</span><span class="sxs-lookup"><span data-stu-id="84009-151">In .xlsx and .xls files, the data type of the column is determined by the most prevalent data type in the first eight rows.</span></span> <span data-ttu-id="84009-152">Если данные в ячейке не соответствуют данному типу, ячейке присваивается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="84009-152">If a cell does not conform to that data type, it will be given a null value.</span></span>  
  
-   <span data-ttu-id="84009-153">В CSV-файле тип данных определяется по преобладающему типу данных в первых восьми строках.</span><span class="sxs-lookup"><span data-stu-id="84009-153">In .csv files, the data type is determined by the most prevalent data type in the first eight rows.</span></span>  
  
-   <span data-ttu-id="84009-154">Значение в электронной таблице Excel, которое не соответствует правилу домена, импортируется как недопустимое значение.</span><span class="sxs-lookup"><span data-stu-id="84009-154">A value in an Excel spreadsheet that does not conform to a domain rule will be imported as an invalid value.</span></span>  
  
-   <span data-ttu-id="84009-155">Если файл Excel поврежден или представлен в недопустимом формате, операция импорта вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="84009-155">If the Excel file is not in the right format or is corrupted, the import operation will result in an error.</span></span>  
  
  
