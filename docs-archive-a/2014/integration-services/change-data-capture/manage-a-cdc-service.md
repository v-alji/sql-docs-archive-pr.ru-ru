---
title: Управление службой CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- manSer
ms.assetid: 645ae53f-f352-4d6a-9eb0-264e53a93a18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d630392216e51efd9ea64116d57b388202061ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728597"
---
# <a name="manage-a-cdc-service"></a><span data-ttu-id="f96da-102">Управление службой CDC</span><span class="sxs-lookup"><span data-stu-id="f96da-102">Manage a CDC Service</span></span>
  <span data-ttu-id="f96da-103">В консоли конструктора CDC можно просматривать службы, созданные с помощью консоли конфигурации служб CDC, а также управлять всеми экземплярами в службе CDC Oracle.</span><span class="sxs-lookup"><span data-stu-id="f96da-103">You can use the CDC Designer Console to view the services you created with the CDC Service Configuration Console and manage all of the instances in the Oracle CDC Service.</span></span>  
  
 <span data-ttu-id="f96da-104">Для управления службой и отображения сведений о ней щелкните ее имя на панели слева.</span><span class="sxs-lookup"><span data-stu-id="f96da-104">Click the name of the service in the left pane to display information about the service and to manage it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f96da-105">Чтобы добавить службу в этот список, сначала необходимо создать ее с помощью консоли конфигурации служб CDC.</span><span class="sxs-lookup"><span data-stu-id="f96da-105">You must first create a service using the CDC Service Configuration Console to add services to this list.</span></span> <span data-ttu-id="f96da-106">Сведения о создании службы см. в справке в Интернете консоли конфигурации служб CDC.</span><span class="sxs-lookup"><span data-stu-id="f96da-106">For information on how to create a service, see the online help provided with the CDC Service Configuration Console.</span></span>  
  
## <a name="what-you-can-do-when-you-display-the-cdc-service-information"></a><span data-ttu-id="f96da-107">Какие действия доступны, когда отображаются сведения о службе CDC</span><span class="sxs-lookup"><span data-stu-id="f96da-107">What you can do when you display the CDC service information</span></span>  
 <span data-ttu-id="f96da-108">Когда отображаются сведения о службе, можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f96da-108">You can do the following when you display information about a service:</span></span>  
  
 <span data-ttu-id="f96da-109">**Создать новый экземпляр CDC для выбранной службы**</span><span class="sxs-lookup"><span data-stu-id="f96da-109">**Create a new CDC instance for the selected service**</span></span>  
  
 <span data-ttu-id="f96da-110">Щелкните **Создать экземпляр Oracle CDC** на панели справа, чтобы создать новый экземпляр для этой службы.</span><span class="sxs-lookup"><span data-stu-id="f96da-110">Click **New Oracle CDC Instance** in the right pane to create a new instance for that service.</span></span> <span data-ttu-id="f96da-111">Для создания экземпляра откроется мастер создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f96da-111">The New Instance wizard opens to create the instance.</span></span> <span data-ttu-id="f96da-112">Дополнительные сведения об использовании мастера создания экземпляра см. в разделе [Use the New Instance Wizard](use-the-new-instance-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f96da-112">For more information about the New Instance wizard, see [Use the New Instance Wizard](use-the-new-instance-wizard.md).</span></span>  
  
 <span data-ttu-id="f96da-113">**Запустить все экземпляры CDC в службе**</span><span class="sxs-lookup"><span data-stu-id="f96da-113">**Start all CDC instances in the service**</span></span>  
  
 <span data-ttu-id="f96da-114">Нажмите кнопку **Запустить все экземпляры** на панели справа, чтобы начать отслеживать данные от всех экземпляров, определенных в службе.</span><span class="sxs-lookup"><span data-stu-id="f96da-114">Click **Start All Instances** in the right pane to begin capturing data from all the defined instances in the service.</span></span>  
  
 <span data-ttu-id="f96da-115">**Остановить все экземпляры CDC в службе**</span><span class="sxs-lookup"><span data-stu-id="f96da-115">**Stop all CDC instances in the service**</span></span>  
  
 <span data-ttu-id="f96da-116">Нажмите кнопку **Остановить все экземпляры** , чтобы отслеживать измененные данные для всех экземпляров в службе.</span><span class="sxs-lookup"><span data-stu-id="f96da-116">Click **Stop All Instances** to stop the change data capture for all instances in the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96da-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f96da-117">See Also</span></span>  
 <span data-ttu-id="f96da-118">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="f96da-118">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="f96da-119">[Как управлять службой CDC из консоли конструктора CDC](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="f96da-119">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="f96da-120">Использование мастера создания экземпляра</span><span class="sxs-lookup"><span data-stu-id="f96da-120">Use the New Instance Wizard</span></span>](use-the-new-instance-wizard.md)  
  
  
