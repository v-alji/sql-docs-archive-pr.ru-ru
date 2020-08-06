---
title: Разрешения, необходимые службе CDC для соединения с SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e63b98ffd0371bd5b70ecc0ac843ad40a4a5d03e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658349"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a><span data-ttu-id="251d3-102">Разрешения, необходимые службе CDC для соединения с SQL Server</span><span class="sxs-lookup"><span data-stu-id="251d3-102">SQL Server Connection Required Permissions for the CDC Service</span></span>
  <span data-ttu-id="251d3-103">Для консоли настройки службы CDC требуются сведения о подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для выполнения соответствующих задач.</span><span class="sxs-lookup"><span data-stu-id="251d3-103">The CDC Service Configuration Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform their tasks.</span></span> <span data-ttu-id="251d3-104">В этом разделе описываются сведения, которые можно указать в диалоговом окне «Подключение к SQL Server» для настройки подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="251d3-104">This topic describes the information that can be provided in the Connect to SQL Server dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="251d3-105">Диалоговое окно «Подключение к SQL Server» открывается при необходимости, например когда сведения о подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отсутствуют или когда они имеются, но для подключения нет требуемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="251d3-105">The Connect to SQL Server dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="251d3-106">В следующей таблице приведено описание различных задач, в рамках которых требуется подключение к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а также необходимых разрешений для имени пользователя/пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="251d3-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="251d3-107">Задача</span><span class="sxs-lookup"><span data-stu-id="251d3-107">Task</span></span>|<span data-ttu-id="251d3-108">Минимальные разрешения</span><span class="sxs-lookup"><span data-stu-id="251d3-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="251d3-109">Подготовка экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="251d3-109">Prepare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance.</span></span>|<span data-ttu-id="251d3-110">`dbcreator` предопределенная роль сервера</span><span class="sxs-lookup"><span data-stu-id="251d3-110">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="251d3-111">Создание имени входа службы Oracle CDC и SQL Server для использования службой Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="251d3-111">Create an Oracle CDC Service-SQL Server login for use by the Oracle CDC service.</span></span>|<span data-ttu-id="251d3-112">`public` предопределенная роль сервера</span><span class="sxs-lookup"><span data-stu-id="251d3-112">`public` fixed-server role</span></span>|  
|<span data-ttu-id="251d3-113">Создание имени входа службы Oracle CDC, которое будет использоваться для регистрации службы в MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="251d3-113">Create an Oracle CDC Service-login to use for registering the new service in MSXDBCDC.</span></span>|<span data-ttu-id="251d3-114">`db_datareader` и `db_datawriter` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="251d3-114">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="251d3-115">Изменение имени входа службы Oracle CDC так, чтобы оно могло использоваться для обновления регистрации службы в MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="251d3-115">Edit an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="251d3-116">`db_datareader` и `db_datawriter` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="251d3-116">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="251d3-117">Удаление имени входа службы Oracle CDC, предназначенного для обновления регистрации службы в MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="251d3-117">Delete an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="251d3-118">`db_datareader` и `db_datawriter` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="251d3-118">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="251d3-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="251d3-119">See Also</span></span>  
 <span data-ttu-id="251d3-120">[Соединение с SQL Server](connection-to-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="251d3-120">[Connection to SQL Server](connection-to-sql-server.md) </span></span>  
 [<span data-ttu-id="251d3-121">Соединение с SQL Server для удаления</span><span class="sxs-lookup"><span data-stu-id="251d3-121">Connection to SQL Server for Delete</span></span>](connection-to-sql-server-for-delete.md)  
  
  
