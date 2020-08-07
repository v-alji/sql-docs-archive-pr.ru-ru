---
title: Отключить пользователей и сеансы на Analysis Services сервере | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: bac20b663b0a65902c70e7a3c3bfe3f27b7bf061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731069"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a><span data-ttu-id="5cd43-102">Отключение пользователей и сеансов на сервере служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5cd43-102">Disconnect Users and Sessions on Analysis Services Server</span></span>
  <span data-ttu-id="5cd43-103">Администратору служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] может понадобиться завершить пользовательские операции в процессе управления рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="5cd43-103">An administrator of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] may want to end user activity as part of workload management.</span></span> <span data-ttu-id="5cd43-104">Это производится путем отмены сеансов и соединений.</span><span class="sxs-lookup"><span data-stu-id="5cd43-104">You do this by canceling sessions and connections.</span></span> <span data-ttu-id="5cd43-105">Сеансы могут формироваться автоматически при запуске запроса (неявно) или именоваться в момент создания администратором (явно).</span><span class="sxs-lookup"><span data-stu-id="5cd43-105">Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit).</span></span> <span data-ttu-id="5cd43-106">Соединения представляют собой открытые каналы, по которым запускаются запросы.</span><span class="sxs-lookup"><span data-stu-id="5cd43-106">Connections are open conduits over which queries can be run.</span></span> <span data-ttu-id="5cd43-107">Как сеансы, так и соединения можно завершать, пока они активны.</span><span class="sxs-lookup"><span data-stu-id="5cd43-107">Both sessions and connections can be ended while they are active.</span></span> <span data-ttu-id="5cd43-108">Например, администратору может потребоваться прекратить обработку для сеанса, если эта обработка продолжается слишком долго или возникли сомнения в правильности написания выполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="5cd43-108">For example, an administrator may want to end processing for a session if the processing is taking too long or if some doubt has arisen as to whether the command being executed was written correctly.</span></span>  
  
## <a name="ending-sessions-and-connections"></a><span data-ttu-id="5cd43-109">Завершение сеансов и соединений</span><span class="sxs-lookup"><span data-stu-id="5cd43-109">Ending Sessions and Connections</span></span>  
 <span data-ttu-id="5cd43-110">Для управления сеансами и соединениями можно использовать динамические административные представления (DMV) и XML для аналитики (XMLA):</span><span class="sxs-lookup"><span data-stu-id="5cd43-110">To manage sessions and connections, you can use Dynamic Management Views (DMVs) and XMLA:</span></span>  
  
1.  <span data-ttu-id="5cd43-111">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5cd43-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="5cd43-112">Вставьте один из следующих запросов к динамическим административным представлениям (DMV) в окно запроса MDX, чтобы получить список всех активных в настоящее время сеансов, соединений и выполняющихся команд.</span><span class="sxs-lookup"><span data-stu-id="5cd43-112">Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:</span></span>  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  <span data-ttu-id="5cd43-113">Нажмите клавишу F5, чтобы выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="5cd43-113">Press F5 to execute the query.</span></span>  
  
     <span data-ttu-id="5cd43-114">Запрос DMV возвращает информацию о сеансе и соединении в виде табличного результирующего набора, что облегчает ее чтение и копирование.</span><span class="sxs-lookup"><span data-stu-id="5cd43-114">The DMV query returns session and connection information in a tabular result set that is easier read and copy from.</span></span>  
  
 <span data-ttu-id="5cd43-115">Не закрывайте окно запроса.</span><span class="sxs-lookup"><span data-stu-id="5cd43-115">Keep the query window open.</span></span> <span data-ttu-id="5cd43-116">На следующем этапе вам может понадобиться вернуться на эту страницу, чтобы скопировать SPID сеанса, который требуется отключить.</span><span class="sxs-lookup"><span data-stu-id="5cd43-116">In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.</span></span>  
  
 <span data-ttu-id="5cd43-117">Чтобы завершить сеанс, откройте второе окно запроса XML для аналитики (XMLA).</span><span class="sxs-lookup"><span data-stu-id="5cd43-117">To end a session, open a second XMLA query window.</span></span>  
  
1.  <span data-ttu-id="5cd43-118">Вставьте следующий синтаксис в окне запроса MDX, заменив заполнители ConnectionID, SessionID или SPID на допустимые значения, скопированные из предыдущего этапа.</span><span class="sxs-lookup"><span data-stu-id="5cd43-118">Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.</span></span>  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  <span data-ttu-id="5cd43-119">Нажмите клавишу F5, чтобы выполнить команду отмены.</span><span class="sxs-lookup"><span data-stu-id="5cd43-119">Press F5 to execute the cancel command.</span></span>  
  
 <span data-ttu-id="5cd43-120">При закрытии соединения отменяются все сеансы и SPID, закрывая сеанс узла.</span><span class="sxs-lookup"><span data-stu-id="5cd43-120">Ending a connection cancels all sessions and SPIDs, closing the host session.</span></span>  
  
 <span data-ttu-id="5cd43-121">Завершение сеанса останавливает все команды (SPID), которые выполняются в рамках этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="5cd43-121">Ending a session stops all commands (SPIDs) that are running as part of that session.</span></span>  
  
 <span data-ttu-id="5cd43-122">Завершение SPID отменяет определенную оценку.</span><span class="sxs-lookup"><span data-stu-id="5cd43-122">Ending a SPID cancels a particular commend.</span></span>  
  
 <span data-ttu-id="5cd43-123">В редких случаях [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не закроет сеанс, если не сможет отследить все сеансы и SPID, связанные с соединением (например, когда несколько сеансов открыто в сценарии HTTP).</span><span class="sxs-lookup"><span data-stu-id="5cd43-123">In rare cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will not close a connection if it cannot track all the sessions and SPIDs associated with the connection (for example, when multiple sessions are open in an HTTP scenario).</span></span>  
  
 <span data-ttu-id="5cd43-124">Дополнительную информацию о XMLA, упомянутом в данном разделе, см. в разделах [Метод Execute (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) и [Элемент Cancel (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="5cd43-124">For more information about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) and [Cancel Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd43-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="5cd43-125">See Also</span></span>  
 <span data-ttu-id="5cd43-126">[Управление подключениями и сеансами &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="5cd43-126">[Managing Connections and Sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span></span>  
 <span data-ttu-id="5cd43-127">[Элемент BeginSession &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="5cd43-127">[BeginSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span></span>  
 <span data-ttu-id="5cd43-128">[Элемент EndSession &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="5cd43-128">[EndSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span></span>  
 [<span data-ttu-id="5cd43-129">Элемент Session (XMLA)</span><span class="sxs-lookup"><span data-stu-id="5cd43-129">Session Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
