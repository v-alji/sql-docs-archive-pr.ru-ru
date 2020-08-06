---
title: Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- monitoring database mirroring [SQL Server]
- Database Mirroring Monitor [SQL Server], starting
- database mirroring [SQL Server], monitoring
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67c7b393b28d4d400535281c18c637146a5d8da7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654494"
---
# <a name="start-database-mirroring-monitor-sql-server-management-studio"></a><span data-ttu-id="58a4b-102">Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="58a4b-102">Start Database Mirroring Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="58a4b-103">Монитор зеркального отображения баз данных является частью монитора [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запускаемого в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58a4b-103">The Database Mirroring Monitor is part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitor, which is launched from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58a4b-104">Монитор зеркального отображения баз данных доступен не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58a4b-104">Database Mirroring Monitor is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="58a4b-105">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="58a4b-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
### <a name="to-launch-the-database-mirroring-monitor"></a><span data-ttu-id="58a4b-106">Запуск монитора зеркального отображения баз данных</span><span class="sxs-lookup"><span data-stu-id="58a4b-106">To launch the Database Mirroring Monitor</span></span>  
  
1.  <span data-ttu-id="58a4b-107">После подключения к экземпляру основного сервера в обозревателе объектов щелкните имя сервера, чтобы развернуть дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="58a4b-107">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="58a4b-108">Разверните узел **Базы данных**и выберите базу данных для мониторинга.</span><span class="sxs-lookup"><span data-stu-id="58a4b-108">Expand **Databases**, and select the database to be monitored.</span></span>  
  
3.  <span data-ttu-id="58a4b-109">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем щелкните **Запустить монитор зеркального отображения баз данных**.</span><span class="sxs-lookup"><span data-stu-id="58a4b-109">Right-click the database, select **Tasks**, and then click **Launch Database Mirroring Monitor**.</span></span>  
  
4.  <span data-ttu-id="58a4b-110">В диалоговом окне **Монитор зеркального отображения баз данных** нажмите кнопку **Зарегистрировать зеркальную базу данных** , чтобы зарегистрировать одну или более зеркальных баз данных.</span><span class="sxs-lookup"><span data-stu-id="58a4b-110">In the **Database Mirroring Monitor** dialog box, click **Register Mirrored Database** to register one or more mirrored database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58a4b-111">После регистрации базы данных на одном партнере база данных автоматически регистрируется на других партнерах.</span><span class="sxs-lookup"><span data-stu-id="58a4b-111">When you register a database at one partner, the database is automatically registered at the other partner.</span></span> <span data-ttu-id="58a4b-112">Если монитор уже имеет учетные данные соединения для экземпляра другого участника, они используются для подключения.</span><span class="sxs-lookup"><span data-stu-id="58a4b-112">If the monitor already has connection credentials for the other partner instance, those are used to connect.</span></span> <span data-ttu-id="58a4b-113">В противном случае, монитор попытается подключиться с помощью проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="58a4b-113">Otherwise the monitor attempts to connect using Windows Authentication.</span></span> <span data-ttu-id="58a4b-114">Если необходимо изменить учетные данные для подключения к экземпляру сервера, установите флажок **Показать диалоговое окно «Управление соединениями сервера» после нажатия кнопки «ОК»**.</span><span class="sxs-lookup"><span data-stu-id="58a4b-114">If you want to change the credentials used to connect to either server instance, click **Show the Manage Server Connections dialog box when I click OK**.</span></span>  
  
 <span data-ttu-id="58a4b-115">Дополнительные сведения о мониторе зеркального отображения баз данных см. в разделе [Обзор монитора зеркального отображения баз данных](database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="58a4b-115">For more information about Database Mirroring Monitor, see [Database Mirroring Monitor Overview](database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a4b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="58a4b-116">See Also</span></span>  
 <span data-ttu-id="58a4b-117">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="58a4b-117">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="58a4b-118">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="58a4b-118">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
  
