---
title: Изменение сеанса расширенных событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 114ec05b-7eca-4c87-b276-25e37b84be39
author: rothja
ms.author: jroth
ms.openlocfilehash: 14be41e48262bc7ebc8aeeaf55185f5e35d0c72e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654287"
---
# <a name="alter-an-extended-events-session"></a><span data-ttu-id="9e7ea-102">Изменение сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="9e7ea-102">Alter an Extended Events Session</span></span>
  <span data-ttu-id="9e7ea-103">После того как создан сеанс расширенных событий, его можно изменить необходимым образом с помощью **Мастера расширенных событий SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-103">After you create an Extended Events session, you can alter it according to your needs using the **SQL Server Extended Events Wizard**.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="9e7ea-104">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="9e7ea-104">Before you Begin</span></span>  
 <span data-ttu-id="9e7ea-105">Нельзя изменять целевой объект для активных или неактивных сеансов, нельзя изменять настройки расширенных свойств для активного сеанса.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-105">You cannot alter a target for active and inactive sessions, and you cannot change the advanced properties configurations for an active session.</span></span>  
  
 <span data-ttu-id="9e7ea-106">Можно вносить следующие изменения как в активные, так и в неактивные сеансы событий.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-106">You can make the following alterations to both active and inactive event sessions:</span></span>  
  
-   <span data-ttu-id="9e7ea-107">Добавлять или удалять события, изменять настройки событий, например поля событий, фильтры и действия.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-107">Add or remove events from the session, and alter the event configurations such as event fields, filters and actions.</span></span>  
  
-   <span data-ttu-id="9e7ea-108">Добавьте или удалите целевой объект из сеанса событий.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-108">Add or remove a target from the event session.</span></span>  
  
-   <span data-ttu-id="9e7ea-109">Включите параметр **Запускать сеанс событий при запуске сервера** .</span><span class="sxs-lookup"><span data-stu-id="9e7ea-109">Enable the **Start the event session on server startup** option.</span></span>  
  
 <span data-ttu-id="9e7ea-110">Можно вносить в неактивный сеанс событий следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-110">You can make the following additional alterations to an inactive event session:</span></span>  
  
-   <span data-ttu-id="9e7ea-111">Включать параметр **Отслеживать связь между событиями** .</span><span class="sxs-lookup"><span data-stu-id="9e7ea-111">Enable the **Track the relationship between events** option.</span></span>  
  
-   <span data-ttu-id="9e7ea-112">Изменять конфигурацию расширенных свойств.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-112">Change the advanced properties configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e7ea-113">В **мастере расширенных событий SQL Server** не поддерживается изменение сеансов событий.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-113">The **SQL Server Extended Events Wizard** does not support event session modification.</span></span>  
  
## <a name="how-to-alter-an-extended-events-session-using-the-sql-server-extended-events-wizard"></a><span data-ttu-id="9e7ea-114">Как изменить сеанс расширенных событий с помощью мастера расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e7ea-114">How to alter an Extended Events session using the SQL Server Extended Events Wizard</span></span>  
  
-   <span data-ttu-id="9e7ea-115">В обозревателе объектов разверните **Управление**, **Расширенные события** и затем **Сеансы**.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-115">In Object Explorer, expand **Management**, expand **Extended Events**, and then expand **Sessions**.</span></span>  
  
-   <span data-ttu-id="9e7ea-116">Щелкните правой кнопкой мыши сеанс, который нужно изменить, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-116">Right-click the session you want to alter, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="9e7ea-117">В диалоговом окне **Свойства** внесите соответствующие изменения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9e7ea-117">In the **Properties** dialog box, make the appropriate changes, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7ea-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e7ea-118">See Also</span></span>  
 <span data-ttu-id="9e7ea-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9e7ea-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="9e7ea-120">Создание сеанса расширенных событий с помощью редактора запросов</span><span class="sxs-lookup"><span data-stu-id="9e7ea-120">Create an Extended Events Session Using Query Editor</span></span>](../../database-engine/create-an-extended-events-session-using-query-editor.md)  
  
  
