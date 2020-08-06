---
title: Разрешения, необходимые конструктору CDC для соединения с SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0815a5d8f1cb66dee0d290a45166ebb395c8efa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655293"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a><span data-ttu-id="a8547-102">Разрешения, необходимые конструктору CDC для соединения с SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8547-102">SQL Server Connection Required Permissions for the CDC Designer</span></span>
  <span data-ttu-id="a8547-103">Консоли конструктора CDC для работы требуются сведения о подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8547-103">The CDC Designer Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform its tasks.</span></span> <span data-ttu-id="a8547-104">В этом разделе описано, какие данные можно задать в диалоговом окне **Соединение с SQL Server** для настройки соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8547-104">This topic describes the information that can be provided in the **Connect to SQL Server** dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a8547-105">Диалоговое окно **Соединение с SQL Server** , например, в том случае, когда сведения о соединении с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отсутствуют либо когда у соединения отсутствуют необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="a8547-105">The **Connect to SQL Server** dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="a8547-106">В следующей таблице приведено описание различных задач, в рамках которых требуется подключение к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а также необходимых разрешений для имени пользователя/пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8547-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="a8547-107">Задача</span><span class="sxs-lookup"><span data-stu-id="a8547-107">Task</span></span>|<span data-ttu-id="a8547-108">Минимальные разрешения</span><span class="sxs-lookup"><span data-stu-id="a8547-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="a8547-109">Просмотр списка служб и экземпляров CDC, где используется связанный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8547-109">View the list of CDC Services and Instances using the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>|<span data-ttu-id="a8547-110">`db_datareader` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a8547-110">`db_datareader` role on MSXDBCDC</span></span>|  
|<span data-ttu-id="a8547-111">Запуск и остановка экземпляров CDC</span><span class="sxs-lookup"><span data-stu-id="a8547-111">Start/Stop CDC Instance(s)</span></span>|<span data-ttu-id="a8547-112">`db_datareader` и `db_datawriter` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a8547-112">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="a8547-113">Просмотр состояния экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="a8547-113">View the CDC Instance status.</span></span>|<span data-ttu-id="a8547-114">`db_owner` в базе данных экземпляра CDC</span><span class="sxs-lookup"><span data-stu-id="a8547-114">`db_owner` role on the CDC Instance database</span></span>|  
|<span data-ttu-id="a8547-115">Создание новой базы данных экземпляра CDC Oracle.</span><span class="sxs-lookup"><span data-stu-id="a8547-115">Create a new Oracle CDC Instance database.</span></span>|<span data-ttu-id="a8547-116">`dbcreator` предопределенная роль сервера</span><span class="sxs-lookup"><span data-stu-id="a8547-116">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="a8547-117">Создание нового экземпляра CDC Oracle.</span><span class="sxs-lookup"><span data-stu-id="a8547-117">Create a new Oracle CDC Instance.</span></span>|<span data-ttu-id="a8547-118">`db_datareader` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a8547-118">`db_datareader` role on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="a8547-119">`db_owner` в базе данных CDC, которая была создана.</span><span class="sxs-lookup"><span data-stu-id="a8547-119">`db_owner` role on the CDC database that was created.</span></span>|  
|<span data-ttu-id="a8547-120">Получение скриптов развертывания.</span><span class="sxs-lookup"><span data-stu-id="a8547-120">Get deployment scripts.</span></span>|<span data-ttu-id="a8547-121">`db_datareader` и `db_datawriter` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a8547-121">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="a8547-122">`db_owner` в связанной базе данных CDC</span><span class="sxs-lookup"><span data-stu-id="a8547-122">`db_owner` role on the relatedCDC database</span></span>|  
|<span data-ttu-id="a8547-123">Изменение конфигурации, а также добавление и удаление экземпляров отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a8547-123">Change configuration and add/remove capture instances.</span></span>|<span data-ttu-id="a8547-124">`db_datareader` и `db_datawriter` в MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="a8547-124">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="a8547-125">`db_owner` в связанной базе данных CDC</span><span class="sxs-lookup"><span data-stu-id="a8547-125">`db_owner` role on the related CDC database</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8547-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8547-126">See Also</span></span>  
 <span data-ttu-id="a8547-127">[Доступ к консоли конструктора CDC](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="a8547-127">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="a8547-128">Соединение с SQL Server для создания экземпляров</span><span class="sxs-lookup"><span data-stu-id="a8547-128">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
