---
title: Параметр конфигурации сервера "remote admin connections" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c17cf278d18444c5b93d4f4b7e0a3da8dbfb671e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667393"
---
# <a name="remote-admin-connections-server-configuration-option"></a><span data-ttu-id="7446c-102">Параметр конфигурации сервера «remote admin connections»</span><span class="sxs-lookup"><span data-stu-id="7446c-102">remote admin connections Server Configuration Option</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7446c-103">предоставляет выделенное административное соединение (DAC).</span><span class="sxs-lookup"><span data-stu-id="7446c-103">provides a dedicated administrator connection (DAC).</span></span> <span data-ttu-id="7446c-104">Такое подключение позволяет администратору получать доступ к серверу для выполнения диагностических функций или инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или решения проблем на сервере, даже когда сервер заблокирован или работает в аварийном состоянии и не отвечает на соединение компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7446c-104">The DAC lets an administrator access a running server to execute diagnostic functions or [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or to troubleshoot problems on the server, even when the server is locked or running in an abnormal state and not responding to a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] connection.</span></span> <span data-ttu-id="7446c-105">По умолчанию выделенные административные соединения доступны только с клиента на сервер.</span><span class="sxs-lookup"><span data-stu-id="7446c-105">By default, the DAC is only available from a client on the server.</span></span> <span data-ttu-id="7446c-106">Чтобы разрешить клиентским приложениям на удаленных компьютерах подключение DAC, используйте параметр remote admin connections хранимой процедуры sp_configure.</span><span class="sxs-lookup"><span data-stu-id="7446c-106">To enable client applications on remote computers to use the DAC, use the remote admin connections option of sp_configure.</span></span>  
  
 <span data-ttu-id="7446c-107">По умолчанию DAC ожидает соединения только на IP-адресе обратной связи (127.0.0.1), порт 1434.</span><span class="sxs-lookup"><span data-stu-id="7446c-107">By default, the DAC only listens on the loop-back IP address (127.0.0.1), port 1434.</span></span> <span data-ttu-id="7446c-108">Если TCP-порт 1434 недоступен, то TCP-порт динамически назначается при запуске компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7446c-108">If TCP port 1434 is not available, a TCP port is dynamically assigned when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts up.</span></span> <span data-ttu-id="7446c-109">Если на компьютере установлено более одного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо проверить номер TCP-порта в журнале ошибок.</span><span class="sxs-lookup"><span data-stu-id="7446c-109">When more than one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a computer, check the error log for the TCP port number.</span></span>  
  
 <span data-ttu-id="7446c-110">В следующей таблице приведены возможные значения параметра remote admin connections.</span><span class="sxs-lookup"><span data-stu-id="7446c-110">The following table lists the possible values for the remote admin connections option.</span></span>  
  
|<span data-ttu-id="7446c-111">Значение</span><span class="sxs-lookup"><span data-stu-id="7446c-111">Value</span></span>|<span data-ttu-id="7446c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7446c-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7446c-113">0</span><span class="sxs-lookup"><span data-stu-id="7446c-113">0</span></span>|<span data-ttu-id="7446c-114">Означает, что разрешены только локальные соединения через DAC.</span><span class="sxs-lookup"><span data-stu-id="7446c-114">Indicates only local connections are allowed by using the DAC.</span></span>|  
|<span data-ttu-id="7446c-115">1</span><span class="sxs-lookup"><span data-stu-id="7446c-115">1</span></span>|<span data-ttu-id="7446c-116">Означает, что разрешены удаленные соединения через DAC.</span><span class="sxs-lookup"><span data-stu-id="7446c-116">Indicates remote connections are allowed by using the DAC.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7446c-117">Пример</span><span class="sxs-lookup"><span data-stu-id="7446c-117">Example</span></span>  
 <span data-ttu-id="7446c-118">В следующем примере показано подключение через DAC с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="7446c-118">The following example enables the DAC from a remote computer.</span></span>  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7446c-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="7446c-119">See Also</span></span>  
 [<span data-ttu-id="7446c-120">Диагностическое соединение для администраторов баз данных</span><span class="sxs-lookup"><span data-stu-id="7446c-120">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
