---
title: Кэширование отчета (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- cache [Reporting Services]
- cached reports [Reporting Services]
- schedules [Reporting Services], report expiration
- expiration [Reporting Services]
ms.assetid: 723d1cb0-c2e7-4763-8690-a6a7a8bbbb90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e359e6c7a40b267979137ef2b3a285667a6fdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665828"
---
# <a name="cache-a-report-report-manager"></a><span data-ttu-id="fd7f1-102">кэшировать отчет (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="fd7f1-102">Cache a Report (Report Manager)</span></span>
  <span data-ttu-id="fd7f1-103">Один из способов повышения производительности состоит в настройке свойств кэширования для отчета.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-103">One way to improve performance is to configure caching properties for a report.</span></span> <span data-ttu-id="fd7f1-104">При кэшировании отчета копия отчета, подготовленного для хранения, сохраняется на короткий промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-104">When a report is cached, a copy of the rendered report is saved for a short period of time.</span></span> <span data-ttu-id="fd7f1-105">Первый пользователь, запросивший этот отчет, должен ожидать, пока не закончится вся обработка, прежде чем сможет просмотреть отчет.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-105">The first user who requests the report must wait for all processing to complete before viewing the report.</span></span> <span data-ttu-id="fd7f1-106">Последующие пользователи, запрашивающие тот же отчет в пределах времени кэширования, могут сразу же просмотреть его, поскольку обработка уже выполнена.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-106">Subsequent users who request the report within the caching period can view it right away because processing has already occurred.</span></span>  
  
 <span data-ttu-id="fd7f1-107">Существуют ограничения на типы отчетов, которые можно кэшировать.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-107">There are restrictions on the types of reports that you can cache.</span></span> <span data-ttu-id="fd7f1-108">Например, отчет не может быть кэширован, если выходные данные отчета зависят от идентификатора пользователя или если данные получаются с помощью токена безопасности пользователя, запросившего отчет.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-108">For example, a report cannot be cached if report output varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="fd7f1-109">Дополнительные сведения см. в разделе [Кэширование отчетов (службы SSRS)](caching-reports-ssrs.md), это был единственный способ предварительной загрузки кэша.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="fd7f1-110">Назначение момента для истечения срока действия кэшированного отчета</span><span class="sxs-lookup"><span data-stu-id="fd7f1-110">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="fd7f1-111">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fd7f1-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="fd7f1-112">В диспетчере отчетов перейдите на страницу **Содержимое** .</span><span class="sxs-lookup"><span data-stu-id="fd7f1-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="fd7f1-113">Перейдите к отчету, для которого необходимо задать свойства кэширования, подведите к нему курсор и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-113">Navigate to the report for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="fd7f1-114">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-114">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="fd7f1-115">В левом окне щелкните **Параметры обработки**.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-115">In the left frame, click the **Processing Options**.</span></span>  
  
5.  <span data-ttu-id="fd7f1-116">На этой странице выберите **Всегда запускать этот отчет с самыми последними данными**.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-116">On the page, select **Always run this report with the most recent data**.</span></span>  
  
6.  <span data-ttu-id="fd7f1-117">Выберите один из режимов кэширования и настройте истечение срока действия:</span><span class="sxs-lookup"><span data-stu-id="fd7f1-117">Select one of the following two cache options and configure expiration as follows:</span></span>  
  
    -   <span data-ttu-id="fd7f1-118">Чтобы срок действия кэшированной копии истек через определенное время, щелкните **Кэшировать временную копию отчета. Срок действия копии отчета заканчивается через несколько минут**.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-118">To configure a cached copy to expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes**.</span></span> <span data-ttu-id="fd7f1-119">Введите срок действия отчета (в минутах).</span><span class="sxs-lookup"><span data-stu-id="fd7f1-119">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="fd7f1-120">Чтобы срок действия кэшированной копии истек в соответствии с расписанием, выберите **Кэшировать временную копию отчета. Срок действия копии отчета истекает в соответствии со следующим расписанием**.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-120">To configure a cached copy to expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="fd7f1-121">Щелкните **Настроить**или выберите общее расписание для управления истечением срока действия отчета.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-121">Click **Configure**, or select a shared schedule to control report expiration</span></span>  
  
7.  <span data-ttu-id="fd7f1-122">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fd7f1-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7f1-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd7f1-123">See Also</span></span>  
 <span data-ttu-id="fd7f1-124">[Установка свойств обработки отчетов](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fd7f1-124">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="fd7f1-125">Кэширование отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="fd7f1-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
