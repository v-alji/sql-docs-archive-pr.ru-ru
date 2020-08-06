---
title: Автономные документы для SQL Server 2014
description: Узнайте, как установить автономную документацию для SQL Server 2014. Используйте SQL Server Management Studio (SSMS) для просмотра автономного содержимого.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659086"
---
# <a name="install-sql-server-2014-offline-documentation"></a><span data-ttu-id="ad8ca-104">Автономная документация по установке SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ad8ca-104">Install SQL Server 2014 offline documentation</span></span>

<span data-ttu-id="ad8ca-105">В этой статье описывается, как загрузить и просмотреть автономное содержимое SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-105">This article describes how to download and view offline SQL Server 2014 content.</span></span> <span data-ttu-id="ad8ca-106">Автономное содержимое позволяет получить доступ к документации без подключения к Интернету (хотя изначально для загрузки требуется подключение к Интернету).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-106">Offline content enables you to access the documentation without an internet connection (although an internet connection is initially required to download it).</span></span>

<span data-ttu-id="ad8ca-107">Этот метод включает использование меню « **Справка** » SQL Server Management Studio (SSMS) для доступа к служебной программе просмотра справки (HlpViewer.exe).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-107">The technique involves using the **Help** menu of SQL Server Management Studio (SSMS), to access the Help Viewer utility (HlpViewer.exe).</span></span>

<span data-ttu-id="ad8ca-108">Автономная документация доступна для версий SQL Server в диапазоне 2012-2019 и, возможно, для других версий.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-108">Offline documentation is available for versions of SQL Server in the range of 2012-2019, and perhaps for additional later versions too.</span></span> <span data-ttu-id="ad8ca-109">Хотя вы можете [просматривать содержимое для предыдущих версий в Интернете](https://docs.microsoft.com/previous-versions/sql/), параметр автономного режима обеспечивает удобный способ доступа к старому содержимому.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-109">Although you can view content for [previous versions online](https://docs.microsoft.com/previous-versions/sql/), an offline option provides a convenient way to access the older content.</span></span>

- [<span data-ttu-id="ad8ca-110">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ad8ca-110">SQL Server 2014</span></span>](#sql-server-2014-offline-content)
- [<span data-ttu-id="ad8ca-111">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ad8ca-111">SQL Server 2012</span></span>](#sql-server-2012-offline-content)

<span data-ttu-id="ad8ca-112">Для SQL Server 2016 и более поздних версий ознакомьтесь с документацией по конкретной версии, чтобы узнать, как эти версии обрабатывали свою автономную документацию.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-112">For SQL Server 2016 and later versions, see their version-specific documentation to learn how those versions handle their offline documentation.</span></span>

## <a name="sql-server-2014-offline-content"></a><span data-ttu-id="ad8ca-113">Автономное содержимое для SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ad8ca-113">SQL Server 2014 offline content</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad8ca-114">Содержимое для SQL 2014 Transact-SQL доступно только в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-114">SQL 2014 Transact-SQL content is only available offline.</span></span>

<span data-ttu-id="ad8ca-115">Ниже описаны действия по загрузке автономного содержимого для SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-115">The following steps explain how to load offline content for SQL Server 2014.</span></span>

1. <span data-ttu-id="ad8ca-116">Скачайте содержимое [документации по продукту Microsoft SQL Server 2014 для сред с брандмауэром и прокси-сервером](https://www.microsoft.com/download/details.aspx?id=42557) из центра загрузки и сохраните его в папке.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-116">Download the [Product Documentation for Microsoft SQL Server 2014 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=42557) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="ad8ca-117">Распакуйте файл, чтобы просмотреть файл *MSHA* .</span><span class="sxs-lookup"><span data-stu-id="ad8ca-117">Unzip the file to view the *.msha* file.</span></span>

   ![Файл установки справочной документации по SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. <span data-ttu-id="ad8ca-119">В SSMS в меню "Справка" выберите пункт **Добавление и удаление содержимого справки**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-119">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Пункт меню "Добавление и удаление содержимого справки" в окне справки](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="ad8ca-121">В окне справки откроется вкладка "Управление содержимым".</span><span class="sxs-lookup"><span data-stu-id="ad8ca-121">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="ad8ca-122">Чтобы установить новейшее содержимое справки, выберите **Диск** в разделе источника установки, а затем — многоточие (...).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-122">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Выбор диска в качестве источника на вкладке "Управление содержимым" в окне справки](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="ad8ca-124">На вкладке "Управление содержимым" в поле Local store path (Путь к локальному хранилищу) отображается расположение содержимого на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-124">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="ad8ca-125">Чтобы изменить расположение, щелкните **Переместить**, в поле **Куда** введите путь к другой папке, а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-125">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="ad8ca-126">Если не удается установить справку после изменения пути к локальному хранилищу, закройте и снова откройте средство просмотра справки.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-126">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="ad8ca-127">Убедитесь, что новое расположение есть в пути к локальному хранилищу, а затем повторите попытку установки.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-127">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="ad8ca-128">Откройте папку, в которую вы распаковали содержимое.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-128">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="ad8ca-129">Выберите в папке файл **HelpContentSetup.msha**, а затем щелкните **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-129">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Открытие файла HelpContentSetup.msha SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. <span data-ttu-id="ad8ca-131">В строке поиска введите *sql server 2014*.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-131">Type in *sql server 2014* in the search bar.</span></span> <span data-ttu-id="ad8ca-132">Получив доступ к содержимому 2014, выберите **Добавить** рядом с каждым пакетом содержимого (документацией), который необходимо установить в окне справки, а затем выберите **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-132">Once you see the 2014 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Поиск документации SQL Server 2014 в окне справки](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Добавление и обновление документации SQL Server 2014 в окне справки](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="ad8ca-135">Если средство просмотра справки зависнет (зависает) при добавлении содержимого, измените строку Cache Ластрефрешед = " \<mm/dd/yyyy> 00:00:00" в файле%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings или HlpViewer_VisualStudiox_en-US. Settings на некоторое время в будущем.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-135">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="ad8ca-136">Сведения об этой проблеме см. в разделе [Окно справки Visual Studio зависает](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-136">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="ad8ca-137">Проверить загрузку содержимого SQL Server 2014 можно, выполнив поиск в области содержимого слева, введя *sql server 2014*.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-137">You can verify that the SQL Server 2014 content installed by searching under the content pane on the left for *sql server 2014*.</span></span>

   ![Автоматическое обновление документации SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a><span data-ttu-id="ad8ca-139">Автономное содержимое для SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ad8ca-139">SQL Server 2012 offline content</span></span>

<span data-ttu-id="ad8ca-140">Ниже описаны действия по загрузке автономного содержимого для SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-140">The following steps explain how to load offline content for SQL Server 2012</span></span>

1. <span data-ttu-id="ad8ca-141">Скачайте содержимое [документации по продукту Microsoft SQL Server 2012 для сред с брандмауэром и прокси-сервером](https://www.microsoft.com/download/details.aspx?id=35750) из центра загрузки и сохраните его в папке.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-141">Download the [Product Documentation for Microsoft SQL Server 2012 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=35750) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="ad8ca-142">Распакуйте файл, чтобы просмотреть файл *MSHA* .</span><span class="sxs-lookup"><span data-stu-id="ad8ca-142">Unzip the file to view the *.msha* file.</span></span>

   ![Файл установки содержимого справки SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. <span data-ttu-id="ad8ca-144">В SSMS в меню "Справка" выберите пункт **Добавление и удаление содержимого справки**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-144">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Пункт меню "Добавление и удаление содержимого справки" в окне справки](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="ad8ca-146">В окне справки откроется вкладка "Управление содержимым".</span><span class="sxs-lookup"><span data-stu-id="ad8ca-146">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="ad8ca-147">Чтобы установить новейшее содержимое справки, выберите **Диск** в разделе источника установки, а затем — многоточие (...).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-147">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Выбор диска в качестве источника на вкладке "Управление содержимым" в окне справки](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="ad8ca-149">На вкладке "Управление содержимым" в поле Local store path (Путь к локальному хранилищу) отображается расположение содержимого на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-149">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="ad8ca-150">Чтобы изменить расположение, щелкните **Переместить**, в поле **Куда** введите путь к другой папке, а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-150">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="ad8ca-151">Если не удается установить справку после изменения пути к локальному хранилищу, закройте и снова откройте средство просмотра справки.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-151">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="ad8ca-152">Убедитесь, что новое расположение есть в пути к локальному хранилищу, а затем повторите попытку установки.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-152">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="ad8ca-153">Откройте папку, в которую вы распаковали содержимое.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-153">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="ad8ca-154">Выберите в папке файл **HelpContentSetup.msha**, а затем щелкните **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-154">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Открытие файла HelpContentSetup.msha SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. <span data-ttu-id="ad8ca-156">В строке поиска введите *sql server 2012*.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-156">Type in *sql server 2012* in the search bar.</span></span> <span data-ttu-id="ad8ca-157">Получив доступ к содержимому 2012, выберите **Добавить** рядом с каждым пакетом содержимого (документацией), который необходимо установить в окне справки, а затем выберите **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-157">Once you see the 2012 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Поиск документации SQL Server 2012 в окне справки](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Добавление и обновление документации SQL Server 2012 в окне справки](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="ad8ca-160">Если средство просмотра справки зависнет (зависает) при добавлении содержимого, измените строку Cache Ластрефрешед = " \<mm/dd/yyyy> 00:00:00" в файле%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings или HlpViewer_VisualStudiox_en-US. Settings на некоторое время в будущем.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-160">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="ad8ca-161">Сведения об этой проблеме см. в разделе [Окно справки Visual Studio зависает](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-161">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="ad8ca-162">Проверить загрузку содержимого SQL Server 2012 можно, выполнив поиск в области содержимого слева, введя *sql server 2012*.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-162">You can verify that the SQL Server 2012 content is loaded by searching under the content pane on the left for *sql server 2012*.</span></span>

   ![Автоматическое обновление документации SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a><span data-ttu-id="ad8ca-164">Просмотр автономной документации</span><span class="sxs-lookup"><span data-stu-id="ad8ca-164">View offline documentation</span></span>

<span data-ttu-id="ad8ca-165">Содержимое справки SQL Server можно просмотреть с помощью меню " **Справка** " в последней версии SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="ad8ca-165">You can view SQL Server help content using the **HELP** menu in the latest version of SQL Server Management Studio (SSMS).</span></span>

### <a name="view-offline-help-content-in-ssms"></a><span data-ttu-id="ad8ca-166">Просмотр автономного содержимого справки в SSMS</span><span class="sxs-lookup"><span data-stu-id="ad8ca-166">View offline help content in SSMS</span></span>

<span data-ttu-id="ad8ca-167">Чтобы просмотреть установленную справку в SSMS, выберите в меню справки пункт **Запустить в средстве просмотра справки**, чтобы открыть окно справки.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-167">To view the installed help in SSMS, select **Launch in Help Viewer** from the Help menu, to launch the Help Viewer.</span></span>

   ![Пункт меню "Запустить в средстве просмотра справки"](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

<span data-ttu-id="ad8ca-169">В окне справки откроется вкладка "Управление содержимым" с таблицей содержимого установленной справки в левой области.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-169">Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane.</span></span> <span data-ttu-id="ad8ca-170">Выберите статьи в таблице содержимого, чтобы просмотреть их в правой области.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-170">select articles in the table of contents to display them in the right pane.</span></span>

> [!Important]
> <span data-ttu-id="ad8ca-171">Если область содержимого не отображается, щелкните "Содержимое" в левом поле.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-171">If the contents pane is not visible, select Contents on the left margin.</span></span> <span data-ttu-id="ad8ca-172">Чтобы область содержимого не закрывалась, щелкните значок канцелярской кнопки.</span><span class="sxs-lookup"><span data-stu-id="ad8ca-172">select the pushpin icon to keep the contents pane open.</span></span>  

   ![Окно справки с содержимым](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
