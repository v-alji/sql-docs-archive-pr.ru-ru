---
title: Свойства подписчика | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.subscribers.f1
helpviewer_keywords:
- Subscriber Properties dialog box
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81ab9cf5f277ccfe1044e5a7083f019db9d843ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749703"
---
# <a name="subscriber-properties"></a><span data-ttu-id="1f2ed-102">Свойства подписчика</span><span class="sxs-lookup"><span data-stu-id="1f2ed-102">Subscriber Properties</span></span>
  <span data-ttu-id="1f2ed-103">Диалоговое окно **Свойства подписчика** содержит сведения, относящиеся к подписчикам, использующим версии [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], предшествующие [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2ed-103">The **Subscriber Properties** dialog box contains information relevant to Subscribers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f2ed-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f2ed-104">Options</span></span>  
 <span data-ttu-id="1f2ed-105">**Соединение агента с подписчиком**</span><span class="sxs-lookup"><span data-stu-id="1f2ed-105">**Agent Connection to the Subscriber**</span></span>  
 <span data-ttu-id="1f2ed-106">Контекст, в котором агент распространителя и агент слияния устанавливают соединение от распространителя к подписчику. Применяется только к версиям, предшествующим [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2ed-106">The context under which the Distribution Agent and Merge Agent connect from the Distributor to the Subscriber This applies only to versions before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="1f2ed-107">Выберите **Выполнять олицетворение учетной записи процесса агента** для соединения с подписчиком при помощи контекста учетной записи агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на распространителе или укажите **Проверка подлинности SQL Server**, а затем введите значения в поля **Имя входа** и **Пароль**.</span><span class="sxs-lookup"><span data-stu-id="1f2ed-107">Select **Impersonate agent process account** to make connections to the Subscriber using the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent account at the Distributor, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1f2ed-108">рекомендует выбрать пункт **Выполнять олицетворение учетной записи процесса агента**.</span><span class="sxs-lookup"><span data-stu-id="1f2ed-108">recommends that you select **Impersonate agent process account**.</span></span>  
  
 <span data-ttu-id="1f2ed-109">Для [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий данные о соединении указываются для каждой подписки в мастере создания подписки, их можно изменить в диалоговом окне **Свойства подписки** .</span><span class="sxs-lookup"><span data-stu-id="1f2ed-109">For [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, connection information is specified for each subscription in the New Subscription Wizard and can be changed in the **Subscription Properties** dialog box.</span></span>  
  
 <span data-ttu-id="1f2ed-110">**Расписания агентов по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="1f2ed-110">**Default Agent Schedules**</span></span>  
 <span data-ttu-id="1f2ed-111">Расписание по умолчанию, используемое в мастере создания подписки для подписчиков, использующих версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , предшествующие [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2ed-111">The default schedule used in the New Subscription Wizard for Subscribers running versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
 <span data-ttu-id="1f2ed-112">**Разное**</span><span class="sxs-lookup"><span data-stu-id="1f2ed-112">**Miscellaneous**</span></span>  
 <span data-ttu-id="1f2ed-113">Содержит сведения о подписчике и типе подписчика.</span><span class="sxs-lookup"><span data-stu-id="1f2ed-113">Includes information on the Subscriber and Subscriber type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2ed-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f2ed-114">See Also</span></span>  
 [<span data-ttu-id="1f2ed-115">Просмотр и изменение свойств издателя и распространителя</span><span class="sxs-lookup"><span data-stu-id="1f2ed-115">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

 [<span data-ttu-id="1f2ed-116">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="1f2ed-116">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
