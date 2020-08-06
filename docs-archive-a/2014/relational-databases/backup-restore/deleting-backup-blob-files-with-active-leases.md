---
title: Удаление резервных файлов больших двоичных объектов с активной арендой | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 13a8f879-274f-4934-a722-b4677fc9a782
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02aea910589633a5c3ec79e283c757727b4d92cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658850"
---
# <a name="deleting-backup-blob-files-with-active-leases"></a><span data-ttu-id="d95df-102">Удаление резервных файлов больших двоичных объектов с активной арендой</span><span class="sxs-lookup"><span data-stu-id="d95df-102">Deleting Backup Blob Files with Active Leases</span></span>
  <span data-ttu-id="d95df-103">При резервном копировании или восстановлении из хранилища Azure SQL Server получает бесконечную аренду для блокировки монопольного доступа к большому двоичному объекту.</span><span class="sxs-lookup"><span data-stu-id="d95df-103">When backing up to or restoring from Azure storage, SQL Server acquires an infinite lease in order to lock exclusive access to the blob.</span></span> <span data-ttu-id="d95df-104">После успешного завершения процесса резервного копирования или восстановления аренда аннулируется.</span><span class="sxs-lookup"><span data-stu-id="d95df-104">When the backup or restore process is successfully completed, the lease is released.</span></span> <span data-ttu-id="d95df-105">Если резервное копирование или восстановление оканчивается неудачей, то в процессе резервного копирования предпринимается попытка очистить все недействительные большие двоичные объекты.</span><span class="sxs-lookup"><span data-stu-id="d95df-105">If a backup or restore fails, the backup process attempts to clean up any invalid blob.</span></span> <span data-ttu-id="d95df-106">Но если резервное копирование оканчивается неудачей из-за длительного или неустранимого сбоя связи с сетью, то, возможно, в процессе резервного копирования нельзя будет получить доступ к большому двоичному объекту и он останется потерянным.</span><span class="sxs-lookup"><span data-stu-id="d95df-106">However, if the backup fails due to prolonged or sustained network connectivity failure, the backup  process may not be able gain access to the blob and the blob may remain orphaned.</span></span> <span data-ttu-id="d95df-107">Это означает, что большой двоичный объект не может быть записан или удален до тех пор, пока аренда не освободится.</span><span class="sxs-lookup"><span data-stu-id="d95df-107">This means that the blob cannot be written to or deleted until the lease is released.</span></span> <span data-ttu-id="d95df-108">В этом разделе показано, как освободить и удалить зарезервированный большой двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="d95df-108">This topic describes how to release the lease and deleting the blob..</span></span>  
  
 <span data-ttu-id="d95df-109">Дополнительные сведения о типах аренды см. в этой [статье](https://go.microsoft.com/fwlink/?LinkId=275664).</span><span class="sxs-lookup"><span data-stu-id="d95df-109">For more information on the types of leases, read this [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span></span>  
  
 <span data-ttu-id="d95df-110">Если операция резервного копирования не удается, это может привести к появлению файла резервной копии, который является нерабочим.</span><span class="sxs-lookup"><span data-stu-id="d95df-110">If the backup operation fails, it can result in a backup file that is not valid.</span></span>  <span data-ttu-id="d95df-111">Также у большого двоичного объекта файла может появиться активная аренда, которая предотвращает его удаление и повторную запись.</span><span class="sxs-lookup"><span data-stu-id="d95df-111">The backup blob file might also have an active lease, preventing it from being deleted or overwritten.</span></span>  <span data-ttu-id="d95df-112">Чтобы удалить или повторно записать такие большие двоичные объекты, необходимо вначале прекратить аренду. Если происходят ошибки при резервном копировании, рекомендуется очистить аренды и удалить большие двоичные объекты.</span><span class="sxs-lookup"><span data-stu-id="d95df-112">In order to delete or overwrite such blobs, the lease should first be broken.If there are backup failures, we recommend that you clean up leases and delete blobs.</span></span> <span data-ttu-id="d95df-113">Также можно внести периодическую чистку в задачи управления хранилищем.</span><span class="sxs-lookup"><span data-stu-id="d95df-113">You can also choose cleanup periodically as part of storage management tasks.</span></span>  
  
 <span data-ttu-id="d95df-114">Если происходит ошибка восстановления, то последующие операции восстановления не блокируются, поэтому проблем с активной арендой не возникает.</span><span class="sxs-lookup"><span data-stu-id="d95df-114">If there is a restore failure, subsequent restores are not blocked, and therefore the active lease may not be an issue.</span></span> <span data-ttu-id="d95df-115">Прерывайте аренду только в том случае, если необходимо перезаписать или удалить большой двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="d95df-115">Breaking the lease is only necessary when you have to overwrite or delete the blob.</span></span>  
  
## <a name="managing-orphaned-blobs"></a><span data-ttu-id="d95df-116">Управление потерянными большими двоичными объектами</span><span class="sxs-lookup"><span data-stu-id="d95df-116">Managing Orphaned Blobs</span></span>  
 <span data-ttu-id="d95df-117">Следующие действия описывают процесс очистки после неудачной операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="d95df-117">The follow steps describe how to clean up after failed backup or restore activity.</span></span> <span data-ttu-id="d95df-118">Все действия могут быть выполнены с помощью скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d95df-118">All the steps can be done using PowerShell scripts.</span></span> <span data-ttu-id="d95df-119">Пример кода представлен в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="d95df-119">A code example is provided in the following section:</span></span>  
  
1.  <span data-ttu-id="d95df-120">**Определение больших двоичных объектов с арендой.** Если резервное копирование выполняется с помощью скрипта или процесса, вы можете фиксировать ошибки внутри такого скрипта или процесса и использовать эти данные для очистки больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="d95df-120">**Identifying blobs that have leases:** If you have a script or a process that runs the backup processes, you might be able to capture the failure within the script or process and use that to clean up the blobs.</span></span>   <span data-ttu-id="d95df-121">Можно также использовать свойства LeaseStats и LeastState, чтобы выделить большие двоичные объекты с арендой.</span><span class="sxs-lookup"><span data-stu-id="d95df-121">You can also use the LeaseStats and LeastState properties to identify the blobs that have leases on them.</span></span> <span data-ttu-id="d95df-122">После определения больших двоичных объектов рекомендуется просмотреть список, проверить работоспособность файла резервной копии перед удалением большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="d95df-122">Once you have identified the blobs, we recommend that you review the list, verify the validity of the backup file before deleting the blob.</span></span>  
  
2.  <span data-ttu-id="d95df-123">**Прерывание аренды.** Авторизованный запрос может прерывать аренду без предоставления идентификатора аренды.</span><span class="sxs-lookup"><span data-stu-id="d95df-123">**Breaking the lease:** An authorized request can break the lease without supplying a lease ID.</span></span> <span data-ttu-id="d95df-124">Дополнительные сведения см. в [этом разделе](https://go.microsoft.com/fwlink/?LinkID=275664) .</span><span class="sxs-lookup"><span data-stu-id="d95df-124">See [here](https://go.microsoft.com/fwlink/?LinkID=275664) for more information.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="d95df-125">SQL Server выдает идентификатор аренды для получения монопольного доступа во время операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="d95df-125">SQL Server issues a lease ID to establish exclusive access during the restore operation.</span></span> <span data-ttu-id="d95df-126">Идентификатор аренды при операции восстановления — BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span><span class="sxs-lookup"><span data-stu-id="d95df-126">The restore lease ID is BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span></span>  
  
3.  <span data-ttu-id="d95df-127">**Удаление большого двоичного объекта.** Чтобы удалить большой двоичный объект с активной арендой, сначала необходимо прервать аренду.</span><span class="sxs-lookup"><span data-stu-id="d95df-127">**Deleting the Blob:** To delete a blob that has an active lease, you must first break the lease.</span></span>  
  
###  <a name="powershell-script-example"></a><a name="Code_Example"></a><span data-ttu-id="d95df-128">Пример сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="d95df-128">PowerShell Script Example</span></span>  
 <span data-ttu-id="d95df-129">\*\* \* \* Важно \* ! \* \*\* если вы используете PowerShell 2,0, возможно, возникли проблемы при загрузке сборки Microsoft WindowsAzure.Storage.dll.</span><span class="sxs-lookup"><span data-stu-id="d95df-129">**\*\* Important \*\*** If you are running PowerShell 2.0, you may have problems loading the Microsoft WindowsAzure.Storage.dll assembly.</span></span> <span data-ttu-id="d95df-130">Рекомендуется обновить Powershell до версии 3.0, чтобы решить проблему.</span><span class="sxs-lookup"><span data-stu-id="d95df-130">We recommend that you upgrade to Powershell 3.0 to solve the issue.</span></span> <span data-ttu-id="d95df-131">Можно также использовать следующее решение для PowerShell 2.0:</span><span class="sxs-lookup"><span data-stu-id="d95df-131">You may also use the following workaround for PowerShell 2.0:</span></span>  
  
-   <span data-ttu-id="d95df-132">Создайте или измените файл powershell.exe.config для загрузки сборки .NET Framework 2.0 и .NET Framework 4.0 в среде выполнения с помощью следующего:</span><span class="sxs-lookup"><span data-stu-id="d95df-132">Create or modify the powershell.exe.config file to load .NET 2.0 and .NET 4.0 assemblies at runtime with the following:</span></span>  
  
    ```xml
    <?xml version="1.0"?>
    <configuration>
        <startup useLegacyV2RuntimeActivationPolicy="true">
            <supportedRuntime version="v4.0.30319"/>
            <supportedRuntime version="v2.0.50727"/>
        </startup>
    </configuration>
    ```  
  
 <span data-ttu-id="d95df-133">В следующем примере показано определение больших двоичных объектов с активной арендой и ее последующее прерывание.</span><span class="sxs-lookup"><span data-stu-id="d95df-133">The following example illustrates identifying blobs that have active leases and then breaking them.</span></span> <span data-ttu-id="d95df-134">В этом примере также показано, как отфильтровывать идентификаторы аренды.</span><span class="sxs-lookup"><span data-stu-id="d95df-134">The example also demonstrates how filter for release lease IDs.</span></span>  
  
 <span data-ttu-id="d95df-135">Советы для запуска этого скрипта</span><span class="sxs-lookup"><span data-stu-id="d95df-135">Tips on running this script</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d95df-136">Если резервное копирование в службу хранилища BLOB-объектов Azure выполняется одновременно с этим сценарием, то резервное копирование может завершиться ошибкой, так как этот скрипт прервет аренду, которую резервная копия пытается получить в то же время.</span><span class="sxs-lookup"><span data-stu-id="d95df-136">If a backup to Azure Blob storage service is running at the same time as this script, the backup can fail since this script will break the lease that the backup is trying to acquire at the same time.</span></span> <span data-ttu-id="d95df-137">Рекомендуется выполнять этот скрипт во время перерывов на профилактическое техобслуживание или в то время, когда не ожидается проведение какого-либо резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d95df-137">We recommend running this script during a maintenance windows or when no backups are expected to run.</span></span>  
  
1.  <span data-ttu-id="d95df-138">При выполнении этого скрипта вам будет предложено указать значения для учетной записи хранения, ключа хранилища, контейнера, пути к сборке службы хранилища Azure и параметров имени.</span><span class="sxs-lookup"><span data-stu-id="d95df-138">When you run this script, you will be prompted to provide values for the storage account, storage key, container, and the Azure storage assembly path and name parameters.</span></span> <span data-ttu-id="d95df-139">Путь к сборке хранилища — это установочная директория экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d95df-139">The path of the storage is assembly is the installation directory of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d95df-140">Имя файла для сборки хранилища — Microsoft.WindowsAzure.Storage.dll.</span><span class="sxs-lookup"><span data-stu-id="d95df-140">The file name for the storage assembly is Microsoft.WindowsAzure.Storage.dll.</span></span> <span data-ttu-id="d95df-141">Далее приводится пример запросов и введенных значений.</span><span class="sxs-lookup"><span data-stu-id="d95df-141">Following is an example of the prompts and values entered:</span></span>  
  
    ```  
    cmdlet  at command pipeline position 1  
    Supply values for the following parameters:  
    storageAccount: mycloudstorageaccount  
    storageKey: 0BopKY7eEha3gBnistYk+904nf  
    blobContainer: mycontainer   
    storageAssemblyPath: C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Microsoft.WindowsAzure.Storage.dll  
    ```  
  
2.  <span data-ttu-id="d95df-142">При отсутствии больших двоичных объектов с заблокированными арендами появится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="d95df-142">If there are no blobs that have locked leases you should see the following message:</span></span>  
  
     <span data-ttu-id="d95df-143">**Отсутствуют большие двоичные объекты с заблокированным статусом аренды**</span><span class="sxs-lookup"><span data-stu-id="d95df-143">**There are no blobs with locked lease status**</span></span>  
  
     <span data-ttu-id="d95df-144">При наличии больших двоичных объектов с заблокированными арендами появится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="d95df-144">If there are blobs with locked leases, you should see the following messages:</span></span>  
  
     <span data-ttu-id="d95df-145">**Прерывание аренды**</span><span class="sxs-lookup"><span data-stu-id="d95df-145">**Breaking Leases**</span></span>  
  
     <span data-ttu-id="d95df-146">**Аренда — это \<URL of the Blob> Аренда восстановления. это сообщение появляется только в том случае, если у вас есть большой двоичный объект с арендой восстановления, которая еще активна.**</span><span class="sxs-lookup"><span data-stu-id="d95df-146">**The lease on \<URL of the Blob> is a restore lease: You will see this message only if you have a blob with a restore lease that is still active.**</span></span>  
  
     <span data-ttu-id="d95df-147">**Аренда в \<URL of the Blob> не является арендой восстановления, в которую включена аренда \<URL of the Bob> .**</span><span class="sxs-lookup"><span data-stu-id="d95df-147">**The lease on \<URL of the Blob> is not a restore lease Breaking lease on \<URL of the Bob>.**</span></span>  
  
```powershell
param(  
       [Parameter(Mandatory=$true)]  
       [string]$storageAccount,  
       [Parameter(Mandatory=$true)]  
       [string]$storageKey,  
       [Parameter(Mandatory=$true)]  
       [string]$blobContainer,  
       [Parameter(Mandatory=$true)]  
       [string]$storageAssemblyPath  
)  
  
# Well known Restore Lease ID  
$restoreLeaseId = "BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2"  
  
# Load the storage assembly without locking the file for the duration of the PowerShell session  
$bytes = [System.IO.File]::ReadAllBytes($storageAssemblyPath)  
[System.Reflection.Assembly]::Load($bytes)  
  
$cred = New-Object 'Microsoft.WindowsAzure.Storage.Auth.StorageCredentials' $storageAccount, $storageKey  
$client = New-Object 'Microsoft.WindowsAzure.Storage.Blob.CloudBlobClient' "https://$storageAccount.blob.core.windows.net", $cred  
$container = $client.GetContainerReference($blobContainer)  
  
#list all the blobs  
$allBlobs = $container.ListBlobs()
  
$lockedBlobs = @()  
# filter blobs that are have Lease Status as "locked"  
foreach($blob in $allBlobs)  
{  
    $blobProperties = $blob.Properties
    if($blobProperties.LeaseStatus -eq "Locked")  
    {  
        $lockedBlobs += $blob  
    }  
}  
  
if ($lockedBlobs.Count -eq 0)  
{
    Write-Host " There are no blobs with locked lease status"  
}

if($lockedBlobs.Count -gt 0)  
{  
    Write-Host "Breaking leases"  
    foreach($blob in $lockedBlobs )
    {  
        try  
        {  
            $blob.AcquireLease($null, $restoreLeaseId, $null, $null, $null)  
            Write-Host "The lease on $($blob.Uri) is a restore lease"  
        }  
        catch [Microsoft.WindowsAzure.Storage.StorageException]  
        {  
            if($_.Exception.RequestInformation.HttpStatusCode -eq 409)  
            {  
                Write-Host "The lease on $($blob.Uri) is not a restore lease"  
            }  
        }  
  
        Write-Host "Breaking lease on $($blob.Uri)"  
        $blob.BreakLease($(New-TimeSpan), $null, $null, $null) | Out-Null  
    }  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="d95df-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="d95df-148">See Also</span></span>  
 <span data-ttu-id="d95df-149">[Резервное копирование SQL Server на URL-адрес — рекомендации и устранение неполадок](sql-server-backup-to-url-best-practices-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="d95df-149">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
