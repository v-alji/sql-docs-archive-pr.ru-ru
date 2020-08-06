---
title: Архивация базы данных (страница "Параметры резервного копирования") | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdatabase.options.f1
- swb.backupdatabase.options.f1
ms.assetid: df0ddcdb-c94e-472b-b786-469ae8117b93
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ffd527ba4334244c7fd4c5d4a73099093cb8520b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668952"
---
# <a name="back-up-database-backup-options-page"></a><span data-ttu-id="7cf00-102">Резервное копирование базы данных (страница «Параметры резервного копирования»)</span><span class="sxs-lookup"><span data-stu-id="7cf00-102">Back Up Database (Backup Options Page)</span></span>
  <span data-ttu-id="7cf00-103">На странице  **Параметры резервного копирования** диалогового окна **Резервное копирование базы данных** можно просмотреть или изменить параметры резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="7cf00-103">Use the  **Backup Options** page of the **Back Up Database** dialog box to view or modify database backup options.</span></span>  
  
 <span data-ttu-id="7cf00-104">**Создание резервной копии с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="7cf00-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="7cf00-105">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7cf00-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="7cf00-106">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7cf00-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7cf00-107">Для создания резервных копий базы данных можно составить план обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="7cf00-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="7cf00-108">Дополнительные сведения см. в статьях [Планы обслуживания](../maintenance-plans/maintenance-plans.md) и [Использование мастера планов обслуживания](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7cf00-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7cf00-109">Если задача резервного копирования определяется с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], можно создать соответствующий скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) , нажав кнопку **Скрипт** и выбрав место назначения для этого скрипта.</span><span class="sxs-lookup"><span data-stu-id="7cf00-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7cf00-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="7cf00-110">Options</span></span>  
  
### <a name="backup-set"></a><span data-ttu-id="7cf00-111">Резервный набор данных</span><span class="sxs-lookup"><span data-stu-id="7cf00-111">Backup set</span></span>  
 <span data-ttu-id="7cf00-112">Параметры панели **Резервный набор данных** позволяют указать необязательные сведения о резервном наборе данных, созданном операцией резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7cf00-112">The options of the **Backup set** panel allow for you to specify optional information about the backup set created by the back up operation.</span></span>  
  
 <span data-ttu-id="7cf00-113">**имя**;</span><span class="sxs-lookup"><span data-stu-id="7cf00-113">**Name**</span></span>  
 <span data-ttu-id="7cf00-114">Укажите имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="7cf00-114">Specify the backup set name.</span></span> <span data-ttu-id="7cf00-115">Система автоматически предложит имя по умолчанию на основе имени базы данных и типа резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7cf00-115">The system automatically suggests a default name based on the database name and the backup type.</span></span>  
  
 <span data-ttu-id="7cf00-116">Сведения о наборах резервных копий см. в разделе [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7cf00-116">For information about backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="7cf00-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7cf00-117">**Description**</span></span>  
 <span data-ttu-id="7cf00-118">Введите описание резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="7cf00-118">Enter a description of the backup set.</span></span>  
  
 <span data-ttu-id="7cf00-119">**Срок действия резервного набора данных истекает**</span><span class="sxs-lookup"><span data-stu-id="7cf00-119">**Backup set will expire**</span></span>  
 <span data-ttu-id="7cf00-120">Выберите один из следующих параметров истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="7cf00-120">Choose one of the following expiration options.</span></span> <span data-ttu-id="7cf00-121">Этот параметр будет отключен, если в качестве назначения резервного копирования выбран **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="7cf00-121">This option is disabled if **URL** is chosen as the backup destination.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cf00-122">**После:**</span><span class="sxs-lookup"><span data-stu-id="7cf00-122">**After**</span></span>|<span data-ttu-id="7cf00-123">Укажите количество дней до истечения срока действия резервного набора данных, после чего его можно будет перезаписать.</span><span class="sxs-lookup"><span data-stu-id="7cf00-123">Specify the number of days that must elapse before this backup set expires and can be overwritten.</span></span> <span data-ttu-id="7cf00-124">Это значение может быть задано в диапазоне от 0 до 99 999 дней. Значение 0 означает, что срок действия резервного набора данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="7cf00-124">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span><br /><br /> <span data-ttu-id="7cf00-125">Значение по умолчанию для срока действия резервного набора данных задается параметром **Срок хранения носителей резервных копий по умолчанию (дней)** .</span><span class="sxs-lookup"><span data-stu-id="7cf00-125">The default value for backup expiration is the value set in the **Default backup media retention (in days)** option.</span></span> <span data-ttu-id="7cf00-126">Чтобы задать этот параметр, щелкните правой кнопкой мыши имя сервера в обозревателе объектов и выберите пункт **Свойства**, а затем страницу **Параметры базы данных** в диалоговом окне **Свойства сервера** .</span><span class="sxs-lookup"><span data-stu-id="7cf00-126">To access this, right-click the server name in Object Explorer and select **Properties**; then click the **Database Settings** page of the **Server Properties** dialog box.</span></span>|  
|<span data-ttu-id="7cf00-127">**Вкл.**</span><span class="sxs-lookup"><span data-stu-id="7cf00-127">**On**</span></span>|<span data-ttu-id="7cf00-128">Укажите дату истечения срока действия резервного набора данных, после которого набор можно будет перезаписать.</span><span class="sxs-lookup"><span data-stu-id="7cf00-128">Specify a specific date when the backup set expires and can be overwritten.</span></span>|  
  
### <a name="compression"></a><span data-ttu-id="7cf00-129">Сжатие</span><span class="sxs-lookup"><span data-stu-id="7cf00-129">Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="7cf00-130">(и более поздние версии) поддерживает [сжатие резервной копии](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7cf00-130">(or a later version) supports [backup compression](backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="7cf00-131">**Установка сжатия резервной копии**</span><span class="sxs-lookup"><span data-stu-id="7cf00-131">**Set backup compression**</span></span>  
 <span data-ttu-id="7cf00-132">В выпуске [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (или более поздней версии) выберите одно из следующих значений сжатия резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7cf00-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (or a later version), select one of the following backup compression values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cf00-133">**Использовать параметр сервера по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="7cf00-133">**Use the default server setting**</span></span>|<span data-ttu-id="7cf00-134">Щелкните для использования настроек уровня сервера, установленных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7cf00-134">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="7cf00-135">Значения по умолчанию устанавливаются в параметре конфигурации сервера **backup compression default** .</span><span class="sxs-lookup"><span data-stu-id="7cf00-135">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="7cf00-136">Сведения о том, как просмотреть текущую настройку этого параметра, см. в разделе [Параметр конфигурации сервера "Просмотр или настройка параметра сжатия резервных копий по умолчанию"](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="7cf00-136">For information about how to view the current setting of this option, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="7cf00-137">**Сжимать резервные копии**</span><span class="sxs-lookup"><span data-stu-id="7cf00-137">**Compress backup**</span></span>|<span data-ttu-id="7cf00-138">Щелкните для сжатия резервной копии, независимо от уровня сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7cf00-138">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="7cf00-139">**\*\* Важно. \*\*** По умолчанию сжатие существенно повышает загрузку ЦП, что может помешать выполнению других операций.</span><span class="sxs-lookup"><span data-stu-id="7cf00-139">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="7cf00-140">Поэтому может потребоваться создать сжатые резервные копии с низким приоритетом в сеансе, для которого использование ЦП ограничивается [регулятором ресурсов](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="7cf00-140">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="7cf00-141">Дополнительные сведения см. ниже в подразделе [Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (Transact-SQL)](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7cf00-141">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="7cf00-142">**Не сжимать резервные копии**</span><span class="sxs-lookup"><span data-stu-id="7cf00-142">**Do not compress backup**</span></span>|<span data-ttu-id="7cf00-143">Щелкните для создания резервной копии без сжатия, независимо от уровня сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7cf00-143">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
### <a name="encryption"></a><span data-ttu-id="7cf00-144">Шифрование</span><span class="sxs-lookup"><span data-stu-id="7cf00-144">Encryption</span></span>  
 <span data-ttu-id="7cf00-145">Для создания шифрованной резервной копии установите флажок **Зашифровать файл резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="7cf00-145">To create an encrypted backup, check the **Encrypt backup** check box.</span></span> <span data-ttu-id="7cf00-146">Выберите алгоритм шифрования для шага шифрования и выберите сертификат или асимметричный ключ из списка существующих сертификатов или асимметричных ключей.</span><span class="sxs-lookup"><span data-stu-id="7cf00-146">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="7cf00-147">Доступны следующие алгоритмы шифрования:</span><span class="sxs-lookup"><span data-stu-id="7cf00-147">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="7cf00-148">AES 128</span><span class="sxs-lookup"><span data-stu-id="7cf00-148">AES 128</span></span>  
  
-   <span data-ttu-id="7cf00-149">AES 192</span><span class="sxs-lookup"><span data-stu-id="7cf00-149">AES 192</span></span>  
  
-   <span data-ttu-id="7cf00-150">AES 256</span><span class="sxs-lookup"><span data-stu-id="7cf00-150">AES 256</span></span>  
  
-   <span data-ttu-id="7cf00-151">Triple DES</span><span class="sxs-lookup"><span data-stu-id="7cf00-151">Triple DES</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7cf00-152">Параметр шифрования отключен, если вы решили присоединить резервную копию к существующему резервному набору данных.</span><span class="sxs-lookup"><span data-stu-id="7cf00-152">The encryption option is disabled if you selected to append to existing backup set.</span></span>  
>   
>  <span data-ttu-id="7cf00-153">Рекомендуется регулярно создавать резервные копии сертификата или ключей и сохранять их в местоположении, отличном от местоположения шифруемой резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7cf00-153">It is recommended practice to back up your certificate or keys and store them in a different location than the backup you encrypted.</span></span>  
>   
>  <span data-ttu-id="7cf00-154">Поддерживаются только ключи, относящиеся к расширенному управлению ключами.</span><span class="sxs-lookup"><span data-stu-id="7cf00-154">Only keys residing in the Extensible Key Management (EKM) are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf00-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="7cf00-155">See Also</span></span>  
 <span data-ttu-id="7cf00-156">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7cf00-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="7cf00-157">[Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7cf00-157">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="7cf00-158">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7cf00-158">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="7cf00-159">Создание резервной копии журнала транзакций при повреждении базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7cf00-159">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
