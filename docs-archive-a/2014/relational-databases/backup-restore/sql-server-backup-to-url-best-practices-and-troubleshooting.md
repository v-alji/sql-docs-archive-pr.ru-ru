---
title: Резервное копирование в SQL Server по URL-адресу — рекомендации и устранение неполадок | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665391"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a><span data-ttu-id="a14a1-102">Резервное копирование SQL Server на URL-адрес — рекомендации и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a14a1-102">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>
  <span data-ttu-id="a14a1-103">В этом разделе рассматриваются рекомендации и советы по устранению неполадок с SQL Server при создании резервных копий и восстановлении с помощью службы BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="a14a1-103">This topic includes best practices and troubleshooting tips for SQL Server backup and restores to the Azure Blob service.</span></span>  
  
 <span data-ttu-id="a14a1-104">Дополнительную сведения об использовании службы хранилища BLOB-объектов Azure для операций резервного копирования или восстановления SQL Server см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="a14a1-104">For more information about using Azure Blob storage service for SQL Server backup or restore operations, see:</span></span>  
  
-   [<span data-ttu-id="a14a1-105">Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="a14a1-105">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [<span data-ttu-id="a14a1-106">Руководство. Резервное копирование и восстановление SQL Server с помощью службы хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="a14a1-106">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a><span data-ttu-id="a14a1-107">Управление резервными копиями</span><span class="sxs-lookup"><span data-stu-id="a14a1-107">Managing Backups</span></span>  
 <span data-ttu-id="a14a1-108">В следующем списке перечислены общие рекомендации по управлению резервным копированием.</span><span class="sxs-lookup"><span data-stu-id="a14a1-108">The following list includes general recommendations to manage backups:</span></span>  
  
-   <span data-ttu-id="a14a1-109">Рекомендуется присваивать каждому файлу уникальное имя, чтобы предотвратить случайное перезаписывание больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="a14a1-109">Unique file name for every backup is recommended to prevent accidentally overwriting the blobs.</span></span>  
  
-   <span data-ttu-id="a14a1-110">При создании контейнера рекомендуется установить уровень доступа **private**, чтобы большие двоичные объекты в контейнере могли читать или записывать только те пользователи или учетные записи, которые предоставили необходимую информацию для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a14a1-110">When creating a container, it is recommended that you set the access level to **private**, so only users or accounts that can provide the required authentication information can read or write the blobs in the container.</span></span>  
  
-   <span data-ttu-id="a14a1-111">Для SQL Server баз данных на экземпляре SQL Server, работающем на виртуальной машине Azure, используйте учетную запись хранения в том же регионе, что и виртуальная машина, чтобы избежать затрат на передачу данных между регионами.</span><span class="sxs-lookup"><span data-stu-id="a14a1-111">For SQL Server databases on an instance of SQL Server running in an Azure Virtual Machine, use a storage account in the same region as the virtual machine to avoid data transfer costs between regions.</span></span> <span data-ttu-id="a14a1-112">Использование одного региона также обеспечивает оптимальную производительность операций резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="a14a1-112">Using the same region also ensures optimal performance for backup and restore operations.</span></span>  
  
-   <span data-ttu-id="a14a1-113">Сбой во время резервного копирования может привести к созданию неработоспособного файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="a14a1-113">Failed backup activity can result in an invalid backup file.</span></span> <span data-ttu-id="a14a1-114">Рекомендуется периодически проводить поиск неудачных резервных копий и удалять файлы больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="a14a1-114">We recommend periodic identification of failed backups and deleting the blob files.</span></span> <span data-ttu-id="a14a1-115">Дополнительные сведения см. в разделе [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="a14a1-115">For more information, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
-   <span data-ttu-id="a14a1-116">Использование параметра `WITH COMPRESSION` во время резервного копирования может уменьшить стоимость хранения и транзакционные издержки хранения.</span><span class="sxs-lookup"><span data-stu-id="a14a1-116">Using the `WITH COMPRESSION` option during backup can minimize your storage costs and storage transaction costs.</span></span> <span data-ttu-id="a14a1-117">Также может сократиться время, необходимое для выполнения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a14a1-117">It can also decrease the time taken to complete the backup process.</span></span>  
  
## <a name="handling-large-files"></a><span data-ttu-id="a14a1-118">Обработка больших файлов</span><span class="sxs-lookup"><span data-stu-id="a14a1-118">Handling Large Files</span></span>  
  
-   <span data-ttu-id="a14a1-119">Операция резервного копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется в несколько потоков, чтобы оптимизировать передачу данных к службам хранилищ BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="a14a1-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup operation uses multiple threads to optimize data transfer to Azure Blob storage services.</span></span>  <span data-ttu-id="a14a1-120">Однако производительность зависит от различных факторов, в том числе от пропускной способности ISV и размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="a14a1-120">However the performance depends on various factors, such as ISV bandwidth and size of the database.</span></span> <span data-ttu-id="a14a1-121">Если планируется создавать резервные копии больших баз данных или файловых групп в локальной базе данных SQL Server, вначале рекомендуется проверить пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="a14a1-121">If you plan to back up large databases or filegroups from an on-premise SQL Server database, it is recommended that you do some throughput testing first.</span></span> <span data-ttu-id="a14a1-122">[Соглашение об уровне обслуживания службы хранилища Azure](https://go.microsoft.com/fwlink/?LinkId=271619) имеет максимальную продолжительность обработки больших двоичных объектов, которые можно принять во внимание.</span><span class="sxs-lookup"><span data-stu-id="a14a1-122">[Azure storage SLA's](https://go.microsoft.com/fwlink/?LinkId=271619) have maximum processing times for blobs that you can take into consideration.</span></span>  
  
-   <span data-ttu-id="a14a1-123">При создании резервных копий больших файлов очень важно использовать параметр `WITH COMPRESSION` в соответствии с рекомендациями, приведенными в разделе **Управление резервным копированием**.</span><span class="sxs-lookup"><span data-stu-id="a14a1-123">Using the `WITH COMPRESSION` option as recommended in the **Managing Backup** section, it is very important when backing up large files.</span></span>  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a><span data-ttu-id="a14a1-124">Устранение неполадок при резервном копирование или восстановлении по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="a14a1-124">Troubleshooting Backup To or Restore from URL</span></span>  
 <span data-ttu-id="a14a1-125">Ниже приведено несколько простых способов устранения неполадок при создании резервной копии или восстановлении из службы хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="a14a1-125">Following are some quick ways to troubleshoot errors when backing up to or restoring from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="a14a1-126">Чтобы избежать ошибок из-за неподдерживаемых параметров или ограничений, ознакомьтесь со списком ограничений и поддержкой команд резервного копирования и восстановления в статье [SQL Server резервное копирование и восстановление с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="a14a1-126">To avoid errors due to unsupported options or limitations, review the list of limitations, and support for BACKUP and RESTORE commands information in the [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) article.</span></span>  
  
 <span data-ttu-id="a14a1-127">**Ошибки проверки подлинности:**</span><span class="sxs-lookup"><span data-stu-id="a14a1-127">**Authentication Errors:**</span></span>  
  
-   <span data-ttu-id="a14a1-128">УЧЕТные данные — это новый параметр, который требуется для резервного копирования или восстановления из службы хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="a14a1-128">WITH CREDENTIAL is a new option and required to back up to or restore from the Azure Blob storage service.</span></span> <span data-ttu-id="a14a1-129">Ниже приводятся возможные ошибки, связанные с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="a14a1-129">Failures related to credential could be the following:</span></span>  
  
     <span data-ttu-id="a14a1-130">Учетные данные, заданные в команде `BACKUP` или `RESTORE`, не существуют.</span><span class="sxs-lookup"><span data-stu-id="a14a1-130">The credential specified in the `BACKUP` or `RESTORE` command does not exist.</span></span> <span data-ttu-id="a14a1-131">Чтобы избежать этой проблемы, можно включить инструкцию T-SQL для создания учетных данных, если она отсутствует в инструкции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a14a1-131">To avoid this issue, you can include T-SQL statements to create the credential if one does not exist in the backup statement.</span></span> <span data-ttu-id="a14a1-132">Ниже приводится пример, который можно использовать.</span><span class="sxs-lookup"><span data-stu-id="a14a1-132">The following is an example you can use:</span></span>  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   <span data-ttu-id="a14a1-133">Учетные данные существуют, но учетная запись, которая используется для запуска команды резервного копирования, не имеет разрешения доступа к учетным данным.</span><span class="sxs-lookup"><span data-stu-id="a14a1-133">The credential exists but the login account that is used to run the backup command does not have permissions to access the credentials.</span></span> <span data-ttu-id="a14a1-134">Используйте учетную запись для входа в роль **db_backupoperator** с разрешением **Изменение любых учетных данных** .</span><span class="sxs-lookup"><span data-stu-id="a14a1-134">Use a login account in the **db_backupoperator** role with **Alter any credential** permissions.</span></span>  
  
-   <span data-ttu-id="a14a1-135">Проверьте имя учетной записи хранилища и значение ключа.</span><span class="sxs-lookup"><span data-stu-id="a14a1-135">Verify the storage account name and key values.</span></span> <span data-ttu-id="a14a1-136">Информация, которая хранится в учетных данных, должна соответствовать значениям свойств учетной записи хранения Azure, используемым в операциях резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="a14a1-136">The information stored in the credential must match the property values of the Azure storage account you are using in the backup and restore operations.</span></span>  
  
 <span data-ttu-id="a14a1-137">**Ошибки и сбои резервного копирования:**</span><span class="sxs-lookup"><span data-stu-id="a14a1-137">**Backup Errors/Failures:**</span></span>  
  
-   <span data-ttu-id="a14a1-138">Параллельное выполнение резервного копирования в один большой двоичный объект вызывает сбой одной из резервных копий с ошибкой **Ошибка инициализации** .</span><span class="sxs-lookup"><span data-stu-id="a14a1-138">Parallel backups to the same blob cause one of the backups to fail with an **Initialization failed** error.</span></span>  
  
-   <span data-ttu-id="a14a1-139">Используйте следующие журналы об ошибке, чтобы помочь при устранении неполадок в резервных ошибках:</span><span class="sxs-lookup"><span data-stu-id="a14a1-139">Use the following error logs to help with troubleshooting backup errors:</span></span>  
  
    -   <span data-ttu-id="a14a1-140">Установите флаг трассировки 3051, чтобы включить ведение записей в конкретном журнале ошибок в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a14a1-140">Set trace flag 3051 to turn on logging to a specific error log with the following format in:</span></span>  
  
         <span data-ttu-id="a14a1-141">BackupToUrl- \<instname> - \<dbname> -Action- \<PID> . log \<action> , где является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="a14a1-141">BackupToUrl-\<instname>-\<dbname>-action-\<PID>.log Where \<action> is one of:</span></span>  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   <span data-ttu-id="a14a1-142">Можно также найти сведения, просмотрев журнал событий Windows в разделе Журналы приложений с именем "Sqlbackuptourl»".</span><span class="sxs-lookup"><span data-stu-id="a14a1-142">You can also find information by reviewing the Windows Event Log - Under Application logs with the name 'SQLBackupToUrl'.</span></span>  
  
-   <span data-ttu-id="a14a1-143">При восстановлении из сжатой резервной копии может появиться следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="a14a1-143">When restoring from a compressed backup, you might see the following error:</span></span>  
  
    -   <span data-ttu-id="a14a1-144">**Произошла SqlException 3284. Серьезность: 16 состояние: 5**</span><span class="sxs-lookup"><span data-stu-id="a14a1-144">**SqlException 3284 occurred. Severity: 16 State: 5**</span></span>  
        <span data-ttu-id="a14a1-145">**Сообщение метка файла на устройстве " https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak " не согласовано. Повторите инструкцию Reissue с тем же размером блока, который использовался для создания резервного набора данных: "65536" похоже на возможное значение.**</span><span class="sxs-lookup"><span data-stu-id="a14a1-145">**Message Filemark on device 'https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak' is not aligned. Reissue the Restore statement with the same block size used to create the backupset: '65536' looks like a possible value.**</span></span>  
  
         <span data-ttu-id="a14a1-146">Чтобы устранить эту ошибку, перезапустите инструкцию `BACKUP` с помощью заметки `BLOCKSIZE = 65536`.</span><span class="sxs-lookup"><span data-stu-id="a14a1-146">To solve this error, reissue the `BACKUP` statement with `BLOCKSIZE = 65536` specified.</span></span>  
  
-   <span data-ttu-id="a14a1-147">Ошибка во время резервного копирования из-за больших двоичных объектов с активной арендой: сбой операции резервного копирования может привести к созданию больших двоичных объектов с активными арендами.</span><span class="sxs-lookup"><span data-stu-id="a14a1-147">Error during backup due to blobs that have active lease on them: Failed backup activity can result in blobs with active leases.</span></span>  
  
     <span data-ttu-id="a14a1-148">Если эта инструкция резервного копирования повторяется, то операция резервного копирования может завершиться со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="a14a1-148">If a backup statement is reattempted, backup operation might fail with an error similar to the following:</span></span>  
  
     <span data-ttu-id="a14a1-149">**Резервное копирование на URL-адрес получило исключение из удаленной конечной точки. Сообщение об исключении: удаленный сервер возвратил ошибку: (412) в настоящее время существует аренда для большого двоичного объекта, однако для запроса не указан идентификатор аренды**.</span><span class="sxs-lookup"><span data-stu-id="a14a1-149">**Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (412) There is currently a lease on the blob and no lease ID was specified in the request**.</span></span>  
  
     <span data-ttu-id="a14a1-150">Если инструкция восстановления выполнялись в резервном файле большого двоичного объекта с активной арендой, операция резервного копирования может завершиться со следующей ошибкой:</span><span class="sxs-lookup"><span data-stu-id="a14a1-150">If a restore statement is attempted on a backup blob file that has an active lease, the restore operation fails with an error similar to the following:</span></span>  
  
     <span data-ttu-id="a14a1-151">**Сообщение об исключении: удаленный сервер вернул ошибку: (409) конфликт…**</span><span class="sxs-lookup"><span data-stu-id="a14a1-151">**Exception Message: The remote server returned an error: (409) Conflict..**</span></span>  
  
     <span data-ttu-id="a14a1-152">Если возникает такая ошибка, файлы больших двоичных объектов следует удалить.</span><span class="sxs-lookup"><span data-stu-id="a14a1-152">When such error occurs, the blob files need to be deleted.</span></span> <span data-ttu-id="a14a1-153">Дополнительные сведения об этом сценарии и устранении этой проблемы см. в разделе [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md).</span><span class="sxs-lookup"><span data-stu-id="a14a1-153">For more information on this scenario and how to correct this problem, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
## <a name="proxy-errors"></a><span data-ttu-id="a14a1-154">Ошибки прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a14a1-154">Proxy Errors</span></span>  
 <span data-ttu-id="a14a1-155">При использовании прокси-серверов для доступа к Интернету возможны следующие проблемы.</span><span class="sxs-lookup"><span data-stu-id="a14a1-155">If you are using Proxy Servers to access the internet, you may see the following issues:</span></span>  
  
 <span data-ttu-id="a14a1-156">**Регулирование соединений прокси-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a14a1-156">**Connection throttling by Proxy Servers:**</span></span>  
  
 <span data-ttu-id="a14a1-157">Прокси-серверы могут иметь параметры, ограничивающие количество соединений в минуту.</span><span class="sxs-lookup"><span data-stu-id="a14a1-157">Proxy Servers can have settings that limit the number of connections per minute.</span></span> <span data-ttu-id="a14a1-158">Процесс резервного копирования на URL-адрес является многопоточным, в связи с чем заданное ограничение может быть превышено.</span><span class="sxs-lookup"><span data-stu-id="a14a1-158">The Backup to URL process is a multi-threaded process and hence can go over this limit.</span></span> <span data-ttu-id="a14a1-159">В этом случае прокси-сервер разрывает соединение.</span><span class="sxs-lookup"><span data-stu-id="a14a1-159">If this happens, the proxy server kills the connection.</span></span> <span data-ttu-id="a14a1-160">Чтобы устранить эту проблему, измените параметры прокси-сервера таким образом, чтобы SQL Server его не использовал.</span><span class="sxs-lookup"><span data-stu-id="a14a1-160">To resolve this issue, change the proxy settings so SQL Server is not using the proxy.</span></span>   <span data-ttu-id="a14a1-161">Далее приведено несколько примеров типов или сообщений об ошибках, которые можно встретить в журнале ошибок.</span><span class="sxs-lookup"><span data-stu-id="a14a1-161">Following are some examples of the types or error messages you may see in the error log:</span></span>  
  
-   <span data-ttu-id="a14a1-162">Ошибка записи в " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ": резервное копирование на URL-адрес получило исключение от удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a14a1-162">Write on "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak" failed: Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="a14a1-163">Сообщение об исключении: не удалось прочитать данные из транспортного соединения. Соединение было закрыто.</span><span class="sxs-lookup"><span data-stu-id="a14a1-163">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
-   <span data-ttu-id="a14a1-164">В файле "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" произошла неустранимая ошибка ввода-вывода "Не удалось получить ошибку из удаленной конечной точки".</span><span class="sxs-lookup"><span data-stu-id="a14a1-164">A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Error could not be gathered from Remote Endpoint.</span></span>  
  
     <span data-ttu-id="a14a1-165">Сообщение 3013, уровень 16, состояние 1, строка 2</span><span class="sxs-lookup"><span data-stu-id="a14a1-165">Msg 3013, Level 16, State 1, Line 2</span></span>  
  
     <span data-ttu-id="a14a1-166">Процесс BACKUP DATABASE завершается аварийно.</span><span class="sxs-lookup"><span data-stu-id="a14a1-166">BACKUP DATABASE is terminating abnormally.</span></span>  
  
-   <span data-ttu-id="a14a1-167">Баккупиорекуест:: Репортиоеррор: Ошибка записи на устройстве резервного копирования " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak ".</span><span class="sxs-lookup"><span data-stu-id="a14a1-167">BackupIoRequest::ReportIoError: write failure on backup device 'http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak'.</span></span> <span data-ttu-id="a14a1-168">Ошибка операционной системы. Процесс резервного копирования на URL-адрес получил исключение от удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a14a1-168">Operating system error Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="a14a1-169">Сообщение об исключении: не удалось прочитать данные из транспортного соединения. Соединение было закрыто.</span><span class="sxs-lookup"><span data-stu-id="a14a1-169">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
 <span data-ttu-id="a14a1-170">Если включить подробный уровень ведения журнала с помощью флага трассировки 3051, то в журналы также может быть занесено следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="a14a1-170">If you turn on the verbose logging using the trace flag 3051 you may also see the following message in the logs:</span></span>  
  
 <span data-ttu-id="a14a1-171">Код состояния HTTP 502, ошибка прокси-сервера сообщения о состоянии HTTP (количество HTTP-запросов в минуту превышает установленный предел.</span><span class="sxs-lookup"><span data-stu-id="a14a1-171">HTTP status code 502, HTTP Status Message Proxy Error ( The number of HTTP requests per minute exceeded the configured limit.</span></span> <span data-ttu-id="a14a1-172">Обратитесь к администратору сервера ISA.</span><span class="sxs-lookup"><span data-stu-id="a14a1-172">Contact your ISA Server administrator.</span></span>  <span data-ttu-id="a14a1-173">)</span><span class="sxs-lookup"><span data-stu-id="a14a1-173">)</span></span>  
  
 <span data-ttu-id="a14a1-174">**Параметры прокси-сервера по умолчанию не используются.**</span><span class="sxs-lookup"><span data-stu-id="a14a1-174">**Default Proxy Settings not picked up:**</span></span>  
  
 <span data-ttu-id="a14a1-175">Иногда параметры по умолчанию не вызывают ошибки проверки подлинности прокси-сервера, как показано ниже:*произошла неустранимая ошибка ввода-вывода в файле " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: " резервная копия на URL-адрес получил исключение от удаленной конечной точки. Сообщение об исключении: удаленный сервер вернул ошибку: (407)* **требуется проверка подлинности прокси-сервера**.</span><span class="sxs-lookup"><span data-stu-id="a14a1-175">Sometimes the default settings are not picked up causing proxy authentication errors such as the one shown below:*A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (407)* **Proxy Authentication Required**.</span></span>  
  
 <span data-ttu-id="a14a1-176">Чтобы устранить эту проблему, создайте файл конфигурации, позволяющий процессу резервного копирования по URL-адресу использовать параметры прокси-сервера по умолчанию. Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a14a1-176">To resolve this issue, create a configuration file that allows the Backup to URL process to use the default proxy settings using the following steps:</span></span>  
  
1.  <span data-ttu-id="a14a1-177">Создайте файл конфигурации BackuptoURL.exe.config со следующим XML-кодом:</span><span class="sxs-lookup"><span data-stu-id="a14a1-177">Create a configuration file named BackuptoURL.exe.config  with the following xml:</span></span>  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  <span data-ttu-id="a14a1-178">Поместите файл конфигурации в папку Binn на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a14a1-178">Place the configuration file in the Binn folder of the SQL Server Instance.</span></span> <span data-ttu-id="a14a1-179">Например, если мой SQL Server установлен на диске C компьютера, разместите файл конфигурации здесь: *C:\Program FILES\MICROSOFT SQL Server\MSSQL12. \<InstanceName> \MSSQL\Binn*.</span><span class="sxs-lookup"><span data-stu-id="a14a1-179">For example, if my SQL Server is installed on the C drive of the machine, place the configuration file here: *C:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Binn*.</span></span>  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a><span data-ttu-id="a14a1-180">Устранение неполадок с управляемым резервным копированием SQL Server в Azure</span><span class="sxs-lookup"><span data-stu-id="a14a1-180">Troubleshooting SQL Server Managed Backup to Azure</span></span>  
 <span data-ttu-id="a14a1-181">Так как служба управляемого резервного копирования SQL Server использует операцию копирования на URL-адрес, советы по устранению проблемы, описанные в предыдущих подразделах, относятся к базам данных и экземплярам, использующим данную службу.</span><span class="sxs-lookup"><span data-stu-id="a14a1-181">Since SQL Server Managed Backup is built on top of Backup to URL, the troubleshooting tips described in the earlier sections apply to databases or instances using SQL Server Managed Backup.</span></span>  <span data-ttu-id="a14a1-182">Сведения об устранении неполадок SQL Server управляемой архивации в Azure подробно описаны в [статье Устранение неполадок SQL Server управляемой архивации в Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="a14a1-182">Information about troubleshooting SQL Server Managed Backup to Azure is described in detail in [Troubleshooting SQL Server Managed  Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14a1-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="a14a1-183">See Also</span></span>  
 [<span data-ttu-id="a14a1-184">Восстановление из резервных копий, хранящихся в Azure</span><span class="sxs-lookup"><span data-stu-id="a14a1-184">Restoring From Backups Stored in Azure</span></span>](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  
