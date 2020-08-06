---
title: Отмена команд (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 003c70362c38ae1838b4679abf6485fa031a9143
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728901"
---
# <a name="canceling-commands-xmla"></a><span data-ttu-id="f107f-102">Отмена команд (XMLA)</span><span class="sxs-lookup"><span data-stu-id="f107f-102">Canceling Commands (XMLA)</span></span>
  <span data-ttu-id="f107f-103">В зависимости от административных разрешений пользователя, выполняющего команду, команда [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) в XML для АНАЛИТИКИ (XMLA) может отменить команду в сеансе, сеансе, подключении, серверном процессе или связанном сеансе или соединении.</span><span class="sxs-lookup"><span data-stu-id="f107f-103">Depending on the administrative permissions of the user issuing the command, the [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.</span></span>  
  
## <a name="canceling-commands"></a><span data-ttu-id="f107f-104">Отмена команд</span><span class="sxs-lookup"><span data-stu-id="f107f-104">Canceling Commands</span></span>  
 <span data-ttu-id="f107f-105">Пользователь может отменить выполняемую в данный момент команду в контексте текущего явного сеанса, отправив команду `Cancel` без указания свойств.</span><span class="sxs-lookup"><span data-stu-id="f107f-105">A user can cancel the currently executing command within the context of the current explicit session by sending a `Cancel` command with no specified properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f107f-106">Пользователь не может отменить команду, выполняющуюся в рамках неявного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f107f-106">A command running in an implicit session cannot be canceled by a user.</span></span>  
  
### <a name="canceling-batch-commands"></a><span data-ttu-id="f107f-107">Отмена пакетов команд</span><span class="sxs-lookup"><span data-stu-id="f107f-107">Canceling Batch Commands</span></span>  
 <span data-ttu-id="f107f-108">Если пользователь отменяет команду `Batch`, то отменяются все остальные команды в рамках команды `Batch`, выполнение которых еще не завершено.</span><span class="sxs-lookup"><span data-stu-id="f107f-108">If a user cancels a `Batch` command, then all remaining commands not yet executed within the `Batch` command are canceled.</span></span> <span data-ttu-id="f107f-109">Если команда `Batch` входила в состав транзакции, то происходит откат всех команд, которые выполнялись до запуска команды `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="f107f-109">If the `Batch` command was transactional, any commands that were executed before the `Cancel` command runs are rolled back.</span></span>  
  
## <a name="canceling-sessions"></a><span data-ttu-id="f107f-110">Отмена сеансов</span><span class="sxs-lookup"><span data-stu-id="f107f-110">Canceling Sessions</span></span>  
 <span data-ttu-id="f107f-111">Указав идентификатор сеанса для явного сеанса в свойстве [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) `Cancel` команды, администратор базы данных или администратор сервера может отменить сеанс, включая выполняемую в данный момент команду.</span><span class="sxs-lookup"><span data-stu-id="f107f-111">By specifying a session identifier for an explicit session in the [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a database administrator or server administrator can cancel a session, including the currently executing command.</span></span> <span data-ttu-id="f107f-112">Администратор баз данных может отменять сеансы только для тех баз данных, на которые у него есть разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="f107f-112">A database administrator can only cancel sessions for databases on which he or she has administrative permissions.</span></span>  
  
 <span data-ttu-id="f107f-113">Администратор базы данных может извлекать сведения об активных сеансах для указанной базы данных путем извлечения набора строк схемы DISCOVER_SESSIONS.</span><span class="sxs-lookup"><span data-stu-id="f107f-113">A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset.</span></span> <span data-ttu-id="f107f-114">Для получения набора строк схемы DISCOVER_SESSIONS администратор базы данных использует `Discover` метод XMLA и указывает соответствующий идентификатор базы данных для столбца ограничений SESSION_CURRENT_DATABASE в свойстве restriction [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) `Discover` метода.</span><span class="sxs-lookup"><span data-stu-id="f107f-114">To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA `Discover` method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) property of the `Discover` method.</span></span>  
  
## <a name="canceling-connections"></a><span data-ttu-id="f107f-115">Отмена соединений</span><span class="sxs-lookup"><span data-stu-id="f107f-115">Canceling Connections</span></span>  
 <span data-ttu-id="f107f-116">Указав идентификатор соединения в свойстве [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) `Cancel` команды, администратор сервера может отменить все сеансы, связанные с данным подключением, включая все выполняющиеся команды, и отменить подключение.</span><span class="sxs-lookup"><span data-stu-id="f107f-116">By specifying a connection identifier in the [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) property of the `Cancel` command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f107f-117">Если экземпляр [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не может располагать и отменять сеансы, связанные с соединением, например, когда в конвейере данных открывается несколько сеансов и предоставляется возможность подключения по протоколу HTTP, экземпляр не может отменить подключение.</span><span class="sxs-lookup"><span data-stu-id="f107f-117">If the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection.</span></span> <span data-ttu-id="f107f-118">Если такая ситуация возникает во время выполнения команды `Cancel`, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="f107f-118">If this case is encountered during the execution of a `Cancel` command, an error occurs.</span></span>  
  
 <span data-ttu-id="f107f-119">Администратор сервера может извлекать сведения об активных соединениях для экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] путем извлечения набора строк схемы DISCOVER_CONNECTIONS при помощи метода XMLA `Discover`.</span><span class="sxs-lookup"><span data-stu-id="f107f-119">A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA `Discover` method.</span></span>  
  
## <a name="canceling-server-processes"></a><span data-ttu-id="f107f-120">Отмена процессов сервера</span><span class="sxs-lookup"><span data-stu-id="f107f-120">Canceling Server Processes</span></span>  
 <span data-ttu-id="f107f-121">Указав идентификатор серверного процесса (SPID) в свойстве [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) `Cancel` команды, администратор сервера может отменить команды, связанные с данным идентификатором SPID.</span><span class="sxs-lookup"><span data-stu-id="f107f-121">By specifying a server process identifier (SPID) in the [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a server administrator can cancel the commands associated with a given SPID.</span></span>  
  
## <a name="canceling-associated-sessions-and-connections"></a><span data-ttu-id="f107f-122">Отмена ассоциированных сеансов и соединений</span><span class="sxs-lookup"><span data-stu-id="f107f-122">Canceling Associated Sessions and Connections</span></span>  
 <span data-ttu-id="f107f-123">Можно задать для свойства [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) значение true, чтобы отменить соединения, сеансы и команды, связанные с соединением, сеансом или SPID, указанными в `Cancel` команде.</span><span class="sxs-lookup"><span data-stu-id="f107f-123">You can set the [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the `Cancel` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f107f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f107f-124">See Also</span></span>  
 <span data-ttu-id="f107f-125">[Метод Discover &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span><span class="sxs-lookup"><span data-stu-id="f107f-125">[Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span></span>  
 [<span data-ttu-id="f107f-126">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f107f-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
