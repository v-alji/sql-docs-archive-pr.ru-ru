---
title: Свойства TCP-IP (вкладка «Протоколы») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655508"
---
# <a name="tcp---ip-properties-protocols-tab"></a><span data-ttu-id="12c3b-102">Свойства TCP-IP (вкладка «Протоколы»)</span><span class="sxs-lookup"><span data-stu-id="12c3b-102">TCP - IP Properties (Protocols Tab)</span></span>
  <span data-ttu-id="12c3b-103">Используйте диалоговое окно **Свойства TCP/IP** для настройки параметров протокола TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="12c3b-103">Use the **TCP/IP Properties** dialog box to configure the options for the TCP/IP protocol.</span></span> <span data-ttu-id="12c3b-104">Щелкните пункт **TCP/IP** в левой панели, чтобы вывести настройки отдельных IP-адресов в панель сведений.</span><span class="sxs-lookup"><span data-stu-id="12c3b-104">Click **TCP/IP** in the left pane, to show individual IP address configurations in the details pane.</span></span>  
  
 <span data-ttu-id="12c3b-105">Чтобы изменения вступили в силу, необходимо перезапустить Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12c3b-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted before the changes take effect.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12c3b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="12c3b-106">Options</span></span>  
 <span data-ttu-id="12c3b-107">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="12c3b-107">**Enabled**</span></span>  
 <span data-ttu-id="12c3b-108">Возможные значения: **Да** и **Нет**.</span><span class="sxs-lookup"><span data-stu-id="12c3b-108">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="12c3b-109">**Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="12c3b-109">**Keep Alive**</span></span>  
 <span data-ttu-id="12c3b-110">Задайте интервал (в миллисекундах), через который будут отправляться пакеты проверки активности для проверки доступности компьютера на удаленном конце соединения.</span><span class="sxs-lookup"><span data-stu-id="12c3b-110">Specify the interval (milliseconds) in which keep-alive packets are transmitted to verify that the computer at the remote end of a connection is still available.</span></span>  
  
 <span data-ttu-id="12c3b-111">**Listen All**</span><span class="sxs-lookup"><span data-stu-id="12c3b-111">**Listen All**</span></span>  
 <span data-ttu-id="12c3b-112">Укажите, должен ли SQL Server прослушивать все IP-адреса, привязанные к сетевым адаптерам компьютера.</span><span class="sxs-lookup"><span data-stu-id="12c3b-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span></span> <span data-ttu-id="12c3b-113">Если параметр имеет значение **Нет**, настройте каждый IP-адрес отдельно при помощи диалогового окна свойств для каждого IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="12c3b-113">If set to **No**, configure each IP address separately using the properties dialog box for each IP address.</span></span> <span data-ttu-id="12c3b-114">Если параметр имеет значение **Да**, то настройки, находящиеся в диалоговом окне свойств **IPAll** , будут применяться ко всем IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="12c3b-114">If set to **Yes**, the settings of the **IPAll** properties box will apply to all IP addresses.</span></span> <span data-ttu-id="12c3b-115">Значение по умолчанию — **Да**.</span><span class="sxs-lookup"><span data-stu-id="12c3b-115">Default value is **Yes**.</span></span>  
  
 <span data-ttu-id="12c3b-116">**No Delay**</span><span class="sxs-lookup"><span data-stu-id="12c3b-116">**No Delay**</span></span>  
 <span data-ttu-id="12c3b-117">Сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не реализует изменения этого свойства.</span><span class="sxs-lookup"><span data-stu-id="12c3b-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not implement changes to this property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c3b-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="12c3b-118">See Also</span></span>  
 <span data-ttu-id="12c3b-119">[Выбор сетевого протокола](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="12c3b-119">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="12c3b-120">Создание допустимой строки подключения с использованием протокола TCP/IP</span><span class="sxs-lookup"><span data-stu-id="12c3b-120">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
