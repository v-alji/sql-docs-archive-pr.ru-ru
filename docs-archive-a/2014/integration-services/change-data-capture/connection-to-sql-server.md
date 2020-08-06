---
title: Соединение с SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5bb582f9-68d3-4c1e-ab02-6fc16807f1a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6639118b3bd531e5cece8899eb0d68e00e566186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656531"
---
# <a name="connection-to-sql-server"></a><span data-ttu-id="ba983-102">Соединение с SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba983-102">Connection to SQL Server</span></span>
  <span data-ttu-id="ba983-103">Если имя входа, не имеющее роли с правами записи в базе данных MSXDBCDC (например, **db_owner** ), пытается создать экземпляр Oracle CDC, появляется диалоговое окно "Подключение к SQL Server".</span><span class="sxs-lookup"><span data-stu-id="ba983-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to create an Oracle CDC instanced, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="ba983-104">Чтобы создать новый экземпляр Oracle CDC, нужно ввести в этом окне учетные данные имени входа, имеющего права записи в базу данных MSXDBCDC, например члена роли базы данных **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="ba983-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to create the new Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="ba983-105">В диалоговом окне «Подключение к SQL Server» введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="ba983-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="ba983-106">Имя сервера</span><span class="sxs-lookup"><span data-stu-id="ba983-106">Server Name</span></span>  
 <span data-ttu-id="ba983-107">Введите имя сервера, на котором находится экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba983-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="ba983-108">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="ba983-108">Authentication</span></span>  
 <span data-ttu-id="ba983-109">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ba983-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="ba983-110">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="ba983-110">Windows Authentication</span></span>  
  
-   <span data-ttu-id="ba983-111">**Проверка подлинности SQL Server**. При выборе этого варианта необходимо ввести **Имя** и **Пароль** для пользователя в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с которым устанавливается соединение.</span><span class="sxs-lookup"><span data-stu-id="ba983-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
### <a name="options"></a><span data-ttu-id="ba983-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba983-112">Options</span></span>  
 <span data-ttu-id="ba983-113">Чтобы просмотреть доступные для настройки параметры, щелкните стрелку.</span><span class="sxs-lookup"><span data-stu-id="ba983-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="ba983-114">Для них можно оставить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba983-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="ba983-115">Доступные параметры:</span><span class="sxs-lookup"><span data-stu-id="ba983-115">The available options are:</span></span>  
  
-   <span data-ttu-id="ba983-116">**Время ожидания подключения**: введите время (в секундах), в течение которого программа ожидает подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , прежде чем выдать ошибку времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="ba983-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="ba983-117">Значение по умолчанию ― **15**.</span><span class="sxs-lookup"><span data-stu-id="ba983-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="ba983-118">**Время ожидания выполнения**: введите время (в секундах), в течение которого программа ожидает выполнения команды SQL, прежде чем выдать ошибку времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="ba983-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="ba983-119">Значение по умолчанию — **30**.</span><span class="sxs-lookup"><span data-stu-id="ba983-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="ba983-120">**Шифрование подключения**: выберите **Шифрование подключения** , чтобы устанавливаемое подключение к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шифровалось для обеспечения конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="ba983-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="ba983-121">**Дополнительно**: нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".</span><span class="sxs-lookup"><span data-stu-id="ba983-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba983-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba983-122">See Also</span></span>  
 [<span data-ttu-id="ba983-123">Разрешения, необходимые службе CDC для соединения с SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba983-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
