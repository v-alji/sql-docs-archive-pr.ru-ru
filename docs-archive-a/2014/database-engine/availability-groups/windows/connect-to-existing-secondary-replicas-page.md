---
title: Страница "подключение к существующим вторичным репликам" (мастер добавления реплики и мастера добавления баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.connecttoreplicas.f1
- sql12.swb.adddatabasewizard.connecttoreplicas.f1
ms.assetid: 850f1bc8-d7d0-425c-bd7b-03f0e9d3348e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 80af8dfebd6e23a923ddf67438edabf9ab0e2f65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729829"
---
# <a name="connect-to-existing-secondary-replicas-page-add-replica-wizard-and-add-databases-wizard"></a><span data-ttu-id="d6b09-102">Подключение к странице существующих вторичных реплик (мастер добавления реплики и мастер добавления баз данных)</span><span class="sxs-lookup"><span data-stu-id="d6b09-102">Connect to Existing Secondary Replicas Page (Add Replica Wizard and Add Databases Wizard)</span></span>
  <span data-ttu-id="d6b09-103"> В этом разделе описываются параметры на странице **Подключиться к существующим вторичным репликам**.</span><span class="sxs-lookup"><span data-stu-id="d6b09-103">This help topic describes the options of the **Connect to Existing Secondary Replicas** page.</span></span> <span data-ttu-id="d6b09-104">Этот раздел используется в [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] и [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] из [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6b09-104">This topic is used by the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="d6b09-105">**Столбцы сетки**</span><span class="sxs-lookup"><span data-stu-id="d6b09-105">**Grid columns:**</span></span>  
 <span data-ttu-id="d6b09-106">**Экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="d6b09-106">**Server Instance**</span></span>  
 <span data-ttu-id="d6b09-107">Отображает имя экземпляра сервера, на котором будет размещена реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="d6b09-107">Displays the name of the server instance that will host the availability replica.</span></span>  
  
 <span data-ttu-id="d6b09-108">**Подключение от имени**</span><span class="sxs-lookup"><span data-stu-id="d6b09-108">**Connected As**</span></span>  
 <span data-ttu-id="d6b09-109">Показывает учетную запись, подключенную к экземпляру сервера после установления соединения.</span><span class="sxs-lookup"><span data-stu-id="d6b09-109">Displays the account that is connected to the server instance, once the connection has been established.</span></span> <span data-ttu-id="d6b09-110">Если в этом столбце для данного экземпляра сервера отображается**Не подключено**, потребуется нажать кнопку **Подключить** или **Подключить все** .</span><span class="sxs-lookup"><span data-stu-id="d6b09-110">If this column displays "**Not Connected**" for a given server instance, you will need to click either the **Connect** or **Connect All** button.</span></span>  
  
 <span data-ttu-id="d6b09-111">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="d6b09-111">**Connect**</span></span>  
 <span data-ttu-id="d6b09-112">Нажмите, если данный экземпляр сервера работает под учетной записью, отличной от учетной записи экземпляров сервера, к которым нужно подключиться.</span><span class="sxs-lookup"><span data-stu-id="d6b09-112">Click if this server instance is running under a different account than other server instances to which you need to connect.</span></span>  
  
 <span data-ttu-id="d6b09-113">**Подключить все**</span><span class="sxs-lookup"><span data-stu-id="d6b09-113">**Connect All**</span></span>  
 <span data-ttu-id="d6b09-114">Нажмите эту кнопку, только если все экземпляры [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , к которым нужно подключиться, работают в виде службы под одной учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="d6b09-114">Click only if every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which you need to connect is running as a service in the same user account.</span></span>  
  
 <span data-ttu-id="d6b09-115">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="d6b09-115">**Cancel**</span></span>  
 <span data-ttu-id="d6b09-116">Щелкните эту кнопку, чтобы отменить запуск мастера.</span><span class="sxs-lookup"><span data-stu-id="d6b09-116">Click to cancel the wizard.</span></span> <span data-ttu-id="d6b09-117">Отмена работы мастера на странице **Подключение к существующим вторичным репликам** приводит к его закрытию без выполнения каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="d6b09-117">On the **Connect to Existing Secondary Replica** page, cancelling the wizard cause it to exit without performing any actions.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d6b09-118">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d6b09-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d6b09-119">Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d6b09-119">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="d6b09-120">Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d6b09-120">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="d6b09-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6b09-121">See Also</span></span>  
 [<span data-ttu-id="d6b09-122">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d6b09-122">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
