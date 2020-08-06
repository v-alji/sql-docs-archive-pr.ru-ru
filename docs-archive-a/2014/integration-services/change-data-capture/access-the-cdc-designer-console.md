---
title: Доступ к консоли конструктора CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750099"
---
# <a name="access-the-cdc-designer-console"></a><span data-ttu-id="41b5c-102">Доступ к консоли конструктора CDC</span><span class="sxs-lookup"><span data-stu-id="41b5c-102">Access the CDC Designer Console</span></span>
  <span data-ttu-id="41b5c-103">Доступ к консоли конструктора CDC осуществляется с компьютера, где установлена консоль.</span><span class="sxs-lookup"><span data-stu-id="41b5c-103">You can access the CDC Designer Console from the computer where you installed the console.</span></span> <span data-ttu-id="41b5c-104">Дополнительные сведения об установке см. в разделе «Установка».</span><span class="sxs-lookup"><span data-stu-id="41b5c-104">For more information about installation, see Installation.</span></span>  
  
 <span data-ttu-id="41b5c-105">При запуске консоли конструктора CDC открывается диалоговое окно «Подключение к SQL Server».</span><span class="sxs-lookup"><span data-stu-id="41b5c-105">When you open the CDC Designer Console, the Connect to SQL Server dialog box opens.</span></span>  
  
 <span data-ttu-id="41b5c-106">Имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с помощью которого осуществляется доступ к конструктору CDC, должно обладать разрешениями UPDATE на базу данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="41b5c-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that accesses the CDC Designer must have UPDATE permissions on the MSXDBCDC database.</span></span> <span data-ttu-id="41b5c-107">Кроме того, это имя входа должно быть членом предопределенной роли сервера `dbcreator` для создания новых экземпляров Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="41b5c-107">In addition, the login must also have the `dbcreator` fixed-server role to create new Oracle CDC Instances.</span></span> <span data-ttu-id="41b5c-108">Рекомендуется, чтобы имя входа также имело доступ SELECT ко всем используемым базам данных CDC, иначе пользователь не сможет видеть состояние этих баз данных.</span><span class="sxs-lookup"><span data-stu-id="41b5c-108">It is recommended that the login also have SELECT access to the CDC databases being used or the user will not be able to view the state of those databases.</span></span>  
  
 <span data-ttu-id="41b5c-109">В диалоговом окне «Подключение к SQL Server» введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="41b5c-109">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="41b5c-110">Имя сервера</span><span class="sxs-lookup"><span data-stu-id="41b5c-110">Server Name</span></span>  
 <span data-ttu-id="41b5c-111">Введите имя сервера, на котором находится экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41b5c-111">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="41b5c-112">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="41b5c-112">Authentication</span></span>  
 <span data-ttu-id="41b5c-113">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="41b5c-113">Select one of the following:</span></span>  
  
-   <span data-ttu-id="41b5c-114">**Проверка подлинности Windows.**</span><span class="sxs-lookup"><span data-stu-id="41b5c-114">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="41b5c-115">**Аутентификация SQL Server**: если вы выберете этот вариант, необходимо будет ввести **имя для входа** и **пароль** в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], к которому вы подключаетесь.</span><span class="sxs-lookup"><span data-stu-id="41b5c-115">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="41b5c-116">Имя входа должно иметь роль базы данных, которая обеспечивает доступ к базе данных MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="41b5c-116">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="41b5c-117">Рекомендуется, чтобы имя входа также имело доступ ко всем другим используемым базам данных. В противном случае пользователь не сможет просматривать данные из этих баз данных.</span><span class="sxs-lookup"><span data-stu-id="41b5c-117">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
### <a name="options"></a><span data-ttu-id="41b5c-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="41b5c-118">Options</span></span>  
 <span data-ttu-id="41b5c-119">Чтобы просмотреть доступные для настройки параметры, щелкните стрелку.</span><span class="sxs-lookup"><span data-stu-id="41b5c-119">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="41b5c-120">Для них можно оставить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41b5c-120">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="41b5c-121">Доступные параметры:</span><span class="sxs-lookup"><span data-stu-id="41b5c-121">The available options are:</span></span>  
  
 <span data-ttu-id="41b5c-122">**Время ожидания соединения**</span><span class="sxs-lookup"><span data-stu-id="41b5c-122">**Connection Timeout**</span></span>  
 <span data-ttu-id="41b5c-123">Введите время (в секундах), в течение которого служба CDC для Oracle ожидает установления соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Значение по умолчанию ― **15**.</span><span class="sxs-lookup"><span data-stu-id="41b5c-123">Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
 <span data-ttu-id="41b5c-124">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="41b5c-124">**Execution Timeout**</span></span>  
 <span data-ttu-id="41b5c-125">Введите время (в секундах), в течение которого служба Windows CDC Oracle ожидает выполнения команды. Значение по умолчанию — **30**.</span><span class="sxs-lookup"><span data-stu-id="41b5c-125">Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
 <span data-ttu-id="41b5c-126">**Шифровать соединение**</span><span class="sxs-lookup"><span data-stu-id="41b5c-126">**Encrypt Connection**</span></span>  
 <span data-ttu-id="41b5c-127">Выберите параметр **Шифровать соединение[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы обмен данными между Oracle CDC Service и целевым экземпляром**  выполнялся по зашифрованному соединению. **Дополнительно**. Нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".</span><span class="sxs-lookup"><span data-stu-id="41b5c-127">Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="41b5c-128">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="41b5c-128">**Advanced**</span></span>  
 <span data-ttu-id="41b5c-129">Нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".</span><span class="sxs-lookup"><span data-stu-id="41b5c-129">Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="41b5c-130">Дополнительные сведения о диалоговом окне «Дополнительные свойства подключения» см. в разделе [Advanced Connection Properties](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="41b5c-130">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b5c-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="41b5c-131">See Also</span></span>  
 [<span data-ttu-id="41b5c-132">Разрешения, необходимые конструктору CDC для соединения с SQL Server</span><span class="sxs-lookup"><span data-stu-id="41b5c-132">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
