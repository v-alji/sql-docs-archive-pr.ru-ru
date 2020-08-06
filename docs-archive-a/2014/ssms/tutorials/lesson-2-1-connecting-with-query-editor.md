---
title: Подключение к редактору запросов | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 48725f54-a7b6-4b79-948e-965c1fe4eef1
author: stevestein
ms.author: sstein
ms.openlocfilehash: b50783450dfb9516c78a465806ee322d7a575377
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665726"
---
# <a name="connecting-with-query-editor"></a><span data-ttu-id="05bdd-102">Соединение с редактором запросов</span><span class="sxs-lookup"><span data-stu-id="05bdd-102">Connecting with Query Editor</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="05bdd-103">можно писать или изменять код без соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="05bdd-103">permits you to write or edit code while disconnected from the server.</span></span> <span data-ttu-id="05bdd-104">Это может оказаться полезным в том случае, если сервер недоступен или требуется экономить ограниченные ресурсы сервера или сети.</span><span class="sxs-lookup"><span data-stu-id="05bdd-104">This can be useful when the server is not available or when you want to conserve scarce server or network resources.</span></span> <span data-ttu-id="05bdd-105">Можно заменить соединение с редактором запросов на соединение с новым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , не открывая нового окна редактора запросов и не вводя код повторно.</span><span class="sxs-lookup"><span data-stu-id="05bdd-105">You can also change the connection of Query Editor to a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without opening a new Query Editor window or retyping your code.</span></span>  
  
## <a name="coding-offline"></a><span data-ttu-id="05bdd-106">Программирование в режиме «вне сети»</span><span class="sxs-lookup"><span data-stu-id="05bdd-106">Coding Offline</span></span>  
  
#### <a name="to-write-code-offline-and-then-connect-to-different-servers"></a><span data-ttu-id="05bdd-107">Написание программы в режиме «вне сети» с последующим подключением к различным серверам</span><span class="sxs-lookup"><span data-stu-id="05bdd-107">To write code offline and then connect to different servers</span></span>  
  
1.  <span data-ttu-id="05bdd-108">На панели инструментов среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] нажмите кнопку **Запрос к ядру СУБД** , чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="05bdd-108">On the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] toolbar, click **Database Engine Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="05bdd-109">В диалоговом окне **Подключиться к компоненту Database Engine** нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="05bdd-109">In the **Connect to Database Engine** dialog box, click **Cancel**.</span></span> <span data-ttu-id="05bdd-110">Будет открыт редактор запросов, в строке заголовка которого будет указано, что соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]не установлено.</span><span class="sxs-lookup"><span data-stu-id="05bdd-110">The Query Editor opens, and the title bar for the Query Editor indicates that you are not connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="05bdd-111">В панели кода введите следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="05bdd-111">In the code pane, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    SELECT * FROM Production.Product;  
    GO  
    ```  
  
     <span data-ttu-id="05bdd-112">На этом этапе можно подключиться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выбрав команды **Подключиться**, **Выполнить**, **Выполнить анализ**или **Показать предполагаемый план выполнения**, которые доступны в меню **Запрос** , на панели инструментов редактора запросов или в контекстном меню, открывающемся при щелчке правой кнопкой мыши в окне редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="05bdd-112">At this point you can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by clicking **Connect**, **Execute**, **Parse**, or **Display Estimated Execution Plan**, all of which are available from either the **Query** menu, the Query Editor toolbar, or from the shortcut menu when you right-click in the Query Editor window.</span></span> <span data-ttu-id="05bdd-113">В этом практическом занятии будет использована панель инструментов.</span><span class="sxs-lookup"><span data-stu-id="05bdd-113">For this practice, we'll use the toolbar.</span></span>  
  
4.  <span data-ttu-id="05bdd-114">На панели инструментов нажмите кнопку **Выполнить** , чтобы открыть диалоговое окно **Подключиться к компоненту Database Engine** .</span><span class="sxs-lookup"><span data-stu-id="05bdd-114">On the toolbar, click the **Execute** button to open the **Connect to Database Engine** dialog box.</span></span>  
  
5.  <span data-ttu-id="05bdd-115">В текстовом поле **Имя сервера** введите имя сервера, а затем нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="05bdd-115">In the **Server name** text box, type your server name, and then click **Options**.</span></span>  
  
6.  <span data-ttu-id="05bdd-116">На вкладке **Свойства соединения** в списке **Соединение с базой данных** найдите на сервере базу данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] и нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="05bdd-116">On the **Connection Properties** tab, in the **Connect to database** list, browse the server to select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="05bdd-117">Чтобы открыть другое окно редактора запросов для того же соединения, на панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="05bdd-117">To open another Query Editor window with the same connection, on the toolbar click **New Query**.</span></span>  
  
8.  <span data-ttu-id="05bdd-118">Чтобы сменить соединения, щелкните правой кнопкой мыши окно редактора запросов, наведите указатель на пункт **Соединение**и выберите команду **Изменить соединение**.</span><span class="sxs-lookup"><span data-stu-id="05bdd-118">To change connections, right-click in the Query Editor window, point to **Connection**, and then click **Change Connection**.</span></span>  
  
9. <span data-ttu-id="05bdd-119">В диалоговом окне **Подключение к SQL Server** выберите другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при его наличии, а затем нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="05bdd-119">In the **Connect to SQL Server** dialog box, select another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if available, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="05bdd-120">Эта новая возможность, предоставляемая редактором запросов, позволяет легко запускать один и тот же код на нескольких серверах.</span><span class="sxs-lookup"><span data-stu-id="05bdd-120">This new feature of Query Editor enables you to easily run the same code on several servers.</span></span> <span data-ttu-id="05bdd-121">Это может быть полезно при обслуживании нескольких схожих серверов.</span><span class="sxs-lookup"><span data-stu-id="05bdd-121">This may be useful for maintenance actions involving similar servers.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="05bdd-122">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="05bdd-122">Next Task in Lesson</span></span>  
 [<span data-ttu-id="05bdd-123">Добавление отступов</span><span class="sxs-lookup"><span data-stu-id="05bdd-123">Adding Indentation</span></span>](lesson-2-2-adding-indentation.md)  
  
  
