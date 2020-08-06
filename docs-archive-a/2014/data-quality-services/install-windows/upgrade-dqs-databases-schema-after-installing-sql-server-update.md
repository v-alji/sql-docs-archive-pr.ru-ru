---
title: Обновление схемы базы данных DQS после установки обновления SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: c8f3fbae-02c4-464d-a35c-7108f48c58cb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 80a1714ea250cf7cf5d34bc9d208a42a64284308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665137"
---
# <a name="upgrade-dqs-databases-schema-after-installing-sql-server-update"></a><span data-ttu-id="1c092-102">Обновление схемы базы данных DQS после установки обновления SQL Server</span><span class="sxs-lookup"><span data-stu-id="1c092-102">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>
  <span data-ttu-id="1c092-103">После установки обновления SQL Server (обновления, исправления или накопительного обновления) на ранее настроенном экземпляре DQS можно обновить схему баз данных DQS, запустив файл DQSInstaller.exe с параметром командной строки **upgrade** .</span><span class="sxs-lookup"><span data-stu-id="1c092-103">After you have installed a SQL Server update (patch, hotfix, or cumulative update) on a previously configured DQS instance, you might have to upgrade the DQS databases schema by running the DQSInstaller.exe file with the **upgrade** command line parameter.</span></span> <span data-ttu-id="1c092-104">В противном случае может появиться сообщение об ошибке при попытке соединения с сервером DQS через клиент Data Quality:</span><span class="sxs-lookup"><span data-stu-id="1c092-104">Otherwise, you might receive the following error while trying to connect to Data Quality Server using your Data Quality Client:</span></span>  
  
```  
An error occurred in the Microsoft .NET Framework while trying to load assembly id 65581.  
```  
  
 <span data-ttu-id="1c092-105">Обновление схемы баз данных DQS не влияет на существующие данные в базах данных DQS (базах знаний, проектах качества данных и экспортированные результаты в базе данных DQS_STAGING_DATA).</span><span class="sxs-lookup"><span data-stu-id="1c092-105">Upgrading DQS databases schema does not impact your existing data in the DQS databases (knowledge bases, data quality projects, and exported results in the DQS_STAGING_DATA database).</span></span> <span data-ttu-id="1c092-106">Однако необходимо создать резервную копию баз данных DQS, прежде чем обновлять схему баз данных DQS, чтобы предотвратить любую случайную потерю данных при обновлении схемы.</span><span class="sxs-lookup"><span data-stu-id="1c092-106">However, you must back up your DQS databases before upgrading DQS databases schema to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="1c092-107">Дополнительные сведения о создании резервной копии баз данных DQS см. в разделе [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1c092-107">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c092-108">Большинство обновлений SQL Server требует обновления схемы баз данных DQS.</span><span class="sxs-lookup"><span data-stu-id="1c092-108">Most of the SQL Server updates will require an upgrade to the DQS databases schema.</span></span> <span data-ttu-id="1c092-109">Дополнительные сведения об обновлениях SQL Server, которые требуют обновления до схемы баз данных DQS, см. в диаграмме на шаге 1.А в статье [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565)(Обновления службы DQS: установка накопительных обновлений или исправлений для служб Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="1c092-109">For information about the SQL Server updates that will require an upgrade to the DQS databases schema, see the chart in step 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1c092-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1c092-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="1c092-111">Необходимо выполнить вход от имени члена группы администраторов на компьютере [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c092-111">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="1c092-112">Учетная запись пользователя Windows должна входить в предопределенную роль сервера sysadmin на экземпляре SQL Server, где установлен сервер [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c092-112">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-dqs-databases-schema"></a><span data-ttu-id="1c092-113">Обновление схемы базы данных DQS</span><span class="sxs-lookup"><span data-stu-id="1c092-113">To upgrade DQS databases schema</span></span>  
  
1.  <span data-ttu-id="1c092-114">(Рекомендуется) Создать резервную копию баз данных DQS, прежде чем продолжить обновление схемы.</span><span class="sxs-lookup"><span data-stu-id="1c092-114">(Recommended) Back up your DQS databases before you proceed with the schema upgrade.</span></span> <span data-ttu-id="1c092-115">Дополнительные сведения о создании резервной копии баз данных DQS см. в разделе [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1c092-115">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="1c092-116">Откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="1c092-116">Start Command Prompt.</span></span>  
  
3.  <span data-ttu-id="1c092-117">В командной строке перейдите в папку, где находится файл DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="1c092-117">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="1c092-118">Если был установлен экземпляр SQL Server по умолчанию, файл DQSInstaller.exe будет находиться в папке «C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn».</span><span class="sxs-lookup"><span data-stu-id="1c092-118">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
4.  <span data-ttu-id="1c092-119">В командной строке введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="1c092-119">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgrade  
    ```  
  
5.  <span data-ttu-id="1c092-120">Установщик предложит создать резервную копию базы данных DQS, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="1c092-120">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="1c092-121">Если резервное копирование баз данных DQS уже выполнено, введите `Y` или `Yes` и нажмите клавишу ВВОД, чтобы продолжить обновление.</span><span class="sxs-lookup"><span data-stu-id="1c092-121">If you have already backed up your DQS databases, type `Y` or `Yes` and press ENTER to continue with the upgrade.</span></span>  
  
6.  <span data-ttu-id="1c092-122">После успешного обновления схемы баз данных DQS отображается сообщение о завершении.</span><span class="sxs-lookup"><span data-stu-id="1c092-122">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1c092-123">Next Steps</span><span class="sxs-lookup"><span data-stu-id="1c092-123">Next Steps</span></span>  
 <span data-ttu-id="1c092-124">Войдите на обновленный сервер из клиентского приложения Data Quality.</span><span class="sxs-lookup"><span data-stu-id="1c092-124">Log on to the upgraded Data Quality Server from a Data Quality Client application.</span></span>  
  
 <span data-ttu-id="1c092-125">Дополнительные сведения об обновлении схемы баз данных DQS после установки обновлений SQL Server и о шагах по устранению связанных с обновлением неполадок см. в статье [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565)(Обновления службы DQS: установка накопительных обновлений или исправлений для служб Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="1c092-125">For more information about upgrading DQS databases schema after installing SQL Server updates and associated troubleshooting steps, see [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c092-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c092-126">See Also</span></span>  
 <span data-ttu-id="1c092-127">[Install Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="1c092-127">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="1c092-128">Обновление сборок SQLCLR после загрузки обновлений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c092-128">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>](upgrade-sqlclr-assemblies-after-net-framework-update.md)  
  
  
