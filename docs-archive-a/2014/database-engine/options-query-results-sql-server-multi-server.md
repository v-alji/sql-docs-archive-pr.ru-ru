---
title: Параметры (результаты запроса-SQL Server-Multi-Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8273ad5edc65dd7351533209e9fa670c49f75f7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736746"
---
# <a name="options-query-results-sql-server-multi-server"></a><span data-ttu-id="138ea-102">Параметры (страница "Результаты запроса/SQL Server/Многосерверные")</span><span class="sxs-lookup"><span data-stu-id="138ea-102">Options (Query Results-SQL Server-Multi-Server)</span></span>
  <span data-ttu-id="138ea-103">При одновременном выполнении запросов для нескольких серверов с помощью этой страницы можно указать параметры отображения результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="138ea-103">When you are querying multiple servers at the same time, use this page to specify the options for displaying result sets.</span></span> <span data-ttu-id="138ea-104">Слияние результатов объединяет результирующие наборы всех серверов в единый результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="138ea-104">Merge results combines the result sets from all servers into a single result set.</span></span> <span data-ttu-id="138ea-105">При объединении результатов первый ответивший сервер устанавливает схему результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="138ea-105">When merging results, the first server to respond sets the schema for the result set.</span></span> <span data-ttu-id="138ea-106">Для объединения результирующих наборов запрос должен вернуть одинаковое число столбцов с одинаковыми для каждого сервера именами.</span><span class="sxs-lookup"><span data-stu-id="138ea-106">To merge the result sets, the query must return the same number of columns with the same column names from each server.</span></span> <span data-ttu-id="138ea-107">При слиянии результатов будет выведено сообщение для каждого сервера, результаты которого не совпадают со схемой (количество и имена столбцов), возвращенной первым сервером, возвратившим результаты.</span><span class="sxs-lookup"><span data-stu-id="138ea-107">When merging results, a message is displayed for each server that does not match the schema (column count and column names) that is returned by the first server to return results.</span></span>  
  
 <span data-ttu-id="138ea-108">Если слияние результатов не выполняется, результирующий набор каждого сервера будет отображен в своей собственной сетке со своей собственной схемой.</span><span class="sxs-lookup"><span data-stu-id="138ea-108">When you do not merge results, the result set from each server will be displayed in its own grid with its own schema.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="138ea-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="138ea-109">UI element list</span></span>  
 <span data-ttu-id="138ea-110">**Произвести слияние результатов**</span><span class="sxs-lookup"><span data-stu-id="138ea-110">**Merge results**</span></span>  
 <span data-ttu-id="138ea-111">Установите данный флажок, чтобы объединить результирующие наборы нескольких серверов в одну сетку.</span><span class="sxs-lookup"><span data-stu-id="138ea-111">Select this check box to combine the result sets from several servers into the same grid.</span></span>  
  
 <span data-ttu-id="138ea-112">**Добавить к результатам имя сервера**</span><span class="sxs-lookup"><span data-stu-id="138ea-112">**Add server name to the results**</span></span>  
 <span data-ttu-id="138ea-113">Установите данный флажок, чтобы включить дополнительный столбец, в котором указывается имя сервера, вернувшего каждую из строк.</span><span class="sxs-lookup"><span data-stu-id="138ea-113">Select this check box to include an additional column that provides the name of the server that produced each row.</span></span>  
  
 <span data-ttu-id="138ea-114">**Добавить имя входа к результатам**</span><span class="sxs-lookup"><span data-stu-id="138ea-114">**Add login name to the results**</span></span>  
 <span data-ttu-id="138ea-115">Установите данный флажок, чтобы включить дополнительный столбец, в котором указывается имя входа, использованное для подключения к серверу, предоставившему каждую из строк.</span><span class="sxs-lookup"><span data-stu-id="138ea-115">Select this check box to include an additional column that provides the login that was used to connect to the server that provided each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138ea-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="138ea-116">See Also</span></span>  
 <span data-ttu-id="138ea-117">[Создание сервера централизованного управления и группы серверов &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span><span class="sxs-lookup"><span data-stu-id="138ea-117">[Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span></span>  
 [<span data-ttu-id="138ea-118">Выполнение инструкции на нескольких серверах одновременно (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="138ea-118">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
