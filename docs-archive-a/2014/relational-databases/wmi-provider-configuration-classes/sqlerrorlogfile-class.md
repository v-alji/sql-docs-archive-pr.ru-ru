---
title: Класс SqlErrorLogFile | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
ms.assetid: 2b83ae4a-c0d4-414c-b6e5-a41ec7c13159
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d73f97ebddd7a1d18c73a2cbce7fe79dafc17a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729218"
---
# <a name="sqlerrorlogfile-class"></a><span data-ttu-id="390d7-102">SqlErrorLogFile, класс</span><span class="sxs-lookup"><span data-stu-id="390d7-102">SqlErrorLogFile Class</span></span>
  <span data-ttu-id="390d7-103">Предоставляет свойства для просмотра информации о файле журнала [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="390d7-103">Provides properties for viewing information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="390d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="390d7-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogFile  
{  
   uint32ArchiveNumber;  
   stringInstanceName;  
   datetimeLastModified;  
   uint32LogFileSize;  
   stringName;  
  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="390d7-105">Свойства</span><span class="sxs-lookup"><span data-stu-id="390d7-105">Properties</span></span>  
 <span data-ttu-id="390d7-106">Класс SQLErrorLogFile определяет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="390d7-106">The SQLErrorLogFile class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="390d7-107">арчивенумбер</span><span class="sxs-lookup"><span data-stu-id="390d7-107">ArchiveNumber</span></span>|<span data-ttu-id="390d7-108">Тип данных: `uint32`</span><span class="sxs-lookup"><span data-stu-id="390d7-108">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="390d7-109">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="390d7-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="390d7-110">Номер архива для файла журнала.</span><span class="sxs-lookup"><span data-stu-id="390d7-110">The archive number for the log file.</span></span>|  
|<span data-ttu-id="390d7-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="390d7-111">InstanceName</span></span>|<span data-ttu-id="390d7-112">Тип данных: `string`</span><span class="sxs-lookup"><span data-stu-id="390d7-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="390d7-113">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="390d7-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="390d7-114">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="390d7-114">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="390d7-115">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], на котором хранится файл журнала.</span><span class="sxs-lookup"><span data-stu-id="390d7-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="390d7-116">LastModified</span><span class="sxs-lookup"><span data-stu-id="390d7-116">LastModified</span></span>|<span data-ttu-id="390d7-117">Тип данных: `datetime`</span><span class="sxs-lookup"><span data-stu-id="390d7-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="390d7-118">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="390d7-118">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="390d7-119">Дата последнего изменения файла журнала.</span><span class="sxs-lookup"><span data-stu-id="390d7-119">The date that the log file was last modified.</span></span>|  
|<span data-ttu-id="390d7-120">LogFileSize</span><span class="sxs-lookup"><span data-stu-id="390d7-120">LogFileSize</span></span>|<span data-ttu-id="390d7-121">Тип данных: `uint32`</span><span class="sxs-lookup"><span data-stu-id="390d7-121">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="390d7-122">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="390d7-122">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="390d7-123">Размер файла журнала в байтах.</span><span class="sxs-lookup"><span data-stu-id="390d7-123">The log file size, in bytes.</span></span>|  
|<span data-ttu-id="390d7-124">Имя</span><span class="sxs-lookup"><span data-stu-id="390d7-124">Name</span></span>|<span data-ttu-id="390d7-125">Тип данных: `string`</span><span class="sxs-lookup"><span data-stu-id="390d7-125">Data type: `string`</span></span><br /><br /> <span data-ttu-id="390d7-126">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="390d7-126">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="390d7-127">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="390d7-127">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="390d7-128">Имя файла журнала.</span><span class="sxs-lookup"><span data-stu-id="390d7-128">The name of the log file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="390d7-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="390d7-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="390d7-130">MOF</span><span class="sxs-lookup"><span data-stu-id="390d7-130">MOF</span></span>|<span data-ttu-id="390d7-131">Sqlmgmprovider xpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="390d7-131">Sqlmgmprovider xpsp2up.mof</span></span>|  
|<span data-ttu-id="390d7-132">DLL</span><span class="sxs-lookup"><span data-stu-id="390d7-132">DLL</span></span>|<span data-ttu-id="390d7-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="390d7-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="390d7-134">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="390d7-134">Namespace</span></span>|<span data-ttu-id="390d7-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="390d7-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="390d7-136">Пример</span><span class="sxs-lookup"><span data-stu-id="390d7-136">Example</span></span>  
 <span data-ttu-id="390d7-137">В этом примере извлекаются данных обо всех файлах журналов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в указанном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="390d7-137">The following example retrieves information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="390d7-138">Чтобы выполнить пример, замените \<*Instance_Name*> именем экземпляра, например "instance1".</span><span class="sxs-lookup"><span data-stu-id="390d7-138">To run the example, replace \<*Instance_Name*> with the name of the instance, for example, 'Instance1'.</span></span>  
  
```  
on error resume next  
set strComputer = "."  
set objWMIService = GetObject("winmgmts:\\.\root\Microsoft\SqlServer\ComputerManagement10")  
set LogFiles = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogFile WHERE InstanceName = '<Instance_Name>'")  
  
For Each logFile in LogFiles  
  
WScript.Echo "Instance Name:  " & logFile.InstanceName & vbNewLine _  
    & "Log File Name:  " & logFile.Name & vbNewLine _  
    & "Archive Number: " & logFile.ArchiveNumber & vbNewLine _  
    & "Log File Size:  " & logFile.LogFileSize & " bytes" & vbNewLine _  
    & "Last Modified:  " & logFile.LastModified & vbNewLine _  
  
Next   
```  
  
## <a name="comments"></a><span data-ttu-id="390d7-139">Комментарии</span><span class="sxs-lookup"><span data-stu-id="390d7-139">Comments</span></span>  
 <span data-ttu-id="390d7-140">Если параметр *instanceName* не указан в инструкции WQL, запрос возвратит сведения для экземпляра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="390d7-140">When *InstanceName* is not provided in the WQL statement, the query will return information for the default instance.</span></span> <span data-ttu-id="390d7-141">Например, следующая инструкция WQL вернет информацию обо всех файлах журнала в текущем экземпляре (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="390d7-141">For example, the following WQL statement will return information about all log files from the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogFile"  
```  
  
## <a name="security"></a><span data-ttu-id="390d7-142">Безопасность</span><span class="sxs-lookup"><span data-stu-id="390d7-142">Security</span></span>  
 <span data-ttu-id="390d7-143">Для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файлу журнала через инструментарий WMI необходимо иметь следующие разрешения на локальном и на удаленном компьютерах:</span><span class="sxs-lookup"><span data-stu-id="390d7-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="390d7-144">Доступ на чтение к пространству имен WMI **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="390d7-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="390d7-145">По умолчанию доступ для чтения задается для всех с помощью разрешения «Включить учетную запись».</span><span class="sxs-lookup"><span data-stu-id="390d7-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="390d7-146">Сведения о том, как проверить разрешения WMI, см. в разделе "безопасность" раздела [Просмотр автономных файлов журнала](../logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="390d7-146">For information about how to verify WMI permissions, see the Security section of the topic [View Offline Log Files](../logs/view-offline-log-files.md).</span></span>  
  
-   <span data-ttu-id="390d7-147">Разрешение для чтения на папку, содержащую журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="390d7-147">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="390d7-148">По умолчанию журналы ошибок расположены по следующему пути (где \<*Drive> \* обозначает диск, на котором установлен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а \<*InstanceName*> — имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="390d7-148">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="390d7-149">\*\* \<Drive> : \PROGRAM Files\Microsoft SQL Server\MSSQL11\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="390d7-149">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL11** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="390d7-150">При соединении с использованием брандмауэра убедитесь, что в брандмауэре задано исключение для WMI на удаленных целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="390d7-150">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="390d7-151">Дополнительные сведения см. [в статье удаленное подключение к WMI, начиная с Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="390d7-151">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390d7-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="390d7-152">See Also</span></span>  
 <span data-ttu-id="390d7-153">[Класс SqlErrorLogEvent](sqlerrorlogevent-class.md) </span><span class="sxs-lookup"><span data-stu-id="390d7-153">[SqlErrorLogEvent Class](sqlerrorlogevent-class.md) </span></span>  
 [<span data-ttu-id="390d7-154">Просмотр автономных файлов журнала</span><span class="sxs-lookup"><span data-stu-id="390d7-154">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
