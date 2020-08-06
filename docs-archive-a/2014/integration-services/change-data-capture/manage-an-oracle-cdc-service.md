---
title: Управление службой CDC Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 5972cee3-b1a9-4c56-aed6-bdddf84af283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5fbe769980297a06b7958ecad04bfed85b9b714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728593"
---
# <a name="manage-an-oracle-cdc-service"></a><span data-ttu-id="fb891-102">Manage an Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="fb891-102">Manage an Oracle CDC Service</span></span>
  <span data-ttu-id="fb891-103">Можно использовать консоль настройки службы CDC для управления конкретной службой CDC.</span><span class="sxs-lookup"><span data-stu-id="fb891-103">You can use the CDC Service Configuration Console to manage a specific CDC Service.</span></span>  
  
 <span data-ttu-id="fb891-104">**Выбор службы CDC, с которой требуется выполнить действия**</span><span class="sxs-lookup"><span data-stu-id="fb891-104">**To select the CDC service you want to work with**</span></span>  
  
1.  <span data-ttu-id="fb891-105">На левой панели консоли настройки службы CDC разверните список **Локальные службы CDC**.</span><span class="sxs-lookup"><span data-stu-id="fb891-105">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
2.  <span data-ttu-id="fb891-106">Выберите службу CDC, с которой требуется выполнить действия.</span><span class="sxs-lookup"><span data-stu-id="fb891-106">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="fb891-107">Также можно щелкнуть правой кнопкой мыши службу CDC, с которой требуется начать работу, и выбрать нужное действие.</span><span class="sxs-lookup"><span data-stu-id="fb891-107">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="fb891-108">См. раздел [Что можно сделать с помощью службы CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="fb891-108">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
 <span data-ttu-id="fb891-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="fb891-109">**OR**</span></span>  
  
1.  <span data-ttu-id="fb891-110">Выберите пункт **Локальные службы CDC** на левой панели консоли настройки службы CDC.</span><span class="sxs-lookup"><span data-stu-id="fb891-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console.</span></span>  
  
2.  <span data-ttu-id="fb891-111">В средней части консоли настройки службы CDC выберите службу, с которой требуется начать работу.</span><span class="sxs-lookup"><span data-stu-id="fb891-111">From the middle section of the CDC Service Configuration Console, select the service you want to work with.</span></span>  
  
     <span data-ttu-id="fb891-112">Также можно щелкнуть правой кнопкой мыши службу CDC, с которой требуется начать работу, и выбрать нужное действие.</span><span class="sxs-lookup"><span data-stu-id="fb891-112">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="fb891-113">См. раздел [Что можно сделать с помощью службы CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="fb891-113">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
##  <a name="what-can-you-do-with-a-cdc-service"></a><a name="BKMK_WhatcandowithCDCService"></a> <span data-ttu-id="fb891-114">Что можно сделать с помощью службы CDC Service</span><span class="sxs-lookup"><span data-stu-id="fb891-114">What can you do with a CDC Service</span></span>  
 <span data-ttu-id="fb891-115">При работе со службой CDC можно выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fb891-115">You can carry out the following actions when working with a CDC service.</span></span>  
  
### <a name="delete-the-service"></a><span data-ttu-id="fb891-116">Удаление службы</span><span class="sxs-lookup"><span data-stu-id="fb891-116">Delete the service</span></span>  
 <span data-ttu-id="fb891-117">На панели **Действия** в правой стороне консоли настройки службы CDC щелкните **Удалить** , чтобы удалить службу.</span><span class="sxs-lookup"><span data-stu-id="fb891-117">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
 <span data-ttu-id="fb891-118">Можно также щелкнуть правой кнопкой мыши службу CDC, которую необходимо удалить, и выбрать команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fb891-118">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
 <span data-ttu-id="fb891-119">**Примечание**. Если на момент удаления службы она запущена, перед удалением выполняется ее остановка.</span><span class="sxs-lookup"><span data-stu-id="fb891-119">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
 <span data-ttu-id="fb891-120">Чтобы удалить определение службы Windows для Oracle CDC, программе нужен доступ в режиме UPDATE к базе данных MSXDBCDC в соответствующем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb891-120">To delete the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="fb891-121">После нажатия кнопки «ОК» для удаления службы программа попытается выполнить удаление регистрации службы Oracle CDC в базе данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="fb891-121">When you click OK to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="fb891-122">Если программа не может удалить регистрацию службы Oracle CDC, поскольку для нее отсутствуют соответствующие разрешения, то выводит запрос на ввод имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с разрешениями на обновление базы данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="fb891-122">If the program cannot delete the Oracle CDC Service registration because it does not have the proper permissions, it prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with update permissions to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="fb891-123">Дополнительные сведения о вводе данных в диалоговом окне «Подключение к SQL Server» см. в разделе [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="fb891-123">For information about the data you must enter in the Connect to SQL Server dialog box, see [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
### <a name="edit-the-cdc-service-properties"></a><span data-ttu-id="fb891-124">Изменение свойств службы CDC</span><span class="sxs-lookup"><span data-stu-id="fb891-124">Edit the CDC Service Properties</span></span>  
 <span data-ttu-id="fb891-125">На панели **Действия** в правой стороне консоли настройки службы CDC щелкните пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fb891-125">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
 <span data-ttu-id="fb891-126">Также можно щелкнуть правой кнопкой мыши службу CDC, свойства которой требуется изменить, и выбрать команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fb891-126">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb891-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb891-127">See Also</span></span>  
 [<span data-ttu-id="fb891-128">Как управлять локальной службой CDC</span><span class="sxs-lookup"><span data-stu-id="fb891-128">How to Manage a Local CDC Service</span></span>](how-to-manage-a-local-cdc-service.md)  
