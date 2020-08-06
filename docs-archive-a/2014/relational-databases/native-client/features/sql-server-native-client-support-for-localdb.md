---
title: Поддержка SQL Server Native Client для LocalDB | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
author: rothja
ms.author: jroth
ms.openlocfilehash: b08ea46e8db1b665280116a439b95748f69d03ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657074"
---
# <a name="sql-server-native-client-support-for-localdb"></a><span data-ttu-id="d57e5-102">Поддержка SQL Server Native Client для LocalDB</span><span class="sxs-lookup"><span data-stu-id="d57e5-102">SQL Server Native Client Support for LocalDB</span></span>
  <span data-ttu-id="d57e5-103">Начиная с версии [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], будет доступна облегченная версия SQL Server, называемая LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d57e5-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="d57e5-104">В этом разделе обсуждается, как можно установить соединение с базой данных на экземпляре LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d57e5-104">This topic discusses how to connect to a database in a LocalDB instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d57e5-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="d57e5-105">Remarks</span></span>  
 <span data-ttu-id="d57e5-106">Дополнительные сведения о LocalDB, включая способы его установки и настройки, см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="d57e5-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see:</span></span>  
  
-   [<span data-ttu-id="d57e5-107">Справочник по SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="d57e5-107">SQL Server Express LocalDB Reference</span></span>](../../sql-server-express-localdb-reference.md)  
  
-   [<span data-ttu-id="d57e5-108">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="d57e5-108">SQL Server 2014 Express LocalDB</span></span>](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 <span data-ttu-id="d57e5-109">LocalDB позволяет выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d57e5-109">To summarize, LocalDB allows you to:</span></span>  
  
-   <span data-ttu-id="d57e5-110">Использовать программу `sqllocaldb.exe i` для поиска имени экземпляра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d57e5-110">Use `sqllocaldb.exe i` to discover the name of the default instance.</span></span>  
  
-   <span data-ttu-id="d57e5-111">Использовать ключевое слово строки подключения `AttachDBFilename` для указания файла базы данных, который сервер должен присоединить.</span><span class="sxs-lookup"><span data-stu-id="d57e5-111">Use the `AttachDBFilename` connection string keyword to specify which database file the server should attach.</span></span> <span data-ttu-id="d57e5-112">Если при использовании `AttachDBFilename` ключевого слова строки подключения к **базе данных** не указано имя базы данных, то при закрытии приложения база данных будет удалена из экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d57e5-112">When using `AttachDBFilename`, if you do not specify the name of the database with the **Database** connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="d57e5-113">Чтобы указать экземпляр LocalDB в строке подключения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d57e5-113">Specify a LocalDB instance in your connection string:</span></span>  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 <span data-ttu-id="d57e5-114">При необходимости можно создать экземпляр LocalDB с помощью программы sqllocaldb.exe.</span><span class="sxs-lookup"><span data-stu-id="d57e5-114">If necessary, you can create a LocalDB instance with sqllocaldb.exe.</span></span> <span data-ttu-id="d57e5-115">Для добавления и изменения баз данных в локальном экземпляре LocalDB можно также воспользоваться программой sqlcmd.exe.</span><span class="sxs-lookup"><span data-stu-id="d57e5-115">You can also use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="d57e5-116">Например, `sqlcmd -S (localdb)\v11.0`.</span><span class="sxs-lookup"><span data-stu-id="d57e5-116">For example, `sqlcmd -S (localdb)\v11.0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d57e5-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="d57e5-117">See Also</span></span>  
 [<span data-ttu-id="d57e5-118">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d57e5-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
