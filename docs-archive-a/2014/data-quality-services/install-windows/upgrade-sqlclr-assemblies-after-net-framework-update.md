---
title: Обновление сборок SQLCLR после установки обновлений .NET Framework | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b1a008cc-7e6b-4655-a869-bd429f986400
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45d60db413e11828f26bd03e1c8f350645838d12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665135"
---
# <a name="upgrade-sqlclr-assemblies-after-net-framework-update"></a><span data-ttu-id="872d3-102">Обновление сборок SQLCLR после загрузки обновлений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="872d3-102">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>
  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] <span data-ttu-id="872d3-103">(DQS) представляют собой набор процедур среды SQLCR, которые ссылаются на сборки Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="872d3-103">(DQS) is a collection of SQL Common Language Runtime (SQLCR) routines that reference Microsoft .NET Framework 4 assemblies.</span></span> <span data-ttu-id="872d3-104">Установка на компьютер любых обновлений .NET Framework, оказывающих влияние на какую-либо подобную сборку, приводит к изменениям в Module Version ID (MVID) сборки в глобальном кэше сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="872d3-104">When you install any .NET Framework updates on your computer that affect any such referenced .NET Framework assembly, it leads to a change in the Module Version ID (MVID) of the assembly in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="872d3-105">Это приводит к возникновению рассогласования между идентификаторами MVID используемой сборки в глобальном кэше сборок и сборки, входящей в состав [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="872d3-105">This causes a mismatch between the MVIDs of the referenced assembly in GAC and the assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="872d3-106">Если после обновления платформы .NET Framework необходимо перезагрузить компьютер с [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , то измененные сборки SQLCLR обновляются автоматически, чтобы устранить рассогласование идентификаторов MVID после перезагрузки компьютера [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="872d3-106">If the .NET Framework update requires you to restart the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, the affected SQLCLR assemblies are upgraded automatically to fix the MVID mismatch issue on restarting the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span> <span data-ttu-id="872d3-107">Однако при обновлениях платформы .NET Framework, не требующих перезагрузки сервера [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , при попытке подключения клиента [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] к серверу [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]происходит ошибка из-за рассогласования идентификаторов MVID сборок.</span><span class="sxs-lookup"><span data-stu-id="872d3-107">However, for .NET Framework updates that do not require you to restart your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, an error occurs due to the mismatch in the MVIDs of the assemblies when you try to connect to a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] using a [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span></span>  
  
```  
A new version of .NET was installed on this machine. In order to continue to work with DQS please run dqsinstaller.exe -upgradedlls.  
```  
  
 <span data-ttu-id="872d3-108">Чтобы исправить эту неполадку, необходимо обновить измененные сборки SQLCLR в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="872d3-108">To fix this issue, the affected SQLCLR assemblies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be upgraded.</span></span> <span data-ttu-id="872d3-109">Для этого запустите файл DQSInstaller.exe с параметром командой строки **upgradedlls** , что позволит пропустить повторное создание баз данных DQS и выполнить только обновления задействованных сборок.</span><span class="sxs-lookup"><span data-stu-id="872d3-109">You can do so by running the DQSInstaller.exe file with the **upgradedlls** command line parameter to skip recreating the DQS databases, and just upgrade the affected assemblies.</span></span> <span data-ttu-id="872d3-110">Существующие базы знаний, проекты служб DQS и любые другие данные в DQS сохранятся.</span><span class="sxs-lookup"><span data-stu-id="872d3-110">This ensures that your knowledge bases, data quality projects, and any other data in DQS are preserved.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="872d3-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="872d3-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="872d3-112">Необходимо выполнить вход от имени члена группы администраторов на компьютере [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="872d3-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="872d3-113">Учетная запись пользователя Windows должна входить в предопределенную роль сервера sysadmin на экземпляре SQL Server, где установлен сервер [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="872d3-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-sqlclr-assemblies"></a><span data-ttu-id="872d3-114">Обновление сборок SQLCLR</span><span class="sxs-lookup"><span data-stu-id="872d3-114">To upgrade SQLCLR Assemblies</span></span>  
  
1.  <span data-ttu-id="872d3-115">Откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="872d3-115">Start Command Prompt.</span></span>  
  
2.  <span data-ttu-id="872d3-116">В командной строке перейдите в папку, где находится файл DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="872d3-116">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="872d3-117">Если был установлен экземпляр SQL Server по умолчанию, файл DQSInstaller.exe будет находиться в папке «C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn».</span><span class="sxs-lookup"><span data-stu-id="872d3-117">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
3.  <span data-ttu-id="872d3-118">В командной строке введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="872d3-118">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgradedlls  
    ```  
  
4.  <span data-ttu-id="872d3-119">Остальные шаги совпадают с шагами 2–6 в разделе [Запуск файла DQSInstaller.exe с экрана "Пуск", из меню "Пуск" или из проводника Windows](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) статьи [Запуск файла DQSInstaller.exe для завершения установки сервера служб DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="872d3-119">Rest of the steps are same as steps 2-6 in the [Run DQSInstaller.exe from Start Screen, Start Menu or Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) section in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872d3-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="872d3-120">See Also</span></span>  
 <span data-ttu-id="872d3-121">[Install Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="872d3-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="872d3-122">Обновление схемы базы данных DQS после установки обновления SQL Server</span><span class="sxs-lookup"><span data-stu-id="872d3-122">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>](upgrade-dqs-databases-schema-after-installing-sql-server-update.md)  
  
  
