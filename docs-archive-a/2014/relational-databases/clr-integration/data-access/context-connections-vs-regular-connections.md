---
title: Обычные и контекстные соединения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
ms.openlocfilehash: ce531129099a8f4908bdc4b29920696d4ba3c505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668922"
---
# <a name="regular-vs-context-connections"></a><span data-ttu-id="e9000-102">Обычные и Контекстные соединения</span><span class="sxs-lookup"><span data-stu-id="e9000-102">Regular vs. Context Connections</span></span>
  <span data-ttu-id="e9000-103">При соединении с удаленным сервером всегда пользуйтесь обычными, а не контекстными соединениями.</span><span class="sxs-lookup"><span data-stu-id="e9000-103">If you are connecting to a remote server, always use regular connections rather than context connections.</span></span> <span data-ttu-id="e9000-104">Если нужно подключиться к тому же серверу, на котором выполняется хранимая процедура или функция, в большинстве случаев используется контекстное соединение.</span><span class="sxs-lookup"><span data-stu-id="e9000-104">If you need to connect to the same server on which the stored procedure or function is running, use the context connection in most cases.</span></span> <span data-ttu-id="e9000-105">Преимущества заключаются в выполнении приложений в одной области транзакций и отсутствии необходимости повторной проверки подлинности имени входа.</span><span class="sxs-lookup"><span data-stu-id="e9000-105">This has benefits such as running in the same transaction space and not having to reauthenticate.</span></span>  
  
 <span data-ttu-id="e9000-106">Кроме того, использование контекстного соединения обычно приводит к повышению производительности при меньшем потреблении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e9000-106">Additionally, using the context connection typically results in better performance and less resource usage.</span></span> <span data-ttu-id="e9000-107">Контекстное соединение является подключением только для обработки, поэтому оно может напрямую связаться с сервером, обходя сетевой протокол и транспортные уровни, чтобы отправлять инструкции Transact-SQL и получать результаты.</span><span class="sxs-lookup"><span data-stu-id="e9000-107">The context connection is an in-process-only connection, so it can contact the server "directly" by bypassing the network protocol and transport layers to send Transact-SQL statements and receive results.</span></span> <span data-ttu-id="e9000-108">Также обходится процесс проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e9000-108">The authentication process is bypassed, as well.</span></span> <span data-ttu-id="e9000-109">На следующем рисунке показаны основные компоненты управляемого поставщика `SqlClient`, а также взаимодействие разных компонентов друг с другом при использовании обычного и контекстного соединения.</span><span class="sxs-lookup"><span data-stu-id="e9000-109">The following figure shows the primary components of the `SqlClient` managed provider, as well as how the different components interact with each other when using a regular connection, and when using the context connection.</span></span>  
  
 <span data-ttu-id="e9000-110">![Кодовые пути контекстного и обычного соединений.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Кодовые пути контекстного и обычного соединений.")</span><span class="sxs-lookup"><span data-stu-id="e9000-110">![Code paths of a context and a regular connnection.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Code paths of a context and a regular connnection.")</span></span>  
  
 <span data-ttu-id="e9000-111">Контекстное соединение требует более короткого кода и меньшего числа компонентов, поэтому запрос к серверу, как и получение результатов, происходит быстрее, чем при обычном соединении.</span><span class="sxs-lookup"><span data-stu-id="e9000-111">The context connection follows a shorter code path and involves fewer components, so you can expect requests and results to get to and from the server faster than in a regular connection.</span></span> <span data-ttu-id="e9000-112">Время выполнение запроса на сервере остается одинаковым для контекстных и обычных соединений.</span><span class="sxs-lookup"><span data-stu-id="e9000-112">Query execution time on the server is the same for context and regular connections.</span></span>  
  
 <span data-ttu-id="e9000-113">В некоторых случаях, возможно, потребуется открыть отдельное обычное соединение с тем же сервером.</span><span class="sxs-lookup"><span data-stu-id="e9000-113">There are some cases in which you may need to open a separate regular connection to the same server.</span></span> <span data-ttu-id="e9000-114">Например, существуют определенные ограничения на использование контекстного соединения, описанные в разделе [ограничения для обычных и контекстных соединений](context-connections-and-regular-connections-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="e9000-114">For example, there are certain restrictions on using the context connection, described in [Restrictions on Regular and Context Connections](context-connections-and-regular-connections-restrictions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9000-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9000-115">See Also</span></span>  
 [<span data-ttu-id="e9000-116">Контекстное соединение</span><span class="sxs-lookup"><span data-stu-id="e9000-116">Context Connection</span></span>](context-connection.md)  
  
  
