---
title: Укажите тип подписки на публикацию слиянием и приоритет разрешения конфликтов (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752107"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a><span data-ttu-id="8648d-102">Указание типа подписки на публикацию слиянием и приоритета устранения конфликтов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8648d-102">Specify a Merge Subscription Type and Conflict Resolution Priority (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8648d-103">Задание типа и приоритета разрешения конфликтов для подписки на публикацию слиянием осуществляется на странице **Тип подписки** мастера создания подписки.</span><span class="sxs-lookup"><span data-stu-id="8648d-103">Specify a merge subscription type and conflict resolution priority on the **Subscription Type** page of the New Subscription Wizard.</span></span> <span data-ttu-id="8648d-104">Дополнительные сведения об использовании этого мастера см. в разделе [Create a Pull Subscription](create-a-pull-subscription.md) и [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="8648d-104">For more information about using this wizard, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="8648d-105">После создания подписки нельзя изменить ее тип, но для типа серверной подписки можно изменить приоритет в диалоговом окне **Свойства подписки — \<Publisher>: \<PublicationDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="8648d-105">Subscription type cannot be modified after a subscription is created, but priority can be modified for the server subscription type in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box.</span></span> <span data-ttu-id="8648d-106">Дополнительные сведения о доступе к этому диалоговому окну см. в разделах [Просмотр и изменение свойств принудительной подписки](view-and-modify-push-subscription-properties.md) и [Просмотр и изменение свойств подписки по запросу](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8648d-106">For more information about accessing this dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a><span data-ttu-id="8648d-107">Указание типа подписки на публикацию слиянием и приоритета разрешения конфликтов</span><span class="sxs-lookup"><span data-stu-id="8648d-107">To specify a merge subscription type and conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="8648d-108">На странице **Тип подписки** мастера создания подписки выберите **Клиент** или **Сервер** в качестве значения параметра **Тип подписки** .</span><span class="sxs-lookup"><span data-stu-id="8648d-108">On the **Subscription Type** page of the New Subscription Wizard, select **Client** or **Server** for the **Subscription Type** option.</span></span>  
  
2.  <span data-ttu-id="8648d-109">Если выбран тип подписки **Сервер**, введите также значение (от 0.00 до 99.99) для параметра **Приоритет разрешения конфликтов** .</span><span class="sxs-lookup"><span data-stu-id="8648d-109">If you select a subscription type of **Server**, also enter a value (0.00 to 99.99) for the **Priority for Conflict Resolution** option.</span></span>  
  
### <a name="to-modify-the-conflict-resolution-priority"></a><span data-ttu-id="8648d-110">Изменение приоритета разрешения конфликтов</span><span class="sxs-lookup"><span data-stu-id="8648d-110">To modify the conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="8648d-111">В диалоговом окне **Свойства подписки — \<Publisher>: \<PublicationDatabase>** в издателе введите значение (от 0,00 до 99,99) для параметра **Приоритет**.</span><span class="sxs-lookup"><span data-stu-id="8648d-111">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** at the Publisher, enter a value (0.00 to 99.99) for the **Priority** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8648d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="8648d-112">See Also</span></span>  
 <span data-ttu-id="8648d-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="8648d-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="8648d-114">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="8648d-114">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
