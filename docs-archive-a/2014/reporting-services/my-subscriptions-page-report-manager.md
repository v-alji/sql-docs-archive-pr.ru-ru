---
title: Страница «Мои подписки» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 491a85a3-f323-4155-a0a8-de2779899995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 891796ec491b157f3c9bb5b4adfd15daedbc7c88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739518"
---
# <a name="my-subscriptions-page-report-manager"></a><span data-ttu-id="531de-102">Страница «Мои подписки» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="531de-102">My Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="531de-103">Используйте страницу «Мои подписки» для просмотра всех подписок.</span><span class="sxs-lookup"><span data-stu-id="531de-103">Use the My Subscriptions page to view all of your subscriptions in one place.</span></span> <span data-ttu-id="531de-104">На этой странице можно открыть, изменить или удалить любую из своих подписок.</span><span class="sxs-lookup"><span data-stu-id="531de-104">From this page, you can access and modify or delete any subscription that you own.</span></span> <span data-ttu-id="531de-105">Пользователь является владельцем только тех подписок, которые были им созданы.</span><span class="sxs-lookup"><span data-stu-id="531de-105">You own only the subscriptions that you create.</span></span> <span data-ttu-id="531de-106">Невозможно открыть подписки других пользователей или используемые, но не принадлежащие пользователю подписки (например, если имя пользователя было добавлено к подписке, определенной другим пользователем).</span><span class="sxs-lookup"><span data-stu-id="531de-106">You cannot access those of other users, nor can you access subscriptions that you use but do not own (for example, if your name has been added to an existing subscription defined by another user).</span></span> <span data-ttu-id="531de-107">На этой странице невозможно создать подписку.</span><span class="sxs-lookup"><span data-stu-id="531de-107">You cannot create subscriptions from this page.</span></span> <span data-ttu-id="531de-108">Дополнительные сведения о создании подписок см. на [странице Создание подписки или изменение подписки &#40;диспетчер отчетов&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="531de-108">For more information about creating subscriptions, see the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="531de-109">По умолчанию подписки отсортированы в алфавитном порядке по именам отчетов.</span><span class="sxs-lookup"><span data-stu-id="531de-109">By default, subscriptions are sorted in alphabetical order by report name.</span></span> <span data-ttu-id="531de-110">Чтобы изменить порядок сортировки, щелкните заголовок другого столбца.</span><span class="sxs-lookup"><span data-stu-id="531de-110">Click a different column heading to change how subscriptions are sorted.</span></span> <span data-ttu-id="531de-111">При отсутствии подписок или разрешения на создание и управление подписками на этой странице подписки не отображаются.</span><span class="sxs-lookup"><span data-stu-id="531de-111">If you have no subscriptions or if permission to create or manage subscriptions is disabled, no subscriptions appear on the page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="531de-112">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="531de-112">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="531de-113">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="531de-113">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="531de-114">Навигация</span><span class="sxs-lookup"><span data-stu-id="531de-114">Navigation</span></span>  
 <span data-ttu-id="531de-115">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="531de-115">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-my-subscriptions-page"></a><span data-ttu-id="531de-116">Открытие страницы «Мои подписки»</span><span class="sxs-lookup"><span data-stu-id="531de-116">To open the My Subscriptions page</span></span>  
  
1.  <span data-ttu-id="531de-117">Откройте диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="531de-117">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="531de-118">В верхнем правом углу страницы нажмите кнопку «Мои подписки».</span><span class="sxs-lookup"><span data-stu-id="531de-118">At the top of the page, in the right-hand corner, click My Subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="531de-119">Страница «Мои подписки» доступна всегда, даже если отсутствует разрешение на создание подписок.</span><span class="sxs-lookup"><span data-stu-id="531de-119">My Subscriptions is always available, even if you lack permission to create subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="531de-120">Варианты</span><span class="sxs-lookup"><span data-stu-id="531de-120">Options</span></span>  
 <span data-ttu-id="531de-121">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="531de-121">**Delete**</span></span>  
 <span data-ttu-id="531de-122">Установите флажки для подписок, которые требуется удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="531de-122">Select the check box next to each subscription that you want to delete and click **Delete**.</span></span>  
  
 <span data-ttu-id="531de-123">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="531de-123">**Edit**</span></span>  
 <span data-ttu-id="531de-124">Щелкните, чтобы просмотреть или изменить описание.</span><span class="sxs-lookup"><span data-stu-id="531de-124">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="531de-125">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="531de-125">**Report**</span></span>  
 <span data-ttu-id="531de-126">Показывает отчет, указанный в подписке.</span><span class="sxs-lookup"><span data-stu-id="531de-126">Shows the report that is specified in the subscription.</span></span> <span data-ttu-id="531de-127">Для просмотра отчета щелкните его имя.</span><span class="sxs-lookup"><span data-stu-id="531de-127">Click the report name to view the report.</span></span>  
  
 <span data-ttu-id="531de-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="531de-128">**Description**</span></span>  
 <span data-ttu-id="531de-129">Показывает описание подписки.</span><span class="sxs-lookup"><span data-stu-id="531de-129">Shows a description of the subscription.</span></span> <span data-ttu-id="531de-130">Чтобы просмотреть или изменить сведения о подписке для отчета, щелкните описание.</span><span class="sxs-lookup"><span data-stu-id="531de-130">Click the description to view or edit the subscription information for the report.</span></span>  
  
 <span data-ttu-id="531de-131">**Папка**</span><span class="sxs-lookup"><span data-stu-id="531de-131">**Folder**</span></span>  
 <span data-ttu-id="531de-132">Показывает папку, в которой хранится отчет, указанный в подписке.</span><span class="sxs-lookup"><span data-stu-id="531de-132">Shows the folder that contains the report that is specified in the subscription.</span></span> <span data-ttu-id="531de-133">Щелкните папку для просмотра ее содержимого.</span><span class="sxs-lookup"><span data-stu-id="531de-133">Click the folder name to view the contents of the folder.</span></span>  
  
 <span data-ttu-id="531de-134">**Триггер**</span><span class="sxs-lookup"><span data-stu-id="531de-134">**Trigger**</span></span>  
 <span data-ttu-id="531de-135">Указывает критерии запуска подписки.</span><span class="sxs-lookup"><span data-stu-id="531de-135">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="531de-136">Триггер **TimedSubscription** основывается на расписании, определяющем время запуска подписки.</span><span class="sxs-lookup"><span data-stu-id="531de-136">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="531de-137">Триггер **SnapshotUpdated** основывается на обновлении, внесенном в моментальный снимок отчета.</span><span class="sxs-lookup"><span data-stu-id="531de-137">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="531de-138">**Последний запуск**</span><span class="sxs-lookup"><span data-stu-id="531de-138">**Last Run**</span></span>  
 <span data-ttu-id="531de-139">Показывает, когда была проведена последняя обработка подписки.</span><span class="sxs-lookup"><span data-stu-id="531de-139">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="531de-140">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="531de-140">**Status**</span></span>  
 <span data-ttu-id="531de-141">Показывает состояние подписки.</span><span class="sxs-lookup"><span data-stu-id="531de-141">Shows the status of the subscription.</span></span> <span data-ttu-id="531de-142">Обычно в качестве состояния используется либо значение «Новая», либо дата и время последнего выполнения подписки.</span><span class="sxs-lookup"><span data-stu-id="531de-142">Usually, the status value is either "New" or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="531de-143">Значение состояния «Ошибочные данные» отображается в случае, когда подписка включает указатель на зашифрованные значения, которые больше не действительны (то есть на сохраненные учетные данные, использованные при выполнении отчета).</span><span class="sxs-lookup"><span data-stu-id="531de-143">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="531de-144">Существующие зашифрованные значения не могут быть использованы после того, как на сервере отчетов были созданы новые симметричные ключи для шифрования и дешифрования данных.</span><span class="sxs-lookup"><span data-stu-id="531de-144">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="531de-145">Подписку нельзя обработать, если она деактивирована.</span><span class="sxs-lookup"><span data-stu-id="531de-145">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="531de-146">Для обновления подписки и перевода ее в исправное состояние откройте подписку, а затем сохраните ее.</span><span class="sxs-lookup"><span data-stu-id="531de-146">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531de-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="531de-147">See Also</span></span>  
 <span data-ttu-id="531de-148">[Подписки и доставка (службы Reporting Services)](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="531de-148">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="531de-149">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="531de-149">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
