---
title: Просмотр состояния зеркального отображения базы данных (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc691e8b746a816ab88448e3399aebad6d8844e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658388"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a><span data-ttu-id="17966-102">Просмотр состояния зеркального отображения базы данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="17966-102">View the State of a Mirrored Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="17966-103">Во время сеанса зеркального отображения базы данных можно просмотреть его состояние на странице **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="17966-103">During a database mirroring session, you can view the status on the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a><span data-ttu-id="17966-104">Просмотр состояния сеанса зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="17966-104">To view the status of a database mirroring session</span></span>  
  
1.  <span data-ttu-id="17966-105">После подключения к экземпляру основного сервера в обозревателе объектов щелкните имя сервера, чтобы развернуть дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="17966-105">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="17966-106">Раскройте узел **Базы данных**и выберите базу данных для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="17966-106">Expand **Databases**, and select the database to be mirrored.</span></span>  
  
3.  <span data-ttu-id="17966-107">Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="17966-107">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="17966-108">Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="17966-108">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="17966-109">После начала зеркального отображения на панели **Состояние** отражается та же информация о состоянии сеанса зеркального отображения, что и при выборе страницы **Зеркальное отображение** или нажатии кнопки **Обновить** .</span><span class="sxs-lookup"><span data-stu-id="17966-109">After mirroring begins, the **Status** panel displays the status of the database mirroring session as of when you selected the **Mirroring** page or clicked the **Refresh** button.</span></span> <span data-ttu-id="17966-110">Возможны следующие состояния.</span><span class="sxs-lookup"><span data-stu-id="17966-110">The possible states are as follows:</span></span>  
  
    |<span data-ttu-id="17966-111">Состояния</span><span class="sxs-lookup"><span data-stu-id="17966-111">States</span></span>|<span data-ttu-id="17966-112">Объяснение</span><span class="sxs-lookup"><span data-stu-id="17966-112">Explanation</span></span>|  
    |------------|-----------------|  
    |\<blank>|<span data-ttu-id="17966-113">Не существует ни одного сеанса зеркального отображения, а сведения об активности не представлены на странице **Зеркальное отображение** .</span><span class="sxs-lookup"><span data-stu-id="17966-113">No database mirroring session exists and there is no activity to report on the **Mirroring** page.</span></span>|  
    |<span data-ttu-id="17966-114">Пауза</span><span class="sxs-lookup"><span data-stu-id="17966-114">Paused</span></span>|<span data-ttu-id="17966-115">Основная база данных запущена, но не посылает никаких записей журнала на зеркальный сервер.</span><span class="sxs-lookup"><span data-stu-id="17966-115">The principal database is running but is not sending any logs to the mirror server.</span></span> <span data-ttu-id="17966-116">Зеркальное отображение базы данных недоступно.</span><span class="sxs-lookup"><span data-stu-id="17966-116">The mirror copy of the database is not available.</span></span>|  
    |<span data-ttu-id="17966-117">Нет соединения</span><span class="sxs-lookup"><span data-stu-id="17966-117">No connection</span></span>|<span data-ttu-id="17966-118">Экземпляр основного сервера не может подключиться к другому участнику или следящему серверу (если он есть).</span><span class="sxs-lookup"><span data-stu-id="17966-118">The principal server instance cannot connect to its partner or to the witness server instance (if any)</span></span>|  
    |<span data-ttu-id="17966-119">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="17966-119">Synchronizing</span></span>|<span data-ttu-id="17966-120">Содержимое зеркальной базы данных отстает от содержимого основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="17966-120">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="17966-121">Экземпляр основного сервера отправляет записи журнала на экземпляр зеркального сервера, который применяет эти изменения к зеркальной базе данных для выполнения наката.</span><span class="sxs-lookup"><span data-stu-id="17966-121">The principal server instance is sending log records to the mirror server instance, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="17966-122">В начале сеанса зеркального отображения базы данных основная и зеркальная базы данных синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="17966-122">At the start of a database mirroring session, the mirror and principal databases are in the synchronizing state.</span></span>|  
    |<span data-ttu-id="17966-123">Отработка отказа</span><span class="sxs-lookup"><span data-stu-id="17966-123">Failover</span></span>|<span data-ttu-id="17966-124">Процесс отработки отказа вручную (смена ролей) начался на экземпляре основного сервера, но еще не был принят зеркальным сервером.</span><span class="sxs-lookup"><span data-stu-id="17966-124">On the principal server instance, a manual failover (role swap) has begun but has not yet accepted by the mirror.</span></span>|  
    |<span data-ttu-id="17966-125">синхронизировано;</span><span class="sxs-lookup"><span data-stu-id="17966-125">Synchronized</span></span>|<span data-ttu-id="17966-126">Зеркальная база данных содержит те же данные, что и основная база данных.</span><span class="sxs-lookup"><span data-stu-id="17966-126">The mirror database contains the same data as the principal database.</span></span> <span data-ttu-id="17966-127">Ручная и автоматическая отработка отказа возможна *только* в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="17966-127">Manual and automatic failover are possible *only* in the synchronized state.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17966-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="17966-128">See Also</span></span>  
 [<span data-ttu-id="17966-129">Состояния зеркального отображения (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="17966-129">Mirroring States &#40;SQL Server&#41;</span></span>](mirroring-states-sql-server.md)  
  
  
