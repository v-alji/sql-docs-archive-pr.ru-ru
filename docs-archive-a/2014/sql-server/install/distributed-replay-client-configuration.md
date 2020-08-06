---
title: Конфигурация клиента распределенное воспроизведение | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668624"
---
# <a name="distributed-replay-client-configuration"></a><span data-ttu-id="5e0a9-102">Конфигурация клиента распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="5e0a9-102">Distributed Replay Client Configuration</span></span>
  <span data-ttu-id="5e0a9-103">Страница **Конфигурация клиента распределенного воспроизведения** мастера установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет указать пользователей, которым нужно предоставить административные разрешения на службу клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-103">Use the **Distributed Replay Client Configuration** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the users you want to grant administrative permissions to for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="5e0a9-104">Пользователи с административными разрешениями будут иметь неограниченный доступ к службе клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-104">Users that have administrative permissions will have unlimited access to the Distributed Replay client service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e0a9-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="5e0a9-105">Options</span></span>  
 <span data-ttu-id="5e0a9-106">**Имя контроллера**</span><span class="sxs-lookup"><span data-stu-id="5e0a9-106">**Controller Name**</span></span>  
 <span data-ttu-id="5e0a9-107">Это необязательный параметр, значение по умолчанию — \<*blank*> .</span><span class="sxs-lookup"><span data-stu-id="5e0a9-107">This is an optional parameter, and the default value is \<*blank*>.</span></span>  
  
 <span data-ttu-id="5e0a9-108">Введите имя контроллера, с которым будет связываться клиентский компьютер для доступа к службе клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-108">Enter the name of the controller that the client computer will communicate with for the Distributed Replay client service.</span></span> <span data-ttu-id="5e0a9-109">Следует отметить следующее.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-109">Note the following:</span></span>  
  
-   <span data-ttu-id="5e0a9-110">Должно быть указано полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5e0a9-110">The name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5e0a9-111">Например, FQDN узла с именем server1 в иерархии продуктов Майкрософт может иметь вид server1.products.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-111">For example, a host called server1 in the products hierarchy at Microsoft may have an FQDN of server1.products.microsoft.com.</span></span>  
  
-   <span data-ttu-id="5e0a9-112">Если контроллер уже настроен, введите имя этого контроллера при настройке каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-112">If you have already set up a controller, enter the name of the controller while configuring each client.</span></span>  
  
-   <span data-ttu-id="5e0a9-113">Если контроллер еще не настроен, имя контроллера можно оставить пустым.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-113">If you have net yet set up a controller, you can leave the controller name blank.</span></span> <span data-ttu-id="5e0a9-114">Однако необходимо вручную ввести имя контроллера в файл **конфигурации клиента** .</span><span class="sxs-lookup"><span data-stu-id="5e0a9-114">However, you must manually enter the controller name in the **client configuration** file.</span></span>  
  
 <span data-ttu-id="5e0a9-115">**Рабочий каталог**</span><span class="sxs-lookup"><span data-stu-id="5e0a9-115">**Working Directory**</span></span>  
 <span data-ttu-id="5e0a9-116">Укажите рабочий каталог для службы клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-116">Specify the working directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="5e0a9-117">Рабочий каталог по умолчанию — \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-117">The default working directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span></span>  
  
 <span data-ttu-id="5e0a9-118">**Папка результатов**</span><span class="sxs-lookup"><span data-stu-id="5e0a9-118">**Result Directory**</span></span>  
 <span data-ttu-id="5e0a9-119">Укажите каталог результатов для службы клиента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-119">Specify the result directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="5e0a9-120">Каталог результатов по умолчанию — \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span><span class="sxs-lookup"><span data-stu-id="5e0a9-120">The default result directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span></span>  
  
  
