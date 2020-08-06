---
title: Класс SqlErrorLogEvent | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 358b6906e422be2984f2ebdbde636ad0b8376993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658674"
---
# <a name="sqlerrorlogevent-class"></a><span data-ttu-id="42f3a-102">SqlErrorLogEvent, класс</span><span class="sxs-lookup"><span data-stu-id="42f3a-102">SqlErrorLogEvent Class</span></span>
  <span data-ttu-id="42f3a-103">Предоставляет свойства для просмотра события в указанном файле журнала [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42f3a-103">Provides properties for viewing events in a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42f3a-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="42f3a-105">Свойства</span><span class="sxs-lookup"><span data-stu-id="42f3a-105">Properties</span></span>  
 <span data-ttu-id="42f3a-106">Класс SQLErrorLogEvent определяет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="42f3a-106">The SQLErrorLogEvent class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42f3a-107">FileName</span><span class="sxs-lookup"><span data-stu-id="42f3a-107">FileName</span></span>|<span data-ttu-id="42f3a-108">Тип данных: `string`</span><span class="sxs-lookup"><span data-stu-id="42f3a-108">Data type: `string`</span></span><br /><br /> <span data-ttu-id="42f3a-109">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="42f3a-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="42f3a-110">Имя файла журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="42f3a-110">The name of the error log file.</span></span>|  
|<span data-ttu-id="42f3a-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="42f3a-111">InstanceName</span></span>|<span data-ttu-id="42f3a-112">Тип данных: `string`</span><span class="sxs-lookup"><span data-stu-id="42f3a-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="42f3a-113">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="42f3a-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="42f3a-114">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="42f3a-114">Qualifiers: Key</span></span><br /><br /> <span data-ttu-id="42f3a-115">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], на котором хранится файл журнала.</span><span class="sxs-lookup"><span data-stu-id="42f3a-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="42f3a-116">логдате</span><span class="sxs-lookup"><span data-stu-id="42f3a-116">LogDate</span></span>|<span data-ttu-id="42f3a-117">Тип данных: `datetime`</span><span class="sxs-lookup"><span data-stu-id="42f3a-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="42f3a-118">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="42f3a-118">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="42f3a-119">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="42f3a-119">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="42f3a-120">Дата и время записи события в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="42f3a-120">The date and time that the event was recorded in the log file.</span></span>|  
|<span data-ttu-id="42f3a-121">Сообщение</span><span class="sxs-lookup"><span data-stu-id="42f3a-121">Message</span></span>|<span data-ttu-id="42f3a-122">Тип данных: `string`</span><span class="sxs-lookup"><span data-stu-id="42f3a-122">Data type: `string`</span></span><br /><br /> <span data-ttu-id="42f3a-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="42f3a-123">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="42f3a-124">Сообщение о событии.</span><span class="sxs-lookup"><span data-stu-id="42f3a-124">The event message.</span></span>|  
|<span data-ttu-id="42f3a-125">процессинфо</span><span class="sxs-lookup"><span data-stu-id="42f3a-125">ProcessInfo</span></span>|<span data-ttu-id="42f3a-126">Тип данных: `string`</span><span class="sxs-lookup"><span data-stu-id="42f3a-126">Data type: `string`</span></span><br /><br /> <span data-ttu-id="42f3a-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="42f3a-127">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="42f3a-128">Сведения об идентификаторе процесса сервера источника (SPID) события.</span><span class="sxs-lookup"><span data-stu-id="42f3a-128">Information about the source server process ID (SPID) for the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42f3a-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="42f3a-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42f3a-130">MOF</span><span class="sxs-lookup"><span data-stu-id="42f3a-130">MOF</span></span>|<span data-ttu-id="42f3a-131">Sqlmgmproviderxpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="42f3a-131">Sqlmgmproviderxpsp2up.mof</span></span>|  
|<span data-ttu-id="42f3a-132">DLL</span><span class="sxs-lookup"><span data-stu-id="42f3a-132">DLL</span></span>|<span data-ttu-id="42f3a-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="42f3a-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="42f3a-134">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="42f3a-134">Namespace</span></span>|<span data-ttu-id="42f3a-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="42f3a-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42f3a-136">Пример</span><span class="sxs-lookup"><span data-stu-id="42f3a-136">Example</span></span>  
 <span data-ttu-id="42f3a-137">В этом примере рассматривается извлечение значений для всех записанных событий в указанном файле журнала.</span><span class="sxs-lookup"><span data-stu-id="42f3a-137">The following example shows how to retrieve values for all logged events in a specified log file.</span></span> <span data-ttu-id="42f3a-138">Чтобы выполнить пример, замените \<*Instance_Name*> именем экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , например "instance1", и замените "File_Name" именем файла журнала ошибок, например "ErrorLog. 1".</span><span class="sxs-lookup"><span data-stu-id="42f3a-138">To run the example, replace \<*Instance_Name*> with the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as 'Instance1', and replace 'File_Name' with the name of the error log file, such as 'ERRORLOG.1'.</span></span>  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a><span data-ttu-id="42f3a-139">Комментарии</span><span class="sxs-lookup"><span data-stu-id="42f3a-139">Comments</span></span>  
 <span data-ttu-id="42f3a-140">Если имя *instanceName* или *filename* не указаны в инструкции WQL, запрос возвратит сведения для экземпляра по умолчанию и текущего [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файла журнала.</span><span class="sxs-lookup"><span data-stu-id="42f3a-140">When *InstanceName* or *FileName* are not provided in the WQL statement, the query will return information for the default instance and the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span> <span data-ttu-id="42f3a-141">Например, следующая инструкция WQL вернет все события журнала из текущего файла журнала (ERRORLOG) в текущем экземпляре (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="42f3a-141">For example, the following WQL statement will return all log events from the current log file (ERRORLOG) on the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a><span data-ttu-id="42f3a-142">Безопасность</span><span class="sxs-lookup"><span data-stu-id="42f3a-142">Security</span></span>  
 <span data-ttu-id="42f3a-143">Для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файлу журнала через инструментарий WMI необходимо иметь следующие разрешения на локальном и на удаленном компьютерах:</span><span class="sxs-lookup"><span data-stu-id="42f3a-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="42f3a-144">Доступ на чтение к пространству имен WMI **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="42f3a-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="42f3a-145">По умолчанию доступ для чтения задается для всех с помощью разрешения «Включить учетную запись».</span><span class="sxs-lookup"><span data-stu-id="42f3a-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
-   <span data-ttu-id="42f3a-146">Разрешение для чтения на папку, содержащую журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="42f3a-146">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="42f3a-147">По умолчанию журналы ошибок расположены по следующему пути (где \<*Drive> \* обозначает диск, на котором установлен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а \<*InstanceName*> — имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ):</span><span class="sxs-lookup"><span data-stu-id="42f3a-147">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="42f3a-148">\*\* \<Drive> : \PROGRAM Files\Microsoft SQL Server\MSSQL12\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="42f3a-148">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="42f3a-149">При соединении с использованием брандмауэра убедитесь, что в брандмауэре задано исключение для WMI на удаленных целевых компьютерах.</span><span class="sxs-lookup"><span data-stu-id="42f3a-149">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="42f3a-150">Дополнительные сведения см. [в статье удаленное подключение к WMI, начиная с Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="42f3a-150">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f3a-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="42f3a-151">See Also</span></span>  
 <span data-ttu-id="42f3a-152">[Класс SqlErrorLogFile](sqlerrorlogfile-class.md) </span><span class="sxs-lookup"><span data-stu-id="42f3a-152">[SqlErrorLogFile Class](sqlerrorlogfile-class.md) </span></span>  
 [<span data-ttu-id="42f3a-153">Просмотр автономных файлов журнала</span><span class="sxs-lookup"><span data-stu-id="42f3a-153">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
