---
title: Связь запроса с подключением в проекте | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], query associations
- projects [SQL Server Management Studio], connections
- projects [SQL Server Management Studio], query connections
- query associations [SQL Server Management Studio]
ms.assetid: c9625ae0-29c1-4179-a709-51b7e2f9e23d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b05715dc6680148a8ae673c73cfc36c96a55c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733433"
---
# <a name="associate-a-query-with-a-connection-in-a-project"></a><span data-ttu-id="0671b-102">Связь запроса с соединением в проекте</span><span class="sxs-lookup"><span data-stu-id="0671b-102">Associate a Query with a Connection in a Project</span></span>
  <span data-ttu-id="0671b-103">Если запрос был создан без соединения или если запрос был перемещен из одного проекта в другой, он не будет связан с соединением в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="0671b-103">If a query was created without a connection, or if a query is moved from one project to another it will not be associated with a connection in the current project.</span></span>  
  
### <a name="to-associate-a-query-with-a-connection-in-a-project"></a><span data-ttu-id="0671b-104">Связывание запроса с соединением в проекте</span><span class="sxs-lookup"><span data-stu-id="0671b-104">To associate a query with a connection in a project</span></span>  
  
1.  <span data-ttu-id="0671b-105">Если запрос открыт в редакторе запросов, щелкните правой кнопкой мыши в пустой области редактора запросов и в контекстном меню укажите **Соединение**, а затем **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="0671b-105">If the query is open in query editor, right-click a blank area of query editor, point to **Connection**, and then click **Connect**.</span></span> <span data-ttu-id="0671b-106">Если запрос не открыт, для соединения запроса дважды щелкните запрос в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="0671b-106">If the query is not open, double-click the query in Solution Explorer to connect the query.</span></span>  
  
2.  <span data-ttu-id="0671b-107">В диалоговом окне **Подключиться к ядру СУБД** введите сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="0671b-107">In the **Connect to Database Engine** dialog box, provide the connection information.</span></span> <span data-ttu-id="0671b-108">Если они совпадут с существующим соединением, запрос будет связан с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="0671b-108">If the connection information matches an existing connection, the query will be associated with that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0671b-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="0671b-109">See Also</span></span>  
 <span data-ttu-id="0671b-110">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="0671b-110">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="0671b-111">[Изменение соединения, связанного с запросом](change-the-connection-associated-with-a-query.md) </span><span class="sxs-lookup"><span data-stu-id="0671b-111">[Change the Connection Associated with a Query](change-the-connection-associated-with-a-query.md) </span></span>  
 [<span data-ttu-id="0671b-112">Просмотр или изменение свойств соединения в проекте</span><span class="sxs-lookup"><span data-stu-id="0671b-112">View or Change the Properties of a Connection in a Project</span></span>](view-or-change-the-properties-of-a-connection-in-a-project.md)  
  
  
