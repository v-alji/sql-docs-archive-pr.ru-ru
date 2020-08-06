---
title: Служба Windows сервера отчетов (MSSQLServer) 107 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8651f98b47b698fbe3cfb6a152b9220a84ed7256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658647"
---
# <a name="report-server-windows-service-mssqlserver-107"></a><span data-ttu-id="a803d-102">Служба Windows сервера отчетов (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="a803d-102">Report Server Windows Service (MSSQLServer) 107</span></span>
    
## <a name="details"></a><span data-ttu-id="a803d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a803d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a803d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a803d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a803d-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a803d-105">Event ID</span></span>|<span data-ttu-id="a803d-106">107</span><span class="sxs-lookup"><span data-stu-id="a803d-106">107</span></span>|  
|<span data-ttu-id="a803d-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="a803d-107">Event Source</span></span>|<span data-ttu-id="a803d-108">Служба Windows сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="a803d-108">Report Server Windows Service</span></span>|  
|<span data-ttu-id="a803d-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="a803d-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="a803d-110">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a803d-110">Message Text</span></span>|<span data-ttu-id="a803d-111">Служба Windows сервера отчетов (MSSQLSERVER) не может соединиться с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a803d-111">Report Server Windows Service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a803d-112">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a803d-112">Explanation</span></span>  
 <span data-ttu-id="a803d-113">Службе сервера отчетов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удается соединиться с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a803d-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service cannot connect to the report server database.</span></span> <span data-ttu-id="a803d-114">Такая ошибка возникает при перезапуске службы, если не удается установить соединение с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a803d-114">This error occurs during a service restart if a connection to the report server database cannot be established.</span></span> <span data-ttu-id="a803d-115">Эта ошибка возникает при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="a803d-115">Conditions under which this error occurs include the following:</span></span>  
  
-   <span data-ttu-id="a803d-116">Компонент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] — служба не была запущена в момент запуска службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a803d-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is not running when the Report Server service starts.</span></span>  
  
-   <span data-ttu-id="a803d-117">Не удалось установить соединение со службой компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , так как не включено использование удаленных соединений или протокола TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="a803d-117">The connection to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service fails because remote connections or the TCP/IP protocol is not enabled.</span></span>  
  
-   <span data-ttu-id="a803d-118">База данных сервера отчетов настроена неправильно.</span><span class="sxs-lookup"><span data-stu-id="a803d-118">The report server database is not configured correctly.</span></span>  
  
-   <span data-ttu-id="a803d-119">Учетная запись службы настроена неправильно или не имеет разрешений для доступа к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a803d-119">The service account is not configured correctly, or the account no longer has permissions on the report server database.</span></span> <span data-ttu-id="a803d-120">Это может произойти в том случае, если настройка учетной записи или базы данных сервера отчетов производилась не через программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a803d-120">This can occur if you do not use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set up the account or the report server database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a803d-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a803d-121">User Action</span></span>  
 <span data-ttu-id="a803d-122">Если служба компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] еще не запущена, то запустите ее и убедитесь, что включены удаленные соединения для протокола TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="a803d-122">Start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service if it is not running and check that remote connections are enabled for TCP/IP protocol.</span></span>  
  
 <span data-ttu-id="a803d-123">Производите настройку базы данных сервера отчетов и учетной записи службы при помощи программы настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a803d-123">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server database and service account.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="a803d-124">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="a803d-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a803d-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a803d-125">See Also</span></span>  
 <span data-ttu-id="a803d-126">[Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a803d-126">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="a803d-127">[Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a803d-127">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 [<span data-ttu-id="a803d-128">Запуск и остановка службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="a803d-128">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
