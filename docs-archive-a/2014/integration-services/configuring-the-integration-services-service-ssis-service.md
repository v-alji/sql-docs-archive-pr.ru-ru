---
title: Настройка службы Integration Services (службы SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- configuration files [Integration Services]
- service [Integration Services], configuring
- default configuration files
ms.assetid: 36d78393-a54c-44b0-8709-7f003f44c27f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70c41377a2c302e1a021c6ade2a9d487579fa64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738630"
---
# <a name="configuring-the-integration-services-service-ssis-service"></a><span data-ttu-id="16dda-102">Настройка служб Integration Services (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="16dda-102">Configuring the Integration Services Service (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="16dda-103">В данном разделе описывается компонент [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] — служба Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16dda-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] <span data-ttu-id="16dda-104">поддерживает эту службу для обеспечения обратной совместимости с более ранними версиями служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16dda-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="16dda-105">Начиная с [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], на сервере служб Integration Services можно управлять пакетами.</span><span class="sxs-lookup"><span data-stu-id="16dda-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="16dda-106">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] используют для определения параметров файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="16dda-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service relies on a configuration file for its settings.</span></span> <span data-ttu-id="16dda-107">По умолчанию имя этого файла конфигурации MsDtsSrvr.ini.xml, а файл находится в папке%ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="16dda-107">By default, the name for this configuration file is MsDtsSrvr.ini.xml, and the file is located in the folder, %ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span></span>  
  
 <span data-ttu-id="16dda-108">Обычно не нужно делать какие-либо изменения в этом файле конфигурации или изменять расположение файла по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16dda-108">Typically, you do not have to make any changes to this configuration file, nor do you have to change the file's default location.</span></span> <span data-ttu-id="16dda-109">Однако если пакеты хранятся в именованном или удаленном экземпляре компонента [!INCLUDE[ssDE](../includes/ssde-md.md)]либо в нескольких экземплярах компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], необходимо изменить файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="16dda-109">However, you will have to modify the configuration file if your packages are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)], or in multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="16dda-110">Кроме того, если файл конфигурации переносится в расположение, отличное от расположения по умолчанию, необходимо изменить раздел реестра, указывающий расположение файла.</span><span class="sxs-lookup"><span data-stu-id="16dda-110">Also, if you move the configuration file to a location other than the default location, you will have to modify the Registry key that specifies the file location.</span></span>  
  
## <a name="configuration-file-contents"></a><span data-ttu-id="16dda-111">Содержимое файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="16dda-111">Configuration File Contents</span></span>  
 <span data-ttu-id="16dda-112">При установке служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]процесс установки создает и устанавливает файл конфигурации для службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16dda-112">When you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the setup process creates and installs the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="16dda-113">Этот файл конфигурации содержит следующие настройки.</span><span class="sxs-lookup"><span data-stu-id="16dda-113">This configuration file contains the following settings:</span></span>  
  
-   <span data-ttu-id="16dda-114">При остановки службы пакетам посылается команда остановки.</span><span class="sxs-lookup"><span data-stu-id="16dda-114">Packages are sent a stop command when the service stops.</span></span>  
  
-   <span data-ttu-id="16dda-115">Корневыми папками служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] для отображения в обозревателе объектов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] являются папки MSDB и файловой системы.</span><span class="sxs-lookup"><span data-stu-id="16dda-115">The root folders to display for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in Object Explorer of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are the MSDB and File System folders.</span></span>  
  
-   <span data-ttu-id="16dda-116">Пакеты в файловой системе, которыми [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] управляет служба, находятся в%ProgramFiles%\MICROSOFT SQL Server\120\DTS\Packages.</span><span class="sxs-lookup"><span data-stu-id="16dda-116">The packages in the file system that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages are located in %ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span></span>  
  
 <span data-ttu-id="16dda-117">В этом файле конфигурации указывается, какая база данных msdb содержит пакеты, которыми будет управлять служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16dda-117">This configuration file also specifies which msdb database contains the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service will manage.</span></span> <span data-ttu-id="16dda-118">По умолчанию служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] настроена для управления пакетами в базе данных msdb экземпляра компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], который установлен одновременно со службами [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16dda-118">By default, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed at the same time as [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="16dda-119">Если экземпляр компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] не установлен в то же время, служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] будет настроена для управления пакетами базы данных msdb локального экземпляра по умолчанию компонента [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16dda-119">If an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] is not installed at the same time, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the local, default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
### <a name="default-configuration-file-example"></a><span data-ttu-id="16dda-120">Пример файла конфигурации по умолчанию</span><span class="sxs-lookup"><span data-stu-id="16dda-120">Default Configuration File Example</span></span>  
 <span data-ttu-id="16dda-121">В следующем примере показан файл конфигурации по умолчанию, который задает следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="16dda-121">The following example shows a default configuration file that specifies the following settings:</span></span>  
  
-   <span data-ttu-id="16dda-122">Выполнение пакетов прекращается, если останавливается служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16dda-122">Packages stop running when the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service stops.</span></span>  
  
-   <span data-ttu-id="16dda-123">Корневыми папками для хранилища пакетов в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] являются MSDB и File System.</span><span class="sxs-lookup"><span data-stu-id="16dda-123">The root folders for package storage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are MSDB and File System.</span></span>  
  
-   <span data-ttu-id="16dda-124">Эта служба управляет пакетами, хранящимися в базе данных msdb локального экземпляра по умолчанию [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16dda-124">The service manages packages that are stored in the msdb database of the local, default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="16dda-125">Службы управляют пакетами, хранящимися в папке Packages файловой системы.</span><span class="sxs-lookup"><span data-stu-id="16dda-125">The service manages packages that are stored in the file system in the Packages folder.</span></span>  
  
 <span data-ttu-id="16dda-126">**Пример стандартного файла конфигурации**</span><span class="sxs-lookup"><span data-stu-id="16dda-126">**Example of a Default Configuration File**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>.</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file"></a><span data-ttu-id="16dda-127">Изменение файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="16dda-127">Modification of the Configuration File</span></span>  
 <span data-ttu-id="16dda-128">Можно изменить файл конфигурации, чтобы продолжить выполнение пакетов при остановке службы, отображать дополнительные корневые папки в обозревателе объектов или указать другую папку или дополнительные папки файловой системы, которые будут управляться службой [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16dda-128">You can modify the configuration file to allow packages to continue running if the service stops, to display additional root folders in Object Explorer, or to specify a different folder or additional folders in the file system to be managed by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="16dda-129">Например, можно создать дополнительные корневые папки типа `SqlServerFolder`, чтобы управлять пакетами в базах данных msdb дополнительных экземпляров компонента [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16dda-129">For example, you can create additional root folders of type, `SqlServerFolder`, to manage packages in the msdb databases of additional instances of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16dda-130">Некоторые символы в именах папок являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="16dda-130">Some characters are not valid in folder names.</span></span> <span data-ttu-id="16dda-131">Допустимые знаки в именах папок определяются классом [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]**System.IO.Path** и полем **GetInvalidFilenameChars** .</span><span class="sxs-lookup"><span data-stu-id="16dda-131">Valid characters for folder names are determined by the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] class **System.IO.Path** and the **GetInvalidFilenameChars** field.</span></span> <span data-ttu-id="16dda-132">Поле **GetInvalidFilenameChars** содержит специфический для платформы набор знаков, которые не могут быть использованы в аргументах, содержащих строки пути и передаваемых элементам класса **Path** .</span><span class="sxs-lookup"><span data-stu-id="16dda-132">The **GetInvalidFilenameChars** field provides a platform-specific array of characters that cannot be specified in path string arguments passed to members of the **Path** class.</span></span> <span data-ttu-id="16dda-133">Набор недопустимых символов меняется в зависимости от файловой системы.</span><span class="sxs-lookup"><span data-stu-id="16dda-133">The set of invalid characters can vary by file system.</span></span> <span data-ttu-id="16dda-134">Обычно недопустимые символы включают кавычки ("), знак «меньше» (<) и вертикальную черту (|).</span><span class="sxs-lookup"><span data-stu-id="16dda-134">Typically, invalid characters are the quotation mark ("), less than (<) character, and pipe (|) character.</span></span>  
  
 <span data-ttu-id="16dda-135">Однако чтобы управлять пакетами, хранящимися в именованном или удаленном экземпляре компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], необходимо изменить файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="16dda-135">However, you will have to modify the configuration file to manage packages that are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="16dda-136">Если не обновить файл конфигурации, в среде **нельзя будет использовать** обозреватель объектов [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , чтобы просмотреть пакеты, хранящиеся в базе данных msdb на именованном или удаленном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="16dda-136">If you do not update the configuration file, you cannot use **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view packages that are stored in the msdb database on the named instance or the remote instance.</span></span> <span data-ttu-id="16dda-137">При попытке использовать **обозреватель объектов** для просмотра этих пакетов появляется следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="16dda-137">If you try to use **Object Explorer** to view these packages, you receive the following error message:</span></span>  
  
 `Failed to retrieve data for this request. (Microsoft.SqlServer.SmoEnum)`  
  
 `The SQL Server specified in Integration Services service configuration is not present or is not available. This might occur when there is no default instance of SQL Server on the computer. For more information, see the topic "Configuring the Integration Services Service" in SQL Server 2008 Books Online.`  
  
 `Login Timeout Expired`  
  
 `An error has occurred while establishing a connection to the server. When connecting to SQL Server 2008, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.`  
  
 `Named Pipes Provider: Could not open a connection to SQL Server [2]. (MsDtsSvr).`  
  
 <span data-ttu-id="16dda-138">Чтобы изменить файл конфигурации для службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , используется текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="16dda-138">To modify the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, you use a text editor.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="16dda-139">После изменения файла конфигурации службы необходимо перезапустить службы, чтобы они использовали обновленную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="16dda-139">After you modify the service configuration file, you must restart the service to use the updated service configuration.</span></span>  
  
### <a name="modified-configuration-file-example"></a><span data-ttu-id="16dda-140">Пример измененного файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="16dda-140">Modified Configuration File Example</span></span>  
 <span data-ttu-id="16dda-141">В следующем примере показан модифицированный файл конфигурации для службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16dda-141">The following example shows a modified configuration file for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="16dda-142">Этот файл предназначен для именованного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , называемого `InstanceName` на сервере с именем `ServerName`.</span><span class="sxs-lookup"><span data-stu-id="16dda-142">This file is for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] called `InstanceName` on a server named `ServerName`.</span></span>  
  
 <span data-ttu-id="16dda-143">**Пример модифицированного файла конфигурации для именованного экземпляра SQL Server**</span><span class="sxs-lookup"><span data-stu-id="16dda-143">**Example of a Modified Configuration File for a Named Instance of SQL Server**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>ServerName\InstanceName</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file-location"></a><span data-ttu-id="16dda-144">Изменение расположения файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="16dda-144">Modification of the Configuration File Location</span></span>  
<span data-ttu-id="16dda-145">Раздел реестра **HKEY_LOCAL_MACHINE \СОФТВАРЕ\МИКРОСОФТ\МИКРОСОФТ SQL Server\120\SSIS\ServiceConfigFile** указывает расположение и имя файла конфигурации, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] используемого службой.</span><span class="sxs-lookup"><span data-stu-id="16dda-145">The Registry key **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\ServiceConfigFile** specifies the location and name for the configuration file that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service uses.</span></span> <span data-ttu-id="16dda-146">Значение по умолчанию для раздела реестра — **C:\Program FILES\MICROSOFT SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span><span class="sxs-lookup"><span data-stu-id="16dda-146">The default value of the Registry key is **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span></span> <span data-ttu-id="16dda-147">Можно изменить значение этого раздела реестра, чтобы использовать другое имя и местонахождение файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="16dda-147">You can update the value of the Registry key to use a different name and location for the configuration file.</span></span> <span data-ttu-id="16dda-148">Обратите внимание, что номер версии в пути (120 для SQL Server [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] ) будет зависеть от версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16dda-148">Note that the version number in the path (120 for SQL Server  [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)]) will vary depending on the SQL Server version.</span></span> 
  
  
> [!CAUTION]  
>  <span data-ttu-id="16dda-149">Неправильное изменение реестра может приводить к серьезным проблемам, вплоть до необходимости переустановки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="16dda-149">Incorrectly editing the Registry can cause serious problems that may require you to reinstall your operating system.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="16dda-150">не гарантирует возможность разрешения проблем, возникших в результате неправильного изменения реестра.</span><span class="sxs-lookup"><span data-stu-id="16dda-150">cannot guarantee that problems resulting from editing the Registry incorrectly can be resolved.</span></span> <span data-ttu-id="16dda-151">Перед изменением реестра создайте резервную копию всех необходимых данных.</span><span class="sxs-lookup"><span data-stu-id="16dda-151">Before editing the Registry, back up any valuable data.</span></span> <span data-ttu-id="16dda-152">Дополнительные сведения о том, как выполнять создание резервной копии, восстановление и изменение системного реестра, см. в [!INCLUDE[msCoName](../includes/msconame-md.md)] статье базы знаний [Описание системного реестра Microsoft Windows](https://support.microsoft.com/kb/256986).</span><span class="sxs-lookup"><span data-stu-id="16dda-152">For information about how to back up, restore, and edit the Registry, see the [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base article, [Description of the Microsoft Windows registry](https://support.microsoft.com/kb/256986).</span></span>  
  
 <span data-ttu-id="16dda-153">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] загружают файл конфигурации при запуске.</span><span class="sxs-lookup"><span data-stu-id="16dda-153">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service loads the configuration file when the service is started.</span></span> <span data-ttu-id="16dda-154">Все изменения записей реестра требуют перезапуска службы.</span><span class="sxs-lookup"><span data-stu-id="16dda-154">Any changes to the Registry entry require that the service be restarted.</span></span>  
  
  
