---
title: Свойства клиентских протоколов (вкладка «порядок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729969"
---
# <a name="client-protocols-properties-order-tab"></a><span data-ttu-id="c892f-102">Свойства клиентских протоколов (вкладка «Порядок»)</span><span class="sxs-lookup"><span data-stu-id="c892f-102">Client Protocols Properties (Order Tab)</span></span>
  <span data-ttu-id="c892f-103">Используйте страницу **Порядок**диалогового окна **Свойства клиентских протоколов** для просмотра и включения клиентских протоколов.</span><span class="sxs-lookup"><span data-stu-id="c892f-103">Use the **Order**page on the **Client Protocols Properties** dialog box to view and enable the client protocols.</span></span>  
  
 <span data-ttu-id="c892f-104">Щелкните протокол, а затем выберите команду **Включить** или **Выключить** для перемещения выбранного протокола в список **Отключенные протоколы** или **Включенные протоколы** .</span><span class="sxs-lookup"><span data-stu-id="c892f-104">Click a protocol, and then click **Enable** or **Disable** to move the selected protocol to the **Disabled Protocols** or **Enabled Protocols** list.</span></span>  
  
 <span data-ttu-id="c892f-105">Попытки использования протоколов происходят в перечисленной в списке последовательности: сначала осуществляется попытка соединения при помощи самого верхнего протокола, затем при помощи протокола, второго в списке, и так далее. Передвигать протоколы вверх и вниз по списку **Включенные протоколы** можно, нажимая кнопки со стрелкой вверх и со стрелкой вниз.</span><span class="sxs-lookup"><span data-stu-id="c892f-105">Protocols are tried in the order listed, attempting to connect using the top protocol first, and then the second listed protocol, etc. Move protocols up or down the **Enabled Protocols** list, by clicking the up arrow and down arrow buttons.</span></span> <span data-ttu-id="c892f-106">При подключении к [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из клиента на том же компьютере в первую очередь происходит попытка подключения через протокол **Shared Memory** (Общая память), если он включен.</span><span class="sxs-lookup"><span data-stu-id="c892f-106">When connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer, the **Shared Memory** protocol will always be tried first, if enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c892f-107">Эти настройки не используются клиентом [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span><span class="sxs-lookup"><span data-stu-id="c892f-107">These settings are not used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span></span> <span data-ttu-id="c892f-108">В порядке протоколов для клиента .NET SqlClient первым идет протокол TCP, а затем именованные каналы. Этот порядок нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="c892f-108">The protocol order for .NET SqlClient is first TCP, and then named pipes, which cannot be changed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c892f-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="c892f-109">Options</span></span>  
 <span data-ttu-id="c892f-110">**Отключенные протоколы**</span><span class="sxs-lookup"><span data-stu-id="c892f-110">**Disabled Protocols**</span></span>  
 <span data-ttu-id="c892f-111">Содержит список установленных, но не используемых в данный момент протоколов.</span><span class="sxs-lookup"><span data-stu-id="c892f-111">Lists protocols which are installed but are not currently used.</span></span>  
  
 <span data-ttu-id="c892f-112">**Включенные протоколы**</span><span class="sxs-lookup"><span data-stu-id="c892f-112">**Enabled Protocols**</span></span>  
 <span data-ttu-id="c892f-113">Список протоколов, доступных для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] клиентов на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="c892f-113">Lists protocols which are available for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this computer.</span></span>  
  
 **>**  
 <span data-ttu-id="c892f-114">Включает выделенный протокол в окне **Отключенные протоколы** и переносит его в окно **Включенные протоколы** .</span><span class="sxs-lookup"><span data-stu-id="c892f-114">Enables the currently highlighted protocol in the **Disabled Protocols** box, moving it to the **Enabled Protocols** box.</span></span>  
  
 **\<**  
 <span data-ttu-id="c892f-115">Отключает выделенный протокол в окне **Включенные протоколы** и переносит его в окно **Отключенные протоколы** .</span><span class="sxs-lookup"><span data-stu-id="c892f-115">Disables the currently highlighted protocol in the **Enabled Protocols** box, moving it to the **Disabled Protocols** box.</span></span>  
  
 <span data-ttu-id="c892f-116">Стрелка вверх</span><span class="sxs-lookup"><span data-stu-id="c892f-116">Up arrow</span></span>  
 <span data-ttu-id="c892f-117">Перемещает выделенный протокол вверх по списку.</span><span class="sxs-lookup"><span data-stu-id="c892f-117">Moves the highlighted protocol up in the list.</span></span> <span data-ttu-id="c892f-118">Это позволяет повысить приоритет использования сетевой библиотекой выбранного протокола для соединений.</span><span class="sxs-lookup"><span data-stu-id="c892f-118">This allows you to increase the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="c892f-119">Стрелка вниз</span><span class="sxs-lookup"><span data-stu-id="c892f-119">Down arrow</span></span>  
 <span data-ttu-id="c892f-120">Перемещает выделенный протокол вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="c892f-120">Moves the highlighted protocol down in the list.</span></span> <span data-ttu-id="c892f-121">Это позволяет понизить приоритет использования сетевой библиотекой выбранного протокола для соединений.</span><span class="sxs-lookup"><span data-stu-id="c892f-121">This allows you to decrease the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="c892f-122">**Включить протокол общей памяти**</span><span class="sxs-lookup"><span data-stu-id="c892f-122">**Enable Shared Memory Protocol**</span></span>  
 <span data-ttu-id="c892f-123">Включает протокол общей памяти, который всегда используется первым (в том случае, если он включен) при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с клиента на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="c892f-123">Enables the shared memory protocol which is always tried first (if enabled), when connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c892f-124">Если протокол определен через префикс или как часть строки соединения, то попытка подключения будет происходить только через определенный протокол.</span><span class="sxs-lookup"><span data-stu-id="c892f-124">If the protocol is specified through a prefix or as part of the connection string, only the specified protocol is attempted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c892f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c892f-125">See Also</span></span>  
 [<span data-ttu-id="c892f-126">Выбор сетевого протокола</span><span class="sxs-lookup"><span data-stu-id="c892f-126">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
