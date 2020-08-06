---
title: Использовать мои подписки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3378a65637ad04151cc517fd9047363af954c31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739095"
---
# <a name="use-my-subscriptions"></a><span data-ttu-id="6d13b-102">Использовать «Мои подписки»</span><span class="sxs-lookup"><span data-stu-id="6d13b-102">Use My Subscriptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]<span data-ttu-id="6d13b-103">Диспетчер отчетов включает страницу **«Мои подписки** », которая организует все подписки в одном месте.</span><span class="sxs-lookup"><span data-stu-id="6d13b-103">Report Manager includes a **My Subscriptions** page that organizes all of your subscriptions into one place.</span></span> <span data-ttu-id="6d13b-104">Можно использовать страницу «Мои подписки» для просмотра, изменения и удаления существующих подписок.</span><span class="sxs-lookup"><span data-stu-id="6d13b-104">You can use My Subscriptions to view, modify, and delete existing subscriptions.</span></span> <span data-ttu-id="6d13b-105">Однако ее нельзя использовать для создания подписок.</span><span class="sxs-lookup"><span data-stu-id="6d13b-105">However, you cannot use it to create subscriptions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="6d13b-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="6d13b-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 <span data-ttu-id="6d13b-107">На странице «Мои подписки» можно сортировать подписки по папкам, отчетам, описаниям, триггерам, дате последнего запуска и состоянию.</span><span class="sxs-lookup"><span data-stu-id="6d13b-107">Within My Subscriptions, you can sort subscriptions by folder, report, description, trigger, last run, or status.</span></span> <span data-ttu-id="6d13b-108">Все значения сортируются по алфавиту, за исключением даты последнего запуска; по ней выполняется сортировка в хронологическом порядке.</span><span class="sxs-lookup"><span data-stu-id="6d13b-108">All values are sorted alphabetically except for Last Run, which is in chronological order.</span></span>  
  
 <span data-ttu-id="6d13b-109">Страница «Мои подписки» показывает лишь созданные вами подписки.</span><span class="sxs-lookup"><span data-stu-id="6d13b-109">My Subscriptions shows only the subscriptions that you create.</span></span> <span data-ttu-id="6d13b-110">На ней не отображаются ни подписки, принадлежащие другим пользователям (даже если вы на них подписаны), ни управляемые данными подписки.</span><span class="sxs-lookup"><span data-stu-id="6d13b-110">It does not list subscriptions that are owned by other users, even if you are added as a subscriber to those subscriptions, nor does it show data-driven subscriptions.</span></span>  
  
 <span data-ttu-id="6d13b-111">В ней нельзя выполнить поиск подписки по имени, по сведениям о триггерах, состоянию и др.</span><span class="sxs-lookup"><span data-stu-id="6d13b-111">You cannot search for subscriptions by name, nor can you search for subscriptions based on trigger information, status information, and so forth.</span></span> <span data-ttu-id="6d13b-112">Дополнительные сведения см. в статьях [Создание, изменение и удаление стандартных подписок &#40;Reporting Services в основном режиме&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6d13b-112">For more information, see [Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span></span>  
  
## <a name="how-to-use-my-subscriptions"></a><span data-ttu-id="6d13b-113">Как использовать страницу «Мои подписки»</span><span class="sxs-lookup"><span data-stu-id="6d13b-113">How to Use My Subscriptions</span></span>  
 <span data-ttu-id="6d13b-114">Страница «Мои подписки» доступна в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="6d13b-114">My Subscriptions is available through Report Manager.</span></span> <span data-ttu-id="6d13b-115">Чтобы получить доступ к странице «Мои подписки», нажмите кнопку **Мои подписки** на общей панели инструментов диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="6d13b-115">To access My Subscriptions, click **My Subscriptions** on the Report Manager global toolbar.</span></span>  
  
## <a name="use-windows-powershell-to-list-mysubscriptions"></a><span data-ttu-id="6d13b-116">Использование Windows PowerShell для перечисления MySubscriptions</span><span class="sxs-lookup"><span data-stu-id="6d13b-116">Use Windows PowerShell to list MySubscriptions</span></span>  
 <span data-ttu-id="6d13b-117">![Содержимое, связанное с PowerShell](../media/rs-powershellicon.jpg "Содержимое, связанное с PowerShell")</span><span class="sxs-lookup"><span data-stu-id="6d13b-117">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>  
  
 <span data-ttu-id="6d13b-118">Следующий скрипт PowerShell возвращает список подписок и свойств подписок для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d13b-118">The following PowerShell script will return the list of subscriptions and subscription properties for the current user.</span></span> <span data-ttu-id="6d13b-119">Дополнительные сведения см. в разделе [Метод ReportingService2010.ListMySubscriptions](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span><span class="sxs-lookup"><span data-stu-id="6d13b-119">For more information, see [ReportingService2010.ListMySubscriptions Method](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span></span>  
  
```powershell
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions
```  
  
## <a name="see-also"></a><span data-ttu-id="6d13b-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d13b-120">See Also</span></span>  
 <span data-ttu-id="6d13b-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="6d13b-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="6d13b-122">[Подписки и доставка (службы Reporting Services)](subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="6d13b-122">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="6d13b-123">Создание и администрирование подписок для серверов отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="6d13b-123">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../create-manage-subscriptions-native-mode-report-servers.md)  
