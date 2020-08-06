---
title: Резервное копирование нескольких баз данных в службу хранилища BLOB-объектов Azure с помощью PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: f7008339-e69d-4e20-9265-d649da670460
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95da5d0009f88943029e62960e7429b292242bbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664957"
---
# <a name="use-powershell-to-backup-multiple-databases-to-azure-blob-storage-service"></a><span data-ttu-id="c702b-102">Использование PowerShell для резервного копирования нескольких баз данных в службу хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="c702b-102">Use PowerShell to Backup Multiple Databases to Azure Blob Storage Service</span></span>
  <span data-ttu-id="c702b-103">В этом разделе приведены примеры скриптов, которые можно использовать для автоматизации резервного копирования в службу хранилища BLOB-объектов Azure с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c702b-103">This topic provides sample scripts that can be used to automate backups to Azure Blob storage service using PowerShell cmdlets.</span></span>  
  
## <a name="overview-of-powershell-cmdlets-for-backup-and-restore"></a><span data-ttu-id="c702b-104">Обзор командлетов PowerShell для резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="c702b-104">Overview of PowerShell cmdlets for Backup and Restore</span></span>  
 <span data-ttu-id="c702b-105">`Backup-SqlDatabase` и `Restore-SqlDatabase` — два основных командлета для операций резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="c702b-105">The `Backup-SqlDatabase` and `Restore-SqlDatabase` are the two main cmdlets available to do backup and restore operations.</span></span> <span data-ttu-id="c702b-106">Кроме того, есть и другие командлеты, которые могут потребоваться для автоматизации резервного копирования в хранилище BLOB-объектов Azure, такие как набор командлетов **SqlCredential**. Ниже приведен список командлетов PowerShell, доступных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] и используемых в операциях резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="c702b-106">In addition, there are other cmdlets that may be required to automate backups to Azure Blob storage like the set of **SqlCredential** cmdlets  Following is a list of PowerShell cmdlets available in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that are used in backup and restore operations:</span></span>  
  
 <span data-ttu-id="c702b-107">Backup-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="c702b-107">Backup-SqlDatabase</span></span>  
 <span data-ttu-id="c702b-108">Этот командлет используется для создания резервной копии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c702b-108">This cmdlet is used to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Backup.</span></span>  
  
 <span data-ttu-id="c702b-109">Restore-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="c702b-109">Restore-SqlDatabase</span></span>  
 <span data-ttu-id="c702b-110">Используется для восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="c702b-110">Used to restore a database.</span></span>  
  
 <span data-ttu-id="c702b-111">New-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="c702b-111">New-SqlCredential</span></span>  
 <span data-ttu-id="c702b-112">Этот командлет используется для создания учетных данных SQL, используемых для резервного копирования SQL Server в службу хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="c702b-112">This cmdlet is used to create a SQL Credential to use for SQL Server Backup to Azure Storage.</span></span> <span data-ttu-id="c702b-113">Дополнительные сведения об учетных данных и их использовании в SQL Server резервного копирования и восстановления см. в статье [SQL Server резервное копирование и восстановление с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="c702b-113">For more information on credentials and their use in SQL Server Backup and Restore, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="c702b-114">Get-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="c702b-114">Get-SqlCredential</span></span>  
 <span data-ttu-id="c702b-115">Этот командлет используется для получения объекта учетных данных и его свойств.</span><span class="sxs-lookup"><span data-stu-id="c702b-115">This cmdlet is used to retrieve the Credential object and its properties.</span></span>  
  
 <span data-ttu-id="c702b-116">Remove-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="c702b-116">Remove-SqlCredential</span></span>  
 <span data-ttu-id="c702b-117">Удаление объекта учетных данных SQL</span><span class="sxs-lookup"><span data-stu-id="c702b-117">Delete a SQL Credential object</span></span>  
  
 <span data-ttu-id="c702b-118">Set-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="c702b-118">Set-SqlCredential</span></span>  
 <span data-ttu-id="c702b-119">Этот командлет используется для изменения или задания свойств объекта учетных данных SQL.</span><span class="sxs-lookup"><span data-stu-id="c702b-119">This cmdlet is used to change or set the properties of the SQL Credential Object.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="c702b-120">Командлеты учетных данных используются в операциях резервного копирования и восстановления в сценариях работы с хранилищем BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="c702b-120">The Credential cmdlets are used in Backup and Restore to Azure Blob storage scenarios.</span></span>  
  
### <a name="powershell-for-multi-database-multi-instance-backup-operations"></a><span data-ttu-id="c702b-121">PowerShell для операций резервного копирования для нескольких баз данных и нескольких экземпляров</span><span class="sxs-lookup"><span data-stu-id="c702b-121">PowerShell for Multi-Database, Multi-Instance Backup Operations</span></span>  
 <span data-ttu-id="c702b-122">Следующие разделы содержат скрипты для различных операций, таких как создание учетных данных SQL в нескольких экземплярах SQL Server, резервное копирование всех пользовательских баз данных в экземпляре SQL Server и т. д.</span><span class="sxs-lookup"><span data-stu-id="c702b-122">The following sections include scripts for various operations like creating a SQL Credential on multiple instance of SQL Server, backing up all user databases in an instance of SQL Server, and such.</span></span> <span data-ttu-id="c702b-123">С помощью этих скриптов можно автоматизировать или запланировать операции резервного копирования в соответствии с требованиями среды.</span><span class="sxs-lookup"><span data-stu-id="c702b-123">You can use these scripts to automate or schedule backup operations according to the requirements of your environment.</span></span> <span data-ttu-id="c702b-124">Скрипты, описанные здесь, являются примерами, и их можно изменять или расширять для конкретной среды.</span><span class="sxs-lookup"><span data-stu-id="c702b-124">The scripts provided here are examples, and may be modified or extended for your environment.</span></span>  
  
 <span data-ttu-id="c702b-125">Ниже приведены замечания для примеров скриптов.</span><span class="sxs-lookup"><span data-stu-id="c702b-125">The following are considerations for the sample scripts:</span></span>  
  
1.  <span data-ttu-id="c702b-126">**Навигация по путям SQL Server PowerShell.** В Windows PowerShell предусмотрены командлеты для навигации по структуре пути, которая представляет иерархию объектов, поддерживаемых поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c702b-126">**Navigating SQL Server PowerShell paths:** Windows PowerShell implements cmdlets to navigate the path structure that represents the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="c702b-127">После перехода к нужному узлу можно использовать другие командлеты для выполнения основных операций с текущим объектом.</span><span class="sxs-lookup"><span data-stu-id="c702b-127">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span>  
  
2.  <span data-ttu-id="c702b-128">`Get-ChildItem`Командлет. сведения, возвращаемые, `Get-ChildItem` зависят от расположения в SQL Server PowerShell пути.</span><span class="sxs-lookup"><span data-stu-id="c702b-128">`Get-ChildItem` cmdlet: The information returned by the `Get-ChildItem` depends on the location in a SQL Server PowerShell path.</span></span> <span data-ttu-id="c702b-129">Например, если размещение находится на уровне компьютера, командлет возвращает все экземпляры ядра СУБД SQL Server, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c702b-129">For example, if the location is at the computer level, this cmdlet returns all the SQL Server database engine instances installed on the computer.</span></span> <span data-ttu-id="c702b-130">Другой пример: если расположение находится на уровне объектов, таких как базы данных, командлет возвращает список объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="c702b-130">As another example, if the location is at the object level such as databases, then this cmdlet returns a list of database objects.</span></span>  <span data-ttu-id="c702b-131">По умолчанию командлет `Get-ChildItem` не возвращает системные объекты.</span><span class="sxs-lookup"><span data-stu-id="c702b-131">By default the `Get-ChildItem` cmdlet does not return system objects.</span></span>  <span data-ttu-id="c702b-132">Системные объекты можно просмотреть, задав параметр -Force.</span><span class="sxs-lookup"><span data-stu-id="c702b-132">Using the -Force parameter you can see the system objects.</span></span>  
  
     <span data-ttu-id="c702b-133">Дополнительные сведения см. в статье [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span><span class="sxs-lookup"><span data-stu-id="c702b-133">For more information, see [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span></span>  
  
3.  <span data-ttu-id="c702b-134">Хотя каждый пример кода можно использовать отдельно, изменив значения переменных, создание учетной записи хранения Azure и учетных данных SQL является предварительным условием и требуется для всех операций резервного копирования и восстановления в службе хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="c702b-134">Although each code sample can be tried independently by changing the variable values, creating an Azure Storage Account and a SQL Credential are prerequisites and required for all backup and restore operations to Azure Blob storage service.</span></span>  
  
### <a name="create-a-sql-credential-on-all-the-instances-of-sql-server"></a><span data-ttu-id="c702b-135">Создание учетных данных SQL для всех экземпляров SQL Server</span><span class="sxs-lookup"><span data-stu-id="c702b-135">Create a SQL Credential on All the Instances of SQL Server</span></span>  
 <span data-ttu-id="c702b-136">Имеется два образца скрипта, и оба создают учетные данные SQL "mybackupToURL" на всех экземплярах SQL Server на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c702b-136">There are two sample scripts, and both create a SQL Credential "mybackupToURL" on all the instances of SQL Server on a computer.</span></span> <span data-ttu-id="c702b-137">В первом простом примере создаются учетные данные и не перехватываются исключения.</span><span class="sxs-lookup"><span data-stu-id="c702b-137">The first example creates is simple and creates the credential and does not trap exceptions.</span></span>  <span data-ttu-id="c702b-138">Например, если в одном из экземпляров на компьютере уже существуют учетные данные с тем же именем, работа скрипта завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="c702b-138">For example, if there was already an existing credential with the same name on one of the instances of the computer, the script would fail.</span></span> <span data-ttu-id="c702b-139">Второй пример перехватывает ошибки, что позволяет продолжить выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="c702b-139">The second example traps errors and allows the script to continue.</span></span>  
  
```powershell
import-module sqlps  
  
# create variables  
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#pipe the instances to new-sqlcredentail cmdlet to create SQL credential  
$instances | New-SqlCredential -Name $credentialName -Identity $storageAccount -Secret $secureString  
```  
  
```powershell
import-module sqlps  
  
# set the parameter values
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#loop through instances and create a SQL credential, output any errors  
ForEach ($instance In $instances)  
{  
    Try  
{  
     New-SqlCredential -Name $credentialName -path "SQLServer:\SQL\$($instance.name)" -Identity $storageAccount -Secret $secureString -ea Stop
}  
Catch [Exception]  
    {
            Write-Host "instance - $($instance.name): "$_.Exception.Message
    }
 }
```  
  
### <a name="remove-a-sql-credential-from-all-the-instances-of-sql-server"></a><span data-ttu-id="c702b-140">Удаление учетных данных SQL для всех экземпляров SQL Server</span><span class="sxs-lookup"><span data-stu-id="c702b-140">Remove A SQL Credential from All the Instances of SQL Server</span></span>  
 <span data-ttu-id="c702b-141">Этот скрипт может использоваться для удаления конкретных учетных данных из всех экземпляров SQL Server, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c702b-141">This script can be used to remove a specific credential from all the instances of SQL Server installed on the computer.</span></span> <span data-ttu-id="c702b-142">Если объект учетных данных не существует в определенном экземпляре, выводится сообщение об ошибке, а скрипт продолжает выполняться до тех пор, пока не будут проверены все экземпляры.</span><span class="sxs-lookup"><span data-stu-id="c702b-142">If the Credential object does not exist on a specific instance, an error message is displayed, and the script continues until all instances are checked.</span></span>  
  
```powershell
import-module sqlps  
  
cd SQLServer:\SQL\COMPUTERNAME  
$credentialName = "mybackuptoURL"  
  
$instances = Get-ChildItem  
  
ForEach ($instance In $instances)  
   {
    Try  
        {  
            $path = "SQLServer:\SQL\$($instance.name)\credentials\$credentialName"   
            Remove-SqlCredential -Path $path -ea stop   
         }  
         Catch [Exception]  
         {  
            Write-Host $_.Exception.Message
        }
    }  
```  
  
### <a name="full-database-backup-for-all-databases-including-system-databases"></a><span data-ttu-id="c702b-143">Полное резервное копирование для всех баз данных (ВКЛЮЧАЯ СИСТЕМНЫЕ)</span><span class="sxs-lookup"><span data-stu-id="c702b-143">Full Database Backup for all Databases (INCLUDING SYSTEM DATABASES)</span></span>  
 <span data-ttu-id="c702b-144">Следующий скрипт создает резервные копии всех баз данных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c702b-144">The following script creates backups of all databases on the computer.</span></span> <span data-ttu-id="c702b-145">Это касается и пользовательских баз данных, и системной базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c702b-145">This includes both user databases and **msdb** system database.</span></span> <span data-ttu-id="c702b-146">Скрипт фильтрует системные базы данных **tempdb** и **model** .</span><span class="sxs-lookup"><span data-stu-id="c702b-146">The script filters out **tempdb** and **model** system databases.</span></span>  
  
```powershell
import-module sqlps  
# set the parameter values  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the  databases -filter out tempdb and model databases  
  
 ForEach ($instance In $instances)  
 {  
   $path = "sqlserver:\sql\$($instance.name)\databases"  
   $alldatabases = Get-ChildItem -Force -path $path | Where-Object {$_.name -ne "tempdb" -and $_.name -ne "model"}   
   $alldatabases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On -script   
 }
```  
  
### <a name="full-database-backup-for-all-user-databases"></a><span data-ttu-id="c702b-147">Полное резервное копирование для ВСЕХ пользовательских баз данных</span><span class="sxs-lookup"><span data-stu-id="c702b-147">Full Database Backup for ALL User Databases</span></span>  
 <span data-ttu-id="c702b-148">Следующий скрипт можно использовать для резервного копирования всех пользовательских баз данных во всех экземплярах SQL Server на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c702b-148">The following script can be used to back up all the user databases on all the instances of SQL Server on the computer.</span></span>  
  
```powershell
import-module sqlps
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the user databases  
 ForEach ($instance In $instances)  
 {  
    $databases = dir "sqlserver:\sql\$($instance.name)\databases"  
    $databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On
 }  
```  
  
### <a name="full-database-backup-for-master-and-msdb-system-databases-on-all-the-instances-of-sql-server"></a><span data-ttu-id="c702b-149">Полное резервное копирование баз данных MASTER и MSDB (СИСТЕМНЫХ БАЗ ДАННЫХ) для всех экземпляров SQL Server</span><span class="sxs-lookup"><span data-stu-id="c702b-149">Full Database Backup for MASTER and MSDB (SYSTEM DATABASES) On All the Instances of SQL Server</span></span>  
 <span data-ttu-id="c702b-150">Следующий скрипт можно использовать для резервного копирования баз данных **master** и **msdb** во всех экземплярах SQL Server, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c702b-150">The following script can be used to back up **master** and **msdb** databases on all the instances of SQL Server installed on the computer.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackupToUrl"  
$sysDbs = "master", "msdb"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
$instances = Get-ChildItem
ForEach ($instance In $instances)  
 {  
      ForEach ($s In $sysdbs)  
     {  
        Backup-SqlDatabase -Database $s -path "sqlserver:\sql\$($instance.name)" -BackupContainer  $backupUrlContainer -SqlCredential $credentialName -Compression On   
}
 } 
```  
  
### <a name="full-database-backup-for-all-user-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="c702b-151">Полное резервное копирование всех пользовательских баз данных для одного экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="c702b-151">Full Database Backup for All User Databases on an Instance of SQL Server</span></span>  
 <span data-ttu-id="c702b-152">Следующий скрипт используется для резервного копирования только пользовательских баз данных, доступных на именованном экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c702b-152">The following script is used to back up only the user databases available on a named instance of SQL Server.</span></span> <span data-ttu-id="c702b-153">Тот же скрипт можно использовать для экземпляра по умолчанию на компьютере, изменив значение параметра $srvPath.</span><span class="sxs-lookup"><span data-stu-id="c702b-153">The same script can be used for the default instance on the computer by changing the $srvPath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME"  # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
  
#retrieves the database objects for a specific instance  
$databases = dir $srvPath\databases  
  
#backup all the user databases  
$databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
```  
  
### <a name="full-database-backup-for-only-system-databases-master-and-msdb-on-an-instance-of-sql-server"></a><span data-ttu-id="c702b-154">Полное резервное копирование только системных баз данных (MASTER И MSDB) для одного экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="c702b-154">Full Database Backup for Only System Databases (MASTER AND MSDB) On an Instance of SQL Server</span></span>  
 <span data-ttu-id="c702b-155">Полный скрипт можно использовать для резервного копирования баз данных **master** и **msdb** на именованном экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c702b-155">The full script can be used to back up the **master** and the **msdb** databases on a named instance of SQL Server.</span></span> <span data-ttu-id="c702b-156">Тот же скрипт можно использовать для экземпляра по умолчанию на компьютере, изменив значение параметра $srvPath.</span><span class="sxs-lookup"><span data-stu-id="c702b-156">The same script can be used for the default instance on the computer by changing the $srvpath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME" # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#navigate to instance level  
cd $srvPath  
  
$sysDbs = "master", "msdb"  
ForEach ($s In $sysDbs)
{  
Backup-SqlDatabase -Database $s -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="c702b-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="c702b-157">See Also</span></span>
 <span data-ttu-id="c702b-158">[SQL Server резервного копирования и восстановления с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server резервного копирования в URL рекомендации и устранение неполадок](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="c702b-158">[SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
