---
title: Страница "подписки" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cf3a6bd0-e0b2-4875-a532-63ef34cfa860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c67895babe99c92b7c09afd8cb75ca88d5cd7553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734929"
---
# <a name="subscriptions-page-report-manager"></a><span data-ttu-id="105d6-102">Страница «Подписки» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="105d6-102">Subscriptions Page (Report Manager)</span></span>
  <span data-ttu-id="105d6-103">Используйте страницу «Подписки», чтобы просмотреть все подписки для текущего отчета или общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="105d6-103">Use the Subscriptions page to list all of the subscriptions for the current report or shared data source.</span></span> <span data-ttu-id="105d6-104">Если имеется соответствующее разрешение (например, переданное задачей «Управление всеми подписками»), можно просмотреть подписки всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="105d6-104">If you have sufficient permission (as conveyed by the "Manage all subscriptions" task), you can view the subscriptions of all users.</span></span> <span data-ttu-id="105d6-105">В противном случае эта страница отобразит только подписки, принадлежащие вам.</span><span class="sxs-lookup"><span data-stu-id="105d6-105">Otherwise, this page shows only the subscriptions that you own.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="105d6-106">Другие страницы также содержат данные о подписке.</span><span class="sxs-lookup"><span data-stu-id="105d6-106">Other pages also contain subscription information.</span></span> <span data-ttu-id="105d6-107">Дополнительные сведения см. на [странице Мои подписки &#40;диспетчер отчетов&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) для доступа ко всем подпискам в одном месте или на [странице Создание подписки или изменение подписки &#40;диспетчер отчетов&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) для создания или изменения подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-107">For more information, see [My Subscriptions Page &#40;Report Manager&#41;](../../2014/reporting-services/my-subscriptions-page-report-manager.md) to access all your subscriptions in one place or the [New Subscription or Edit Subscription Page &#40;Report Manager&#41;](../../2014/reporting-services/new-subscription-or-edit-subscription-page-report-manager.md) to create or edit a subscription.</span></span>  
  
 <span data-ttu-id="105d6-108">Некоторые параметры видимы только при наличии существующих подписок, с которыми можно работать.</span><span class="sxs-lookup"><span data-stu-id="105d6-108">Some options are visible only if there are existing subscriptions to work with.</span></span> <span data-ttu-id="105d6-109">Если ни одна подписка не определена и эта страница открывается из отчета, то единственными элементами на странице будут **Создать подписку** и **Создать управляемую данными подписку** .</span><span class="sxs-lookup"><span data-stu-id="105d6-109">If no subscriptions are defined and you are accessing this page from a report, the **New Subscription** and **New Data-Driven Subscription** are the only options on the page.</span></span>  
  
 <span data-ttu-id="105d6-110">Прежде чем создать новую подписку, убедитесь в том, что источник данных отчета использует сохраненные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="105d6-110">Before you can create a new subscription, you must verify that the report data source uses stored credentials.</span></span> <span data-ttu-id="105d6-111">Используйте страницу свойств «Источники данных», чтобы сохранить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="105d6-111">Use the Data Sources properties page to store credentials.</span></span> <span data-ttu-id="105d6-112">Дополнительные сведения см. на [странице свойств источников данных &#40;диспетчер отчетов&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="105d6-112">For more information, see [Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="105d6-113">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="105d6-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="105d6-114">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="105d6-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="105d6-115">Навигация</span><span class="sxs-lookup"><span data-stu-id="105d6-115">Navigation</span></span>  
 <span data-ttu-id="105d6-116">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="105d6-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-subscriptions-page-for-report"></a><span data-ttu-id="105d6-117">Открытие страницы «Подписки» отчета</span><span class="sxs-lookup"><span data-stu-id="105d6-117">To open the Subscriptions page for report</span></span>  
  
1.  <span data-ttu-id="105d6-118">Откройте диспетчер отчетов и найдите отчет, для которого необходимо просмотреть или настроить подписку.</span><span class="sxs-lookup"><span data-stu-id="105d6-118">Open Report Manager, and locate the report for which you want to view or configure a subscription.</span></span>  
  
2.  <span data-ttu-id="105d6-119">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="105d6-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="105d6-120">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="105d6-120">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="105d6-121">Откроется страница свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="105d6-121">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="105d6-122">Выберите вкладку **Подписки** .</span><span class="sxs-lookup"><span data-stu-id="105d6-122">Select the **Subscriptions** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="105d6-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="105d6-123">Options</span></span>  
 <span data-ttu-id="105d6-124">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="105d6-124">**Delete**</span></span>  
 <span data-ttu-id="105d6-125">Нажмите кнопку, чтобы удалить подписку.</span><span class="sxs-lookup"><span data-stu-id="105d6-125">Click to delete a subscription.</span></span> <span data-ttu-id="105d6-126">Прежде чем можно будет удалить подписку, установите флажок рядом с каждой подпиской, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="105d6-126">Before you can delete a subscription, select the check box next to each subscription that you want to delete.</span></span>  
  
 <span data-ttu-id="105d6-127">**Создать подписку**</span><span class="sxs-lookup"><span data-stu-id="105d6-127">**New Subscription**</span></span>  
 <span data-ttu-id="105d6-128">Нажмите кнопку, чтобы создать новую подписку на текущий отчет.</span><span class="sxs-lookup"><span data-stu-id="105d6-128">Click to create a new subscription to the current report.</span></span> <span data-ttu-id="105d6-129">Эта кнопка включена, когда в отчете используются сохраненные учетные данные или учетные данные не используются.</span><span class="sxs-lookup"><span data-stu-id="105d6-129">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="105d6-130">Эта кнопка недоступна при открытии страницы «Подписки» общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="105d6-130">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="105d6-131">**Создать управляемую данными подписку**</span><span class="sxs-lookup"><span data-stu-id="105d6-131">**New Data-Driven Subscription**</span></span>  
 <span data-ttu-id="105d6-132">Нажмите кнопку, чтобы сформировать список подписчиков и параметры доставки из команды или запроса к хранилищу данных, содержащего эти сведения.</span><span class="sxs-lookup"><span data-stu-id="105d6-132">Click to generate a subscriber list and delivery options from a command or query against a data store that contains this information.</span></span> <span data-ttu-id="105d6-133">Эта кнопка включена, когда в отчете используются сохраненные учетные данные или учетные данные не используются.</span><span class="sxs-lookup"><span data-stu-id="105d6-133">This button is enabled when the report uses stored credentials or no credentials.</span></span> <span data-ttu-id="105d6-134">Эта кнопка недоступна при открытии страницы «Подписки» общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="105d6-134">This button is not available when you open the Subscriptions page for a shared data source.</span></span>  
  
 <span data-ttu-id="105d6-135">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="105d6-135">**Edit**</span></span>  
 <span data-ttu-id="105d6-136">Щелкните, чтобы просмотреть или изменить описание.</span><span class="sxs-lookup"><span data-stu-id="105d6-136">Click to view or edit the description.</span></span>  
  
 <span data-ttu-id="105d6-137">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="105d6-137">**Report**</span></span>  
 <span data-ttu-id="105d6-138">При открытии этой страницы из общего источника данных этот столбец указывает на отчет, для которого определена подписка.</span><span class="sxs-lookup"><span data-stu-id="105d6-138">When you open this page from a shared data source, this column identifies the report for which the subscription is defined.</span></span> <span data-ttu-id="105d6-139">Столбец **Папка** указывает местоположение отчета.</span><span class="sxs-lookup"><span data-stu-id="105d6-139">The **Folder** column identifies the location of the report.</span></span>  
  
 <span data-ttu-id="105d6-140">**Описание**</span><span class="sxs-lookup"><span data-stu-id="105d6-140">**Description**</span></span>  
 <span data-ttu-id="105d6-141">Показывает описание подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-141">Shows a description of the subscription.</span></span>  
  
 <span data-ttu-id="105d6-142">**Триггер**</span><span class="sxs-lookup"><span data-stu-id="105d6-142">**Trigger**</span></span>  
 <span data-ttu-id="105d6-143">Указывает критерии запуска подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-143">Identifies criteria that cause the subscription to run.</span></span> <span data-ttu-id="105d6-144">Триггер **TimedSubscription** основывается на расписании, определяющем время запуска подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-144">A **TimedSubscription** trigger is based on a schedule that defines when the subscription runs.</span></span> <span data-ttu-id="105d6-145">Триггер **SnapshotUpdated** основывается на обновлении, внесенном в моментальный снимок отчета.</span><span class="sxs-lookup"><span data-stu-id="105d6-145">A **SnapshotUpdated** trigger is based on an update to a report snapshot.</span></span>  
  
 <span data-ttu-id="105d6-146">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="105d6-146">**Owner**</span></span>  
 <span data-ttu-id="105d6-147">Показывает имя пользователя, создавшего подписку.</span><span class="sxs-lookup"><span data-stu-id="105d6-147">Shows the name of the user who created the subscription.</span></span>  
  
 <span data-ttu-id="105d6-148">**Последний запуск**</span><span class="sxs-lookup"><span data-stu-id="105d6-148">**Last Run**</span></span>  
 <span data-ttu-id="105d6-149">Показывает, когда была проведена последняя обработка подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-149">Shows the last time that the subscription was processed.</span></span>  
  
 <span data-ttu-id="105d6-150">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="105d6-150">**Status**</span></span>  
 <span data-ttu-id="105d6-151">Показывает состояние подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-151">Shows the status of the subscription.</span></span> <span data-ttu-id="105d6-152">Обычно в качестве значения состояния используется либо «Новая», либо дата и время последнего выполнения подписки.</span><span class="sxs-lookup"><span data-stu-id="105d6-152">Usually, the status value is either New or the date and time at which the subscription last ran.</span></span>  
  
 <span data-ttu-id="105d6-153">Значение состояния «Ошибочные данные» отображается в случае, когда подписка включает указатель на зашифрованные значения, которые больше не действительны (то есть на сохраненные учетные данные, использованные при выполнении отчета).</span><span class="sxs-lookup"><span data-stu-id="105d6-153">A status value of "Bad Data" occurs when the subscription includes a pointer to encrypted values that are no longer valid (that is, to the stored credentials used to run the report).</span></span> <span data-ttu-id="105d6-154">Существующие зашифрованные значения не могут быть использованы после того, как на сервере отчетов были созданы новые симметричные ключи для шифрования и дешифрования данных.</span><span class="sxs-lookup"><span data-stu-id="105d6-154">Existing encrypted values become unusable when the symmetric keys used to encrypt and decrypt data are recreated on the report server.</span></span>  
  
 <span data-ttu-id="105d6-155">Подписку нельзя обработать, если она деактивирована.</span><span class="sxs-lookup"><span data-stu-id="105d6-155">A subscription cannot be processed if it has been deactivated.</span></span> <span data-ttu-id="105d6-156">Для обновления подписки и перевода ее в исправное состояние откройте подписку, а затем сохраните ее.</span><span class="sxs-lookup"><span data-stu-id="105d6-156">To update the subscription and make it operational, open and then save the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105d6-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="105d6-157">See Also</span></span>  
 <span data-ttu-id="105d6-158">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="105d6-158">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="105d6-159">[Создание, изменение и удаление стандартных подписок &#40;Reporting Services в основном режиме&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span><span class="sxs-lookup"><span data-stu-id="105d6-159">[Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md) </span></span>  
 <span data-ttu-id="105d6-160">[Создание, изменение и удаление расписаний](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="105d6-160">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="105d6-161">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="105d6-161">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
