---
title: Общие (диалоговое окно «Восстановление базы данных») (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.f1
ms.assetid: 319e7ef5-c9c7-4e50-8690-02a90aed006f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25a49e17227fc2ed6b7b18d2e0964cd8812cbdcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668500"
---
# <a name="general-restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="031b9-102">Общие (диалоговое окно «Восстановление базы данных») (службы Analysis Services - многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="031b9-102">General (Restore Database Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="031b9-103">Для задания файла резервной копии и общих настроек используется страница **Общие** диалогового окна **Восстановление базы данных** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] при восстановлении базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="031b9-103">Use the **General** page of the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to specify the backup file and general settings to use when restoring an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="031b9-104">Пользователь, выполняющий команду восстановления, должен иметь разрешение на чтение из папки резервного копирования, указанной для каждого восстанавливаемого файла.</span><span class="sxs-lookup"><span data-stu-id="031b9-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="031b9-105">Чтобы восстановить базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которая не установлена на сервере, пользователь также должен быть членом роли сервера для этого экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="031b9-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="031b9-106">Чтобы перезаписать базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , пользователь должен быть членом одной из следующих ролей: роль сервера для экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или роль базы данных с разрешениями "Полный доступ (администратор)" в восстанавливаемой базе данных.</span><span class="sxs-lookup"><span data-stu-id="031b9-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="031b9-107">После восстановления существующей базы данных пользователь, выполнявший восстановление, может утратить доступ к этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="031b9-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="031b9-108">Потеря доступа может произойти в случае, если на время создания резервной копии этот пользователь не был членом роли сервера и роли базы данных с разрешением «Полный доступ (Администратор)».</span><span class="sxs-lookup"><span data-stu-id="031b9-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="031b9-109">**Отображение страницы «Общие» в диалоговом окне «Восстановление базы данных»**</span><span class="sxs-lookup"><span data-stu-id="031b9-109">**To display the General page in the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="031b9-110">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши папку **Базы данных** экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базу данных в окне **Обозреватель объектов**, выберите пункт **Восстановить**, а затем на панели **Выбор страницы**выберите **Общие**.</span><span class="sxs-lookup"><span data-stu-id="031b9-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, click **Restore**, and then under **Select a page**, click **General**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="031b9-111">Варианты</span><span class="sxs-lookup"><span data-stu-id="031b9-111">Options</span></span>  
 <span data-ttu-id="031b9-112">**Сценарий**</span><span class="sxs-lookup"><span data-stu-id="031b9-112">**Script**</span></span>  
 <span data-ttu-id="031b9-113">Создает скрипт восстановления, основанный на параметрах, выбранных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="031b9-113">Creates a restore script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="031b9-114">Скрипт восстановления написан на языке скриптов служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="031b9-114">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="031b9-115">Щелкнув значок **Скрипт** , можно отправить скрипт восстановления в новое окно запроса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="031b9-115">Clicking the **Script** icon sends the restore script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="031b9-116">Щелкнув стрелку **Скрипт** , можно открыть меню, в котором можно выбрать, куда отправить скрипт восстановления:</span><span class="sxs-lookup"><span data-stu-id="031b9-116">Clicking the **Script** arrow displays a menu that allows you to choose where to send the restore script:</span></span>  
  
-   <span data-ttu-id="031b9-117">в новое окно запроса (по умолчанию);</span><span class="sxs-lookup"><span data-stu-id="031b9-117">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="031b9-118">в файл;</span><span class="sxs-lookup"><span data-stu-id="031b9-118">To a file.</span></span>  
  
-   <span data-ttu-id="031b9-119">в буфер обмена;</span><span class="sxs-lookup"><span data-stu-id="031b9-119">To the clipboard.</span></span>  
  
-   <span data-ttu-id="031b9-120">в задание.</span><span class="sxs-lookup"><span data-stu-id="031b9-120">To a job.</span></span>  
  
 <span data-ttu-id="031b9-121">**Восстановление базы данных**</span><span class="sxs-lookup"><span data-stu-id="031b9-121">**Restore database**</span></span>  
 <span data-ttu-id="031b9-122">Выберите базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для восстановления.</span><span class="sxs-lookup"><span data-stu-id="031b9-122">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to restore.</span></span>  
  
 <span data-ttu-id="031b9-123">**Из файла резервной копии**</span><span class="sxs-lookup"><span data-stu-id="031b9-123">**From backup file**</span></span>  
 <span data-ttu-id="031b9-124">Выберите файл резервной копии, из которого необходимо восстановить базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="031b9-124">Select the backup file from which to restore the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="031b9-125">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="031b9-125">**Browse**</span></span>  
 <span data-ttu-id="031b9-126">Выберите этот пункт для отображения диалогового окна **Расположение файлов базы данных**, а затем путь и имя файла резервной копии для использования.</span><span class="sxs-lookup"><span data-stu-id="031b9-126">Click to display the **Locate Database Files** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="031b9-127">Дополнительные сведения о диалоговом окне **Расположение файлов базы данных** см. в разделе [Диалоговое окно "Расположение файлов базы данных" (службы Analysis Services — многомерные данные)](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="031b9-127">For more information about the **Locate Database Files** dialog box, see [Locate Database Files Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="031b9-128">**Разрешить перезапись базы данных**</span><span class="sxs-lookup"><span data-stu-id="031b9-128">**Allow database overwrite**</span></span>  
 <span data-ttu-id="031b9-129">Выберите, чтобы разрешить службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] восстановить содержимое выбранного файла резервной копии, перезаписывая все существующие объекты в выбранной базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="031b9-129">Select to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to restore the contents of the selected backup file over any existing objects in the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="031b9-130">**Включить сведения о безопасности**</span><span class="sxs-lookup"><span data-stu-id="031b9-130">**Include security information**</span></span>  
 <span data-ttu-id="031b9-131">Выберите, чтобы скопировать все сведения о безопасности, хранимые в файле резервной копии, в базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="031b9-131">Select to copy any security information stored in the backup file to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="031b9-132">Если выбран этот параметр, то можно выбрать количество сведений о безопасности из раскрывающегося списка, который включается при выборе этого параметра.</span><span class="sxs-lookup"><span data-stu-id="031b9-132">If this option is selected, you can choose the amount of security information from the drop-down list enabled by selecting this option.</span></span> <span data-ttu-id="031b9-133">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="031b9-133">The following options are available:</span></span>  
  
|<span data-ttu-id="031b9-134">Параметр</span><span class="sxs-lookup"><span data-stu-id="031b9-134">Option</span></span>|<span data-ttu-id="031b9-135">Описание</span><span class="sxs-lookup"><span data-stu-id="031b9-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="031b9-136">**Копировать все**</span><span class="sxs-lookup"><span data-stu-id="031b9-136">**Copy All**</span></span>|<span data-ttu-id="031b9-137">Восстанавливает роли базы данных, содержащиеся в файле резервной копии, а также учетные записи пользователей, связанные с ролями.</span><span class="sxs-lookup"><span data-stu-id="031b9-137">Restores the database roles contained in the backup file, as well as the user accounts associated with the roles.</span></span>|  
|<span data-ttu-id="031b9-138">**Пропустить членство**</span><span class="sxs-lookup"><span data-stu-id="031b9-138">**Skip Membership**</span></span>|<span data-ttu-id="031b9-139">Восстанавливает роли базы данных, содержащиеся в файле резервной копии, но не восстанавливает учетные записи пользователей, связанные с ролями.</span><span class="sxs-lookup"><span data-stu-id="031b9-139">Restores the database roles contained in the backup file, but does not restore the user accounts associated with the roles.</span></span>|  
  
 <span data-ttu-id="031b9-140">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="031b9-140">**Password**</span></span>  
 <span data-ttu-id="031b9-141">Если файл резервной копии зашифрован, то введите пароль, использовавшийся для его шифрования.</span><span class="sxs-lookup"><span data-stu-id="031b9-141">If the backup file is encrypted, type the password used to encrypt the backup file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031b9-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="031b9-142">See Also</span></span>  
 <span data-ttu-id="031b9-143">[Диалоговое окно «Восстановление базы данных» &#40;Analysis Services многомерных данных&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="031b9-143">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="031b9-144">[Секции &#40;диалоговое окно «Восстановление базы данных»&#41; &#40;Analysis Services многомерных данных&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="031b9-144">[Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="031b9-145">Создание и восстановление резервных копий баз данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="031b9-145">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
