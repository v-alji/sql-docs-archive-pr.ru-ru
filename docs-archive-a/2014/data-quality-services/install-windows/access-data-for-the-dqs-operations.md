---
title: Предоставление доступа к данным для операций со службами DQS | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 515b087a8d16e44314d1a21d3dfbd6f13c767f5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733201"
---
# <a name="access-data-for-the-dqs-operations"></a><span data-ttu-id="7740f-102">Предоставление доступа к данным для операций со службами DQS</span><span class="sxs-lookup"><span data-stu-id="7740f-102">Access Data for the DQS Operations</span></span>
  <span data-ttu-id="7740f-103">Чтобы использовать исходные данные для операций служб [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) и экспортировать обработанные данные, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7740f-103">To use your source data for [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) operations, and export your processed data, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="7740f-104">Скопируйте исходные данные в таблицу или представление в базе данных DQS_STAGING_DATA, а затем передайте данную таблицу или представление на обработку операции DQS.</span><span class="sxs-lookup"><span data-stu-id="7740f-104">Copy your source data to a table/view in the DQS_STAGING_DATA database, and then use it for DQS operations.</span></span> <span data-ttu-id="7740f-105">Можно также выполнить экспорт обработанных данных в новую таблицу в базе данных DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="7740f-105">You can also export the processed data to a new table in the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="7740f-106">Для этого учетной записи пользователя Windows должен быть предоставлен доступ на чтение и запись к базе данных DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="7740f-106">To do so, your Windows user account must be granted read/write access to the DQS_STAGING_DATA database.</span></span>  
  
-   <span data-ttu-id="7740f-107">Собственная база данных может использоваться как в качестве исходных данных для операций служб DQS, так и для экспорта обработанных данных.</span><span class="sxs-lookup"><span data-stu-id="7740f-107">Use your own database as the source data for the DQS operations, and destination for exporting the processed data.</span></span> <span data-ttu-id="7740f-108">Для этого убедитесь, что она размещена на том же экземпляре SQL Server, что и базы данных сервера служб Data Quality.</span><span class="sxs-lookup"><span data-stu-id="7740f-108">To do so, ensure that your database is in the same SQL Server instance as the Data Quality Server databases.</span></span> <span data-ttu-id="7740f-109">В противном случае база данных не будет доступна в клиенте служб Data Quality для операций DQS.</span><span class="sxs-lookup"><span data-stu-id="7740f-109">Otherwise, the database will not be available in the Data Quality Client for DQS operations.</span></span> <span data-ttu-id="7740f-110">Также для учетной записи пользователя Windows должен быть предоставлен доступ к базе данных DQS_STAGING_DATA для экспорта соответствующих результатов, так как они экспортируются в два этапа: сначала экспортируются во временные таблицы в базе данных DQS_STAGING_DATA, а затем перемещаются в таблицу целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="7740f-110">Also, your Windows user account must be granted access on the DQS_STAGING_DATA database for exporting the matching results because matching results are exported in two phases: first, the matching results are exported to the temporary tables in the DQS_STAGING_DATA database, and then moved to the table in your destination database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7740f-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7740f-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="7740f-112">Необходимо, чтобы установка сервера [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , запускаемая с помощью файла DQSInstaller.exe, была завершена.</span><span class="sxs-lookup"><span data-stu-id="7740f-112">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="7740f-113">Дополнительные сведения см. в разделе [Запуск файла DQSInstaller.exe для завершения установки сервера служб DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="7740f-113">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="7740f-114">Учетная запись пользователя Windows должна входить в соответствующую предопределенную роль сервера (например, securityadmin, serveradmin или sysadmin) на экземпляре компонента Database Engine для предоставления и изменения доступа имени входа SQL Server к базам данных.</span><span class="sxs-lookup"><span data-stu-id="7740f-114">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) in the database engine instance to grant/modify access to SQL login on databases.</span></span>  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqs_staging_data-database"></a><span data-ttu-id="7740f-115">Предоставление доступа на чтение и запись пользователям базы данных DQS_STAGING_DATA</span><span class="sxs-lookup"><span data-stu-id="7740f-115">To grant read/write access to a User on the DQS_STAGING_DATA Database</span></span>  
  
1.  <span data-ttu-id="7740f-116">Запустите среду Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7740f-116">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="7740f-117">В среде Microsoft SQL Server Management Studio разверните узел экземпляра SQL Server, а затем узлы **Безопасность**и **Имена входа**.</span><span class="sxs-lookup"><span data-stu-id="7740f-117">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="7740f-118">Правой кнопкой мыши щелкните имя входа SQL Server и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7740f-118">Right-click a SQL login, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7740f-119">В диалоговом окне **Свойства имени входа** щелкните страницу **Сопоставление пользователей** в левой части.</span><span class="sxs-lookup"><span data-stu-id="7740f-119">In the **Login Properties** dialog box, click the **User Mapping** page in the left pane.</span></span>  
  
5.  <span data-ttu-id="7740f-120">На правой панели установите флажок в столбце **Сопоставление** для базы данных **DQS_STAGING_DATA** , а затем выберите следующие роли в панели **Членство в роли базы данных для DQS_STAGING_DATA** :</span><span class="sxs-lookup"><span data-stu-id="7740f-120">In the right pane, select the check box under the **Map** column for the **DQS_STAGING_DATA** database, and then select the following roles in the **Database role membership for: DQS_STAGING_DATA** pane:</span></span>  
  
    -   <span data-ttu-id="7740f-121">**db_datareader**: чтение данных из таблиц и представлений.</span><span class="sxs-lookup"><span data-stu-id="7740f-121">**db_datareader**: Read data from tables/views.</span></span>  
  
    -   <span data-ttu-id="7740f-122">**db_datawriter**: добавление, удаление и изменение данных в таблицах.</span><span class="sxs-lookup"><span data-stu-id="7740f-122">**db_datawriter**: Add, delete, or change data in tables.</span></span>  
  
    -   <span data-ttu-id="7740f-123">**db_ddladmin**: создание, изменение или удаление таблиц и представлений.</span><span class="sxs-lookup"><span data-stu-id="7740f-123">**db_ddladmin**: Create, modify, or delete tables/views.</span></span>  
  
6.  <span data-ttu-id="7740f-124">В диалоговом окне **Свойства имени входа** нажмите кнопку **ОК** , чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="7740f-124">In the **Login Properties** dialog box, click **OK** to apply the changes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7740f-125">Next Steps</span><span class="sxs-lookup"><span data-stu-id="7740f-125">Next Steps</span></span>  
 <span data-ttu-id="7740f-126">Проверьте работоспособность операций служб DQS, использующих эту базу данных в качестве источника данных, а затем экспортирующих в нее обработанные данные.</span><span class="sxs-lookup"><span data-stu-id="7740f-126">Try performing DQS operations that accesses the database as data source for DQS operation, and then exports the processed data to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7740f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="7740f-127">See Also</span></span>  
 [<span data-ttu-id="7740f-128">Install Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="7740f-128">Install Data Quality Services</span></span>](install-data-quality-services.md)  
  
  
