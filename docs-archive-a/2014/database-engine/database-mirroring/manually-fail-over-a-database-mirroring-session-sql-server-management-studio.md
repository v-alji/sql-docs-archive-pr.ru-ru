---
title: Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 4ecf9c63-b3a4-4c54-b553-5bc37973232b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f7f4547058b2dfd4229142dca73a7d9b4bdb239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751455"
---
# <a name="manually-fail-over-a-database-mirroring-session-sql-server-management-studio"></a><span data-ttu-id="747cf-102">Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="747cf-102">Manually Fail Over a Database Mirroring Session (SQL Server Management Studio)</span></span>
  <span data-ttu-id="747cf-103">Когда зеркальная база данных синхронизирована (то есть база данных находится в состоянии SYNCHRONIZED), владелец базы данных может инициировать отработку отказа на зеркальном сервере вручную.</span><span class="sxs-lookup"><span data-stu-id="747cf-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span>  
  
 <span data-ttu-id="747cf-104">При отработке отказа вручную основная и зеркальная роли сервера для базы данных, в которых произошла отработка отказа, меняются местами.</span><span class="sxs-lookup"><span data-stu-id="747cf-104">During a manual failover, the principal and mirror server roles are swapped for the database on which the failover occurs.</span></span> <span data-ttu-id="747cf-105">Зеркальная база данных становится основной базой данных, а основная — зеркальной.</span><span class="sxs-lookup"><span data-stu-id="747cf-105">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span> <span data-ttu-id="747cf-106">Например в следующей таблице показано, как отработка отказа вручную меняет местами роли двух участников зеркального отображения: `SQLDBENGINE0_1` и `SQLDBENGINE0_2`.</span><span class="sxs-lookup"><span data-stu-id="747cf-106">For example, the following table shows the how a manual failover swaps the roles of two mirroring partners: `SQLDBENGINE0_1` and `SQLDBENGINE0_2`.</span></span>  
  
|<span data-ttu-id="747cf-107">Сервер</span><span class="sxs-lookup"><span data-stu-id="747cf-107">Server</span></span>|<span data-ttu-id="747cf-108">До отработки отказа</span><span class="sxs-lookup"><span data-stu-id="747cf-108">Before failover</span></span>|<span data-ttu-id="747cf-109">После отработки отказа</span><span class="sxs-lookup"><span data-stu-id="747cf-109">After failover</span></span>|  
|------------|---------------------|--------------------|  
|`SQLDBENGINE0_1`|<span data-ttu-id="747cf-110">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="747cf-110">PRINCIPAL</span></span>|<span data-ttu-id="747cf-111">MIRROR</span><span class="sxs-lookup"><span data-stu-id="747cf-111">MIRROR</span></span>|  
|`SQLDBENGINE0_2`|<span data-ttu-id="747cf-112">MIRROR</span><span class="sxs-lookup"><span data-stu-id="747cf-112">MIRROR</span></span>|<span data-ttu-id="747cf-113">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="747cf-113">PRINCIPAL</span></span>|  
  
 <span data-ttu-id="747cf-114">Обратите внимание на то, что роли сервера для других сеансов зеркального отображения баз данных не подвергаются изменению.</span><span class="sxs-lookup"><span data-stu-id="747cf-114">Note that the server roles for other database mirroring sessions are not affected.</span></span> <span data-ttu-id="747cf-115">Дополнительные сведения см. в статье [Переключение ролей во время сеанса зеркального отображения базы данных (SQL Server)](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="747cf-115">For more information, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
### <a name="to-manually-fail-over-database-mirroring"></a><span data-ttu-id="747cf-116">Ручное переключение зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="747cf-116">To manually fail over database mirroring</span></span>  
  
1.  <span data-ttu-id="747cf-117">Установите соединение с экземпляром основного сервера и на панели **Обозреватель объектов** щелкните имя сервера, чтобы развернуть этот узел.</span><span class="sxs-lookup"><span data-stu-id="747cf-117">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="747cf-118">Раскройте узел **Базы данных**и выберите базу данных для перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="747cf-118">Expand **Databases**, and select the database to be failed over.</span></span>  
  
3.  <span data-ttu-id="747cf-119">Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="747cf-119">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="747cf-120">Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="747cf-120">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="747cf-121">Щелкните **Отработка отказа**.</span><span class="sxs-lookup"><span data-stu-id="747cf-121">Click **Failover**.</span></span>  
  
     <span data-ttu-id="747cf-122">Появится окно подтверждения.</span><span class="sxs-lookup"><span data-stu-id="747cf-122">A confirmation box appears.</span></span>  <span data-ttu-id="747cf-123">Основной сервер начинает работу с подключения к зеркальному серверу, используя проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="747cf-123">The principal server begins by trying to connect to the mirror server by using Windows Authentication.</span></span> <span data-ttu-id="747cf-124">Если проверка подлинности Windows не работает, основной сервер выводит диалоговое окно **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="747cf-124">If Windows Authentication does not work, the principal server displays the **Connect to Server** dialog box.</span></span> <span data-ttu-id="747cf-125">Если зеркальный сервер использует проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выберите вариант **Проверка подлинности SQL Server** в поле **Проверка подлинности** .</span><span class="sxs-lookup"><span data-stu-id="747cf-125">If the mirror server uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, select **SQL Server Authentication** in the **Authentication** box.</span></span> <span data-ttu-id="747cf-126">Укажите в текстовом поле **Имя входа** учетную запись входа, с которой устанавливается соединения на зеркальном сервере, а в текстовом поле **Пароль** — пароль для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="747cf-126">In the **Login** text box, specify the login account to connect with on the mirror server, and in the **Password** text box, specify the password for that account.</span></span>  
  
     <span data-ttu-id="747cf-127">Если отработка отказа выполняется успешно, диалоговое окно **Свойства базы данных** закрывается.</span><span class="sxs-lookup"><span data-stu-id="747cf-127">If failover succeeds, the **Database Properties** dialog box closes.</span></span> <span data-ttu-id="747cf-128">Зеркальная база данных становится основной базой данных, а основная — зеркальной.</span><span class="sxs-lookup"><span data-stu-id="747cf-128">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span>  
  
     <span data-ttu-id="747cf-129">При ошибке отработки отказа отображается сообщение об ошибке и диалоговое окно останется открытым.</span><span class="sxs-lookup"><span data-stu-id="747cf-129">If failover fails, an error message is displayed and the dialog box remains open.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="747cf-130">Если с момента открытия страницы **Зеркальное отображение** были изменены какие-либо свойства, эти изменения не будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="747cf-130">If you have modified any properties since opening the **Mirroring** page, those changes will not be saved.</span></span>  
  
     <span data-ttu-id="747cf-131">Диалоговое окно закрывается автоматически.</span><span class="sxs-lookup"><span data-stu-id="747cf-131">The dialog box closes automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747cf-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="747cf-132">See Also</span></span>  
 <span data-ttu-id="747cf-133">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="747cf-133">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="747cf-134">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="747cf-134">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="747cf-135">[Переключение сеанса зеркального отображения базы данных на другой ресурс вручную (язык Transact-SQL)](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="747cf-135">[Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="747cf-136">[Приостановка или возобновление сеанса зеркального отображения базы данных (SQL Server)](pause-or-resume-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="747cf-136">[Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="747cf-137">Удаление зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="747cf-137">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
  
