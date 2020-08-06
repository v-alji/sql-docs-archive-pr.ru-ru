---
title: Клиентские протоколы — свойства TCP и IP (вкладка «Протокол») | Документация Майкрософт
description: Узнайте, как указать параметры TCP/IP в Microsoft SQL Server Configuration Manager, например параметр проверки активности и номер порта по умолчанию.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737358"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a><span data-ttu-id="1e23e-103">Клиентские протоколы — свойства TCP/IP (вкладка "Протокол")</span><span class="sxs-lookup"><span data-stu-id="1e23e-103">Client Protocols - TCP and IP Properties (Protocol Tab)</span></span>
  <span data-ttu-id="1e23e-104">В диспетчере конфигурации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используйте вкладку **Протокол** в диалоговом окне **Свойства TCP/IP**, чтобы просмотреть или задать указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="1e23e-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use the **Protocol** tab on the **TCP/IP Properties** dialog box to view or specify the following options.</span></span> <span data-ttu-id="1e23e-105">Чтобы подключиться к другому порту, введите номер порта в поле **Порт по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="1e23e-105">To connect to a different port, type the port number in the **Default Port** box.</span></span> <span data-ttu-id="1e23e-106">Дополнительные сведения о строках подключения см. в разделе [Создание допустимой строки подключения с использованием протокола TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span><span class="sxs-lookup"><span data-stu-id="1e23e-106">For more information about connection strings, see [Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e23e-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="1e23e-107">Options</span></span>  
 <span data-ttu-id="1e23e-108">**Порт по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="1e23e-108">**Default Port**</span></span>  
 <span data-ttu-id="1e23e-109">Указывает порт, который сетевая библиотека TCP/IP использует для попытки подключения к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e23e-109">Specifies the port that the TCP/IP Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1e23e-110">Значение порта по умолчанию равно 1433.</span><span class="sxs-lookup"><span data-stu-id="1e23e-110">The default value port is 1433.</span></span>  
  
 <span data-ttu-id="1e23e-111">При подключении к экземпляру по умолчанию компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]клиент использует это значение.</span><span class="sxs-lookup"><span data-stu-id="1e23e-111">When connecting to a default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client uses this value.</span></span> <span data-ttu-id="1e23e-112">Если экземпляр по умолчанию был настроен для прослушивания другого порта, измените это значение на соответствующий номер порта.</span><span class="sxs-lookup"><span data-stu-id="1e23e-112">If a default instance has been configured to listen on a different port, change this value to that port number.</span></span>  
  
 <span data-ttu-id="1e23e-113">При подключении к именованному экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]клиент будет пытаться получить номер порта от службы браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запущенной на компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="1e23e-113">When connecting to a named instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client will attempt to obtain the port number from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service running on the server computer.</span></span> <span data-ttu-id="1e23e-114">Если служба браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не запущена, номер порта должен предоставляться через этот параметр или как часть строки соединения.</span><span class="sxs-lookup"><span data-stu-id="1e23e-114">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service is not running, the port number must be provided through this setting, or as part of the connection string.</span></span>  
  
 <span data-ttu-id="1e23e-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="1e23e-115">**Enabled**</span></span>  
 <span data-ttu-id="1e23e-116">Возможные значения: **Да** и **нет**.</span><span class="sxs-lookup"><span data-stu-id="1e23e-116">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="1e23e-117">**Проверка активности (Keep Alive)**</span><span class="sxs-lookup"><span data-stu-id="1e23e-117">**Keep Alive**</span></span>  
 <span data-ttu-id="1e23e-118">Этот параметр (в миллисекундах) управляет частотой попыток протокола TCP проверить работоспособность неактивного соединения путем отправки пакета **KEEPALIVE** .</span><span class="sxs-lookup"><span data-stu-id="1e23e-118">This parameter (in milliseconds) controls how often TCP attempts to verify that an idle connection is still intact by sending a **KEEPALIVE** packet.</span></span> <span data-ttu-id="1e23e-119">Значение по умолчанию — 30 000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="1e23e-119">The default is 30000 milliseconds.</span></span>  
  
 <span data-ttu-id="1e23e-120">**Интервал проверки активности**</span><span class="sxs-lookup"><span data-stu-id="1e23e-120">**Keep Alive Interval**</span></span>  
 <span data-ttu-id="1e23e-121">Этот параметр (в миллисекундах) определяет интервал, разделяющий повторные передачи пакета **KEEPALIVE** , пока не происходит получение ответа.</span><span class="sxs-lookup"><span data-stu-id="1e23e-121">This parameter (in milliseconds) determines the interval separating **KEEPALIVE** retransmissions until a response is received.</span></span> <span data-ttu-id="1e23e-122">Значение по умолчанию — 1 000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="1e23e-122">The default is 1000 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e23e-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e23e-123">See Also</span></span>  
 <span data-ttu-id="1e23e-124">[Выбор сетевого протокола](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="1e23e-124">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 <span data-ttu-id="1e23e-125">[Новый псевдоним &#40;вкладка Псевдоним&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span><span class="sxs-lookup"><span data-stu-id="1e23e-125">[New Alias &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span></span>  
 [<span data-ttu-id="1e23e-126">Свойства &#60;Псевдоним&#62; (вкладка "Псевдоним")</span><span class="sxs-lookup"><span data-stu-id="1e23e-126">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
