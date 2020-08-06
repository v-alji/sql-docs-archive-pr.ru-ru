---
title: Настройка разрешений файловой системы для доступа к компоненту ядра СУБД | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1d9abbd095f2d5be7415ed28a17fb710ff8ab504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669112"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a><span data-ttu-id="62856-102">Настройка разрешений файловой системы для доступа к компоненту ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="62856-102">Configure File System Permissions for Database Engine Access</span></span>
  <span data-ttu-id="62856-103">В этом разделе описана процедура предоставления компоненту [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]доступа к тому расположению в файловой системе, где хранятся файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="62856-103">This topic describes how to grant the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], file system access to the location where database files are stored.</span></span> <span data-ttu-id="62856-104">Служба компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] должна иметь разрешение файловой системы Windows для доступа к папке, в которой хранятся файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="62856-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] service must have permission of the Windows file system to access the file folder where database files are stored.</span></span> <span data-ttu-id="62856-105">Разрешение на расположение по умолчанию задается во время установки.</span><span class="sxs-lookup"><span data-stu-id="62856-105">Permission to the default location is configured during setup.</span></span> <span data-ttu-id="62856-106">Если файла базы данных размещаются в другом расположении, то необходимо выполнить эти действия, чтобы предоставить компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] разрешение полного доступа к этому расположению.</span><span class="sxs-lookup"><span data-stu-id="62856-106">If you place your database files in a different location, you might need to follow these steps to grant the [!INCLUDE[ssDE](../../includes/ssde-md.md)] the full control permission to that location.</span></span>  
  
 <span data-ttu-id="62856-107">Начиная с версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , разрешения назначаются идентификатору безопасности каждой из служб.</span><span class="sxs-lookup"><span data-stu-id="62856-107">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permissions are assigned to the per-service SID for each of its services.</span></span> <span data-ttu-id="62856-108">Эта система позволяет обеспечить изоляцию и всестороннюю защиту службы.</span><span class="sxs-lookup"><span data-stu-id="62856-108">This system helps provide service isolation and defense in depth.</span></span> <span data-ttu-id="62856-109">Идентификатор безопасности службы создается на основе имени службы и является уникальным для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="62856-109">The per-service SID is derived from the service name and is unique to each service.</span></span> <span data-ttu-id="62856-110">В разделе [Настройка учетных записей и разрешений службы Windows](configure-windows-service-accounts-and-permissions.md) описывается идентификатор безопасности каждой службы доступа, а имена перечисляются в разделе **Права и привилегии Windows**.</span><span class="sxs-lookup"><span data-stu-id="62856-110">The topic [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md) describes the per-service SID and provides the names in the section **Windows Privileges and Rights**.</span></span> <span data-ttu-id="62856-111">Разрешение на доступ к расположению файла назначается именно идентификатору безопасности службы.</span><span class="sxs-lookup"><span data-stu-id="62856-111">It is the per-service SID that must be assigned the access permission on the file location.</span></span>  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a><span data-ttu-id="62856-112">Предоставление разрешение на доступ к файловой системе идентификатору безопасности службы</span><span class="sxs-lookup"><span data-stu-id="62856-112">To Grant File System Permission to the Per-service SID</span></span>  
  
1.  <span data-ttu-id="62856-113">С помощью проводника Windows перейдите в папку файловой системы, в которой находятся файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="62856-113">Using Windows Explorer, navigate to the file system location where the database files are stored.</span></span> <span data-ttu-id="62856-114">Правой кнопкой мыши щелкните эту папку и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="62856-114">Right-click the file system folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="62856-115">На вкладке **Безопасность** щелкните **Изменить**и затем ― **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="62856-115">On the **Security** tab, click **Edit**, and then **Add**.</span></span>  
  
3.  <span data-ttu-id="62856-116">В диалоговом окне **Выбор пользователей, компьютеров, учетных записей служб или групп** щелкните **Расположения**, в начале списка расположений выберите имя своего компьютера и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="62856-116">In the **Select Users, Computer, Service Account, or Groups** dialog box, click **Locations**, at the top of the location list, select your computer name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="62856-117">В поле **Введите имена объектов для выбора** введите имя идентификатора безопасности службы, указанное в разделе Электронная документация **Настройка учетных записей службы Windows и разрешений**.</span><span class="sxs-lookup"><span data-stu-id="62856-117">In the **Enter the object names to select** box, type the name of the per-service SID listed in the Books Online topic **Configure Windows Service Accounts and Permissions**.</span></span> <span data-ttu-id="62856-118">(Для [!INCLUDE[ssDE](../../includes/ssde-md.md)] идентификатора безопасности службы используйте **NT SERVICE\MSSQLSERVER** для экземпляра по умолчанию или **NT SERVICE\MSSQL $ имя_экземпляра** для именованного экземпляра.)</span><span class="sxs-lookup"><span data-stu-id="62856-118">(For the [!INCLUDE[ssDE](../../includes/ssde-md.md)] per service SID, use **NT SERVICE\MSSQLSERVER** for a default instance, or **NT SERVICE\MSSQL$InstanceName** for a named instance.)</span></span>  
  
5.  <span data-ttu-id="62856-119">Щелкните **Проверить имена** , чтобы проверить введенные данные.</span><span class="sxs-lookup"><span data-stu-id="62856-119">Click **Check Names** to validate the entry.</span></span> <span data-ttu-id="62856-120">Проверка зачастую выявляет ошибки, по ее окончании может появиться сообщение о том, что имя не найдено.</span><span class="sxs-lookup"><span data-stu-id="62856-120">The validation often fails, and might advise you that the name was not found.</span></span> <span data-ttu-id="62856-121">При нажатии кнопки **ОК**открывается диалоговое окно **Обнаружено несколько имен** .</span><span class="sxs-lookup"><span data-stu-id="62856-121">When you click **OK**, a **Multiple Names Found** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="62856-122">Теперь выберите идентификатор безопасности службы: **MSSQLServer** или **NT SERVICE\MSSQL $ имя_экземпляра**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="62856-122">Now select the per-service SID, either **MSSQLSERVER** or **NT SERVICE\MSSQL$InstanceName**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="62856-123">Нажмите кнопку **ОК** еще раз, чтобы вернуться в диалоговое окно **разрешения** .</span><span class="sxs-lookup"><span data-stu-id="62856-123">Click **OK** again to return to the **Permissions** dialog box.</span></span>  
  
8.  <span data-ttu-id="62856-124">В поле имена **групп или пользователей** выберите идентификатор безопасности службы, а затем в поле **разрешения для** \<name> установите флажок **Разрешить** для **полного доступа**.</span><span class="sxs-lookup"><span data-stu-id="62856-124">In the **Group or user** names box, select the per-service SID, and then in the **Permissions for** \<name> box, select the **Allow** check box for **Full control**.</span></span>  
  
9. <span data-ttu-id="62856-125">Нажмите кнопку **Применить**, а затем дважды кнопку **ОК** , чтобы выполнить выход.</span><span class="sxs-lookup"><span data-stu-id="62856-125">Click **Apply**, and then click **OK** twice to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62856-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="62856-126">See Also</span></span>  
 <span data-ttu-id="62856-127">[Управление службами компонента Database Engine](manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="62856-127">[Manage the Database Engine Services](manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="62856-128">[Перемещение системных баз данных](../../relational-databases/databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="62856-128">[Move System Databases](../../relational-databases/databases/system-databases.md) </span></span>  
 [<span data-ttu-id="62856-129">Перемещение пользовательских баз данных</span><span class="sxs-lookup"><span data-stu-id="62856-129">Move User Databases</span></span>](../../relational-databases/databases/move-user-databases.md)  
  
  
