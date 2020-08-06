---
title: Создание допустимой строки подключения с использованием протокола общей памяти | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca97332a09a33fcfc15a3dbb2599af27dbe0e1db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727697"
---
# <a name="creating-a-valid-connection-string-using-shared-memory-protocol"></a><span data-ttu-id="4841f-102">Создание допустимой строки соединения с использованием протокола общей памяти</span><span class="sxs-lookup"><span data-stu-id="4841f-102">Creating a Valid Connection String Using Shared Memory Protocol</span></span>
  <span data-ttu-id="4841f-103">при подключении к [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с клиента, запущенного на том же компьютере, используется протокол общей памяти.</span><span class="sxs-lookup"><span data-stu-id="4841f-103">Connections to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client running on the same computer use the shared memory protocol.</span></span> <span data-ttu-id="4841f-104">У общей памяти нет настраиваемых свойств.</span><span class="sxs-lookup"><span data-stu-id="4841f-104">Shared memory has no configurable properties.</span></span> <span data-ttu-id="4841f-105">Протокол общей памяти всегда используется первым и его нельзя переместить с верхней строчки списка **Включенные протоколы** окна **Свойства клиентских протоколов** .</span><span class="sxs-lookup"><span data-stu-id="4841f-105">Shared memory is always tried first, and cannot be moved from the top position of the **Enabled Protocols** list in the **Client Protocols Properties** list.</span></span> <span data-ttu-id="4841f-106">Протокол общей памяти может быть отключен, что бывает полезным при устранении неполадок в одном из других протоколов.</span><span class="sxs-lookup"><span data-stu-id="4841f-106">The Shared Memory protocol can be disabled, which is useful when troubleshooting one of the other protocols.</span></span>  
  
 <span data-ttu-id="4841f-107">При помощи протокола общей памяти нельзя создать псевдоним, но если протокол общей памяти включен, то во время подключения к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] по имени создается соединение общей памяти.</span><span class="sxs-lookup"><span data-stu-id="4841f-107">You cannot create an alias using the shared memory protocol, but if shared memory is enabled, then connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by name, creates a shared memory connection.</span></span> <span data-ttu-id="4841f-108">В строке подключения общей памяти используется формат `lpc:<servername>[\instancename]`.</span><span class="sxs-lookup"><span data-stu-id="4841f-108">A shared memory connection string uses the format `lpc:<servername>[\instancename]`.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="4841f-109">Подключение к локальному серверу</span><span class="sxs-lookup"><span data-stu-id="4841f-109">Connecting to the Local Server</span></span>  
 <span data-ttu-id="4841f-110">При подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запущенному на том же компьютере, что и клиент, в качестве имени сервера можно использовать **(local)** .</span><span class="sxs-lookup"><span data-stu-id="4841f-110">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use **(local)** as the server name.</span></span> <span data-ttu-id="4841f-111">Это действие не рекомендуется, поскольку может вызвать неоднозначность, но может быть полезным, если известно, что клиент запущен на нужном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4841f-111">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="4841f-112">Например, при создании приложения для мобильных отключенных пользователей, таких как торговый персонал, когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет запускаться на переносных компьютерах и использоваться для хранения данных проекта, клиент, подключающийся к **(local)** , будет всегда подключаться к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполняющемуся на переносном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4841f-112">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to **(local)** would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="4841f-113">Вместо **(local)** можно использовать слово**localhost**или точку ( **.** ).</span><span class="sxs-lookup"><span data-stu-id="4841f-113">The word **localhost** or a period (**.**) can be used in place of **(local)**.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="4841f-114">Проверка протокола соединения</span><span class="sxs-lookup"><span data-stu-id="4841f-114">Verifying your Connection Protocol</span></span>  
 <span data-ttu-id="4841f-115">Следующий запрос возвратит протокол, используемый в текущем соединении.</span><span class="sxs-lookup"><span data-stu-id="4841f-115">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="4841f-116">Примеры:</span><span class="sxs-lookup"><span data-stu-id="4841f-116">Examples:</span></span>  
 <span data-ttu-id="4841f-117">Следующие имена будут подключаться к локальному компьютеру при помощи протокола общей памяти, если он включен:</span><span class="sxs-lookup"><span data-stu-id="4841f-117">The following names will connect to the local computer with the shared memory protocol if it is enabled:</span></span>  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 <span data-ttu-id="4841f-118">Невозможно создать псевдоним для соединения по протоколу общей памяти.</span><span class="sxs-lookup"><span data-stu-id="4841f-118">You cannot create an alias for a shared memory connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4841f-119">При указании IP-адреса в поле **Сервер** будет установлено соединение TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="4841f-119">Specifying an IP Address in the **Server** box will result in a TCP/IP connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4841f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4841f-120">See Also</span></span>  
 <span data-ttu-id="4841f-121">[Создание допустимой строки подключения с использованием протокола TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="4841f-121">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 <span data-ttu-id="4841f-122">[Создание допустимой строки подключения, использующей протокол именованных каналов](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="4841f-122">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="4841f-123">Выбор сетевого протокола</span><span class="sxs-lookup"><span data-stu-id="4841f-123">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
