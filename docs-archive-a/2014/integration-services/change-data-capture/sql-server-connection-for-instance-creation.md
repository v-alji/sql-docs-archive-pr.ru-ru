---
title: Соединение с SQL Server для создания экземпляров | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cdff17b763257c2a3280981c1f5c16040cc61413
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656526"
---
# <a name="sql-server-connection-for-instance-creation"></a><span data-ttu-id="1804e-102">Соединение с SQL Server для создания экземпляров</span><span class="sxs-lookup"><span data-stu-id="1804e-102">SQL Server Connection for Instance Creation</span></span>
  <span data-ttu-id="1804e-103">Одним из первых шагов при создании экземпляра CDC Oracle является создание базы данных CDC на целевом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1804e-103">One of the first steps when creating an Oracle CDC Instance is the creation of a CDC database on the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="1804e-104">Эта база данных CDC должна быть подготовлена к работе CDC SQL Server, для чего требуется имя входа, которое является членом предопределенной роли сервера `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="1804e-104">This CDC database is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="1804e-105">Если пользователь, запускающий мастер **создания экземпляра Oracle CDC** , не является членом предопределенной роли сервера `sysadmin` , то открывается диалоговое окно **Соединение с SQL Server** , где необходимо ввести учетные данные члена роли `sysadmin` , чтобы обеспечить подготовку базы данных задачей CDC SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1804e-105">When a user that starts the **Create an Oracle CDC Instance** wizard is not a member of the `sysadmin` fixed-server role, the **Connect to SQL Server** dialog box opens and requests the credentials for a member of the `sysadmin` role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="1804e-106">При создании базы данных CDC имя входа `sysadmin` удаляется, а работа возобновляется с первоначальным именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое использовалось для входа в консоль конструктора Oracle.</span><span class="sxs-lookup"><span data-stu-id="1804e-106">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="1804e-107">Список задач</span><span class="sxs-lookup"><span data-stu-id="1804e-107">Task List</span></span>  
 <span data-ttu-id="1804e-108">В диалоговом окне **Соединение с SQL Server** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="1804e-108">Enter the following information in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="1804e-109">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="1804e-109">**Server Name**</span></span>  
 <span data-ttu-id="1804e-110">Введите имя сервера, на котором находится экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1804e-110">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="1804e-111">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="1804e-111">**Authentication**</span></span>  
 <span data-ttu-id="1804e-112">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="1804e-112">Select one of the following:</span></span>  
  
-   <span data-ttu-id="1804e-113">**Проверка подлинности Windows.**</span><span class="sxs-lookup"><span data-stu-id="1804e-113">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="1804e-114">**Аутентификация SQL Server**: если вы выберете этот вариант, необходимо будет ввести **имя для входа** и **пароль** в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], к которому вы подключаетесь.</span><span class="sxs-lookup"><span data-stu-id="1804e-114">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="1804e-115">Имя входа должно иметь роль базы данных, которая обеспечивает доступ к базе данных MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="1804e-115">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="1804e-116">Рекомендуется, чтобы имя входа также имело доступ ко всем другим используемым базам данных. В противном случае пользователь не сможет просматривать данные из этих баз данных.</span><span class="sxs-lookup"><span data-stu-id="1804e-116">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
 <span data-ttu-id="1804e-117">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="1804e-117">**Options**</span></span>  
 <span data-ttu-id="1804e-118">Чтобы просмотреть доступные для настройки параметры, щелкните стрелку.</span><span class="sxs-lookup"><span data-stu-id="1804e-118">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="1804e-119">Для них можно оставить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1804e-119">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="1804e-120">Доступные параметры:</span><span class="sxs-lookup"><span data-stu-id="1804e-120">The available options are:</span></span>  
  
-   <span data-ttu-id="1804e-121">**Время ожидания соединения**: Введите время (в секундах), в течение которого служба CDC для Oracle ожидает установления соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Значение по умолчанию ― **15**.</span><span class="sxs-lookup"><span data-stu-id="1804e-121">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="1804e-122">**Время ожидания выполнения**: Введите время (в секундах), в течение которого служба Windows CDC Oracle ожидает выполнения команды. Значение по умолчанию — **30**.</span><span class="sxs-lookup"><span data-stu-id="1804e-122">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="1804e-123">**Шифровать соединение**: выберите параметр **Шифровать соединение**, чтобы обмен данными между службой Oracle CDC Service и целевым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполнялся по зашифрованному соединению.</span><span class="sxs-lookup"><span data-stu-id="1804e-123">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="1804e-124">**Дополнительно**: Нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".</span><span class="sxs-lookup"><span data-stu-id="1804e-124">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
     <span data-ttu-id="1804e-125">Дополнительные сведения о диалоговом окне «Дополнительные свойства подключения» см. в разделе [Advanced Connection Properties](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1804e-125">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1804e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="1804e-126">See Also</span></span>  
 <span data-ttu-id="1804e-127">[Создание базы данных изменения SQL Server](create-the-sql-server-change-database.md) </span><span class="sxs-lookup"><span data-stu-id="1804e-127">[Create the SQL Server Change Database](create-the-sql-server-change-database.md) </span></span>  
 [<span data-ttu-id="1804e-128">Разрешения, необходимые конструктору CDC для соединения с SQL Server</span><span class="sxs-lookup"><span data-stu-id="1804e-128">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
