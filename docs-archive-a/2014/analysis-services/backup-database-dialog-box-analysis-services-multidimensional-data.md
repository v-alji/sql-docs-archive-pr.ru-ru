---
title: Диалоговое окно "резервное копирование базы данных" (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Backup.f1
ms.assetid: 7811ce7d-6c37-4189-bfa6-ef36fb4932db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 48cf094353c53213864dae656af94ae791442105
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656872"
---
# <a name="backup-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6784e-102">Диалоговое окно «Создание резервной копии базы данных» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="6784e-102">Backup Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6784e-103">Используйте диалоговое окно **Создание резервной копии базы данных** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , чтобы осуществлять резервное копирование базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в файл резервной копии, использующий формат файла резервной копии служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ABF).</span><span class="sxs-lookup"><span data-stu-id="6784e-103">Use the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to back up an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6784e-104">Пользователь, выполняющий команду резервного копирования, должен иметь разрешение на запись в папку резервного копирования, указанную для каждого копируемого файла.</span><span class="sxs-lookup"><span data-stu-id="6784e-104">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="6784e-105">Кроме того, пользователь должен быть членом одной из следующих ролей: роль сервера для экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или роль базы данных с разрешениями "Полный доступ (администратор)" в базе данных, для которой создается резервная копия.</span><span class="sxs-lookup"><span data-stu-id="6784e-105">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="6784e-106">**Отображение диалогового окна «Создание резервной копии базы данных»**</span><span class="sxs-lookup"><span data-stu-id="6784e-106">**To display the Backup Database dialog box**</span></span>  
  
-   <span data-ttu-id="6784e-107">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши папку **Базы данных** экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базу данных в **обозревателе объектов**, а затем выберите команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="6784e-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Backup**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6784e-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="6784e-108">Options</span></span>  
 <span data-ttu-id="6784e-109">**Сценарий**</span><span class="sxs-lookup"><span data-stu-id="6784e-109">**Script**</span></span>  
 <span data-ttu-id="6784e-110">Создает скрипт резервного копирования, основанный на параметрах, выбранных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="6784e-110">Creates a backup script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="6784e-111">Скрипт восстановления написан на языке скриптов служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).</span><span class="sxs-lookup"><span data-stu-id="6784e-111">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="6784e-112">Щелкнув значок **скрипт** , можно отправить скрипт резервного копирования в новое окно запроса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6784e-112">Clicking the **Script** icon sends the backup script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="6784e-113">Щелкнув стрелку **скрипт** , можно открыть меню, в котором можно выбрать, куда отправить скрипт резервного копирования:</span><span class="sxs-lookup"><span data-stu-id="6784e-113">Clicking the **Script** arrow displays a menu that allows you to choose where to send the backup script:</span></span>  
  
-   <span data-ttu-id="6784e-114">в новое окно запроса (по умолчанию);</span><span class="sxs-lookup"><span data-stu-id="6784e-114">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="6784e-115">в файл;</span><span class="sxs-lookup"><span data-stu-id="6784e-115">To a file.</span></span>  
  
-   <span data-ttu-id="6784e-116">в буфер обмена;</span><span class="sxs-lookup"><span data-stu-id="6784e-116">To the clipboard.</span></span>  
  
-   <span data-ttu-id="6784e-117">в задание.</span><span class="sxs-lookup"><span data-stu-id="6784e-117">To a job.</span></span>  
  
 <span data-ttu-id="6784e-118">**База данных**</span><span class="sxs-lookup"><span data-stu-id="6784e-118">**Database**</span></span>  
 <span data-ttu-id="6784e-119">Отображает имя выбранной базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6784e-119">Displays the name of the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="6784e-120">**Файл резервной копии**</span><span class="sxs-lookup"><span data-stu-id="6784e-120">**Backup file**</span></span>  
 <span data-ttu-id="6784e-121">Введите полный путь и имя файла резервной копии, который нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="6784e-121">Type the full path and file name of the backup file to use.</span></span>  
  
 <span data-ttu-id="6784e-122">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="6784e-122">**Browse**</span></span>  
 <span data-ttu-id="6784e-123">Нажмите, чтобы отобразить диалоговое окно **Сохранение файла** и выбрать путь и имя файла резервной копии, которые нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="6784e-123">Click to display the **Save File As** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="6784e-124">Дополнительные сведения о диалоговом окне **Сохранение файла** см. в разделе [Диалоговое окно "Сохранение файла" (службы Analysis Services — многомерные данные)](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="6784e-124">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="6784e-125">**Разрешить перезапись файла**</span><span class="sxs-lookup"><span data-stu-id="6784e-125">**Allow file overwrite**</span></span>  
 <span data-ttu-id="6784e-126">Выберите, чтобы разрешить перезапись существующего файла резервной копии или удаленного файла резервной копии, если таковой существует.</span><span class="sxs-lookup"><span data-stu-id="6784e-126">Select to overwrite an existing backup file or remote backup file, if one exists.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6784e-127"> Может произойти ошибка, если этот параметр не выбран, но существует файл резервной копии, указанный в пункте **Файл резервной копии** , или удаленный файл резервной копии, указанный в пункте **Удаленный файл резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="6784e-127">If this option is not selected and the backup file specified in **Backup file** or a remote backup file specified in **Remote backup file** exists, an error occurs.</span></span>  
  
 <span data-ttu-id="6784e-128">**Выполнить сжатие**</span><span class="sxs-lookup"><span data-stu-id="6784e-128">**Apply compression**</span></span>  
 <span data-ttu-id="6784e-129">Выберите, чтобы сжать содержимое файла резервной копии и, если указано, удаленных файлов резервной копии.</span><span class="sxs-lookup"><span data-stu-id="6784e-129">Select to compress the contents of the backup file and, if specified, remote backup files.</span></span>  
  
 <span data-ttu-id="6784e-130">**Зашифровать файл резервной копии**</span><span class="sxs-lookup"><span data-stu-id="6784e-130">**Encrypt backup file**</span></span>  
 <span data-ttu-id="6784e-131">Выберите, чтобы зашифровать файл резервной копии, используя пароль, указанный в пункте **Пароль**.</span><span class="sxs-lookup"><span data-stu-id="6784e-131">Select to encrypt the backup file using the password supplied in **Password**.</span></span>  
  
 <span data-ttu-id="6784e-132">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="6784e-132">**Password**</span></span>  
 <span data-ttu-id="6784e-133">Введите пароль для использования при шифровании содержимого файла резервной копии и, если указано, удаленных файлов резервной копии.</span><span class="sxs-lookup"><span data-stu-id="6784e-133">Type the password to use when encrypting the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6784e-134"> Этот параметр включен, только если выбран пункт **Зашифровать файл резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="6784e-134">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="6784e-135">**Подтвердите пароль**</span><span class="sxs-lookup"><span data-stu-id="6784e-135">**Confirm Password**</span></span>  
 <span data-ttu-id="6784e-136">Введите еще раз пароль, введенный в пункте **Пароль** , чтобы подтвердить его для файла резервной копии и, если указано, удаленных файлов резервной копии.</span><span class="sxs-lookup"><span data-stu-id="6784e-136">Type the password entered in **Password** to confirm the password for the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6784e-137"> Этот параметр включен, только если выбран пункт **Зашифровать файл резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="6784e-137">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="6784e-138">**Создать резервную копию удаленных секций**</span><span class="sxs-lookup"><span data-stu-id="6784e-138">**Backup remote partition(s)**</span></span>  
 <span data-ttu-id="6784e-139">Выберите, чтобы включить в файл резервной копии информацию о местоположении и данные удаленных секций.</span><span class="sxs-lookup"><span data-stu-id="6784e-139">Select to include location information and data for remote partitions in the backup file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6784e-140">Этот параметр включен, только если в базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , выбранной в настоящий момент, используются удаленные секции.</span><span class="sxs-lookup"><span data-stu-id="6784e-140">This option is enabled only if the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database uses remote partitions.</span></span>  
  
 <span data-ttu-id="6784e-141">**Местонахождение резервной копии удаленных секций**</span><span class="sxs-lookup"><span data-stu-id="6784e-141">**Remote partition backup location**</span></span>  
 <span data-ttu-id="6784e-142">Отображает местоположение удаленных секций, связанных с выбранной базой данных, а также местоположение удаленного файла резервной копии, используемого для резервного копирования данных и метаданных удаленных секций.</span><span class="sxs-lookup"><span data-stu-id="6784e-142">Displays the location of remote partitions associated with the selected database, as well as the remote backup file used to back up the data and metadata for the remote partitions.</span></span> <span data-ttu-id="6784e-143">Доступны следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="6784e-143">The following columns are available:</span></span>  
  
|<span data-ttu-id="6784e-144">Столбец</span><span class="sxs-lookup"><span data-stu-id="6784e-144">Column</span></span>|<span data-ttu-id="6784e-145">Описание</span><span class="sxs-lookup"><span data-stu-id="6784e-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6784e-146">**Server**</span><span class="sxs-lookup"><span data-stu-id="6784e-146">**Server**</span></span>|<span data-ttu-id="6784e-147">Отображает экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , управляющий удаленными секциями.</span><span class="sxs-lookup"><span data-stu-id="6784e-147">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that manages the remote partitions.</span></span>|  
|<span data-ttu-id="6784e-148">**База данных**</span><span class="sxs-lookup"><span data-stu-id="6784e-148">**Database**</span></span>|<span data-ttu-id="6784e-149">Отображает базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которая содержит удаленные секции.</span><span class="sxs-lookup"><span data-stu-id="6784e-149">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the remote partitions.</span></span>|  
|<span data-ttu-id="6784e-150">**Список секций**</span><span class="sxs-lookup"><span data-stu-id="6784e-150">**Partition List**</span></span>|<span data-ttu-id="6784e-151">Отображает список удаленных секций, содержащихся в базе данных, отображенной в пункте **База данных**.</span><span class="sxs-lookup"><span data-stu-id="6784e-151">Displays the list of remote partitions contained by the database displayed in **Database**.</span></span>|  
|<span data-ttu-id="6784e-152">**Удаленный файл резервной копии**</span><span class="sxs-lookup"><span data-stu-id="6784e-152">**Remote backup file**</span></span>|<span data-ttu-id="6784e-153">Введите полный путь и имя удаленного файла резервной копии, который следует использовать, либо нажмите кнопку с многоточием (**...**), чтобы отобразить диалоговое окно **Сохранение файла** и выбрать путь и имя удаленного файла резервной копии, который следует использовать.</span><span class="sxs-lookup"><span data-stu-id="6784e-153">Type the full path and file name of the remote backup file to use, or click the ellipsis button (**...**) to display the **Save File As** dialog box and select the path and file name of the remote backup file to use.</span></span> <span data-ttu-id="6784e-154">Дополнительные сведения о диалоговом окне **Сохранение файла** см. в разделе [Диалоговое окно "Сохранение файла" (службы Analysis Services — многомерные данные)](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="6784e-154">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6784e-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="6784e-155">See Also</span></span>  
 <span data-ttu-id="6784e-156">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="6784e-156">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="6784e-157">Создание и восстановление резервных копий баз данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6784e-157">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
