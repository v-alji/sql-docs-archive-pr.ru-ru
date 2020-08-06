---
title: Настройка сервера для прослушивания альтернативного канала (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Named Pipes [SQL Server], configuring
- listening [SQL Server], pipes
- pipes [SQL Server], alternate
- alternate pipes [SQL Server]
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 57d70cf4cd1d7474b895aeb8cb144c885e8a0f99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655360"
---
# <a name="configure-a-server-to-listen-on-an-alternate-pipe-sql-server-configuration-manager"></a><span data-ttu-id="9d9d0-102">Настройка сервера для прослушивания альтернативного канала (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-102">Configure a Server to Listen on an Alternate Pipe (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="9d9d0-103">В этом разделе описан процесс настройки сервера на прослушивание другого канала в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-103">This topic describes how to configure a server to listen on an alternate pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="9d9d0-104">По умолчанию неименованный экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] прослушивает именованный канал \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-104">By default, the default instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on named pipe \\\\.\pipe\sql\query.</span></span> <span data-ttu-id="9d9d0-105">Именованные экземпляры компонентов [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и [!INCLUDE[ssEW](../../includes/ssew-md.md)] настроены на прослушивание других каналов.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-105">Named instances of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] listen on other pipes.</span></span>  
  
 <span data-ttu-id="9d9d0-106">Клиентское приложение можно подключить к конкретному именованному каналу тремя способами:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-106">There are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="9d9d0-107">запустив на сервере службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="9d9d0-107">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="9d9d0-108">создав псевдоним клиента с указанием именованного канала;</span><span class="sxs-lookup"><span data-stu-id="9d9d0-108">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="9d9d0-109">Настройте клиент на использование пользовательской строки подключения.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-109">Program the client to connect using a custom connection string.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9d9d0-110">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d9d0-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-the-named-pipe-used-by-the-sql-server-database-engine"></a><span data-ttu-id="9d9d0-111">Настройка именованного канала, используемого компонентом SQL Server Database Engine</span><span class="sxs-lookup"><span data-stu-id="9d9d0-111">To configure the named pipe used by the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="9d9d0-112">В области консоли диспетчера конфигурации SQL Server разверните узел **Сетевая конфигурация SQL Server**, а затем **Протоколы для** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="9d9d0-112">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, and then click expand **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="9d9d0-113">В области сведений щелкните правой кнопкой мыши **Именованные каналы**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-113">In the details pane, right-click **Named Pipes**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9d9d0-114">На вкладке **Протоколы** в поле **Имя канала** укажите канал, который должен прослушиваться компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-114">On the **Protocol** tab, in the **Pipe Name** box, type the pipe you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9d9d0-115">В области консоли выберите **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-115">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="9d9d0-116">В области сведений щелкните правой кнопкой мыши **SQL Server (** \<instance name> **)** и выберите команду **Перезапустить**, чтобы остановить и снова запустить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d9d0-116">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9d9d0-117">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прослушивает альтернативный канал, то подключить клиентское приложение к конкретному именованному каналу можно тремя способами:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-117">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on an alternate pipe, there are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="9d9d0-118">запустив на сервере службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="9d9d0-118">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="9d9d0-119">создав псевдоним клиента с указанием именованного канала;</span><span class="sxs-lookup"><span data-stu-id="9d9d0-119">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="9d9d0-120">Настройте клиент на использование пользовательской строки подключения.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-120">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9d0-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-121">See Also</span></span>  
 <span data-ttu-id="9d9d0-122">[Создание или удаление псевдонима сервера для использования клиентом (диспетчер конфигурации SQL Server)](create-or-delete-a-server-alias-for-use-by-a-client.md) </span><span class="sxs-lookup"><span data-stu-id="9d9d0-122">[Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span></span>  
 [<span data-ttu-id="9d9d0-123">Сетевая конфигурация сервера</span><span class="sxs-lookup"><span data-stu-id="9d9d0-123">Server Network Configuration</span></span>](server-network-configuration.md)  
  
  
