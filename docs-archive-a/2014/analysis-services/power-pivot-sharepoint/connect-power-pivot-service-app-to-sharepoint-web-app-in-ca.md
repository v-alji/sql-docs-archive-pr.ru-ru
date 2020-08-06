---
title: Подключение приложения службы PowerPivot к веб-приложению SharePoint в центре администрирования | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5da8e29-7ffd-44e7-bf61-344fa5bea8ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5fc6dcde4cc2d18c3650adbab0ec71ef5c6265cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666805"
---
# <a name="connect-a-powerpivot-service-application-to-a-sharepoint-web-application-in-central-administration"></a><span data-ttu-id="f7e57-102">Подключение приложения службы PowerPivot к веб-приложению SharePoint в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="f7e57-102">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>
  <span data-ttu-id="f7e57-103">Приложение службы PowerPivot может быть использовано неограниченным числом веб-приложений SharePoint в ферме.</span><span class="sxs-lookup"><span data-stu-id="f7e57-103">A PowerPivot service application can be used by any number of SharePoint Web applications in the farm.</span></span> <span data-ttu-id="f7e57-104">Чтобы приложение службы PowerPivot стало доступным, его необходимо добавить в список ассоциаций служб.</span><span class="sxs-lookup"><span data-stu-id="f7e57-104">To make a PowerPivot service application available, you add it to a service association list.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f7e57-105">Наличие приложения службы PowerPivot в группе ассоциаций по умолчанию необходимо для правильной работы панели управления PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f7e57-105">You must have one PowerPivot service application in the default group to ensure that PowerPivot Management Dashboard works properly.</span></span> <span data-ttu-id="f7e57-106">Не добавляйте в группу по умолчанию более одного приложения службы PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f7e57-106">Do not add more than one PowerPivot service application to the default group.</span></span> <span data-ttu-id="f7e57-107">Добавление нескольких записей приложений службы одного типа не поддерживается, это может привести к возникновению ошибок.</span><span class="sxs-lookup"><span data-stu-id="f7e57-107">Adding multiple entries of the same service application type is not a supported configuration and might cause errors.</span></span> <span data-ttu-id="f7e57-108">При создании дополнительных приложений службы добавляйте их в пользовательский список.</span><span class="sxs-lookup"><span data-stu-id="f7e57-108">If you are creating additional service applications, add them to custom lists.</span></span>  
  
 <span data-ttu-id="f7e57-109">Этот раздел состоит из следующих подразделов.</span><span class="sxs-lookup"><span data-stu-id="f7e57-109">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="f7e57-110">Добавление приложения службы PowerPivot в группу по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f7e57-110">Add PowerPivot Services Application to the Default Group</span></span>](#default)  
  
 [<span data-ttu-id="f7e57-111">Добавление приложения службы PowerPivot в пользовательский список ассоциаций служб</span><span class="sxs-lookup"><span data-stu-id="f7e57-111">Add PowerPivot Services Application a Custom Service Association List</span></span>](#custom)  
  
##  <a name="add-powerpivot-services-application-to-the-default-group"></a><a name="default"></a><span data-ttu-id="f7e57-112">Добавление приложения служб PowerPivot в группу по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f7e57-112">Add PowerPivot Services Application to the Default Group</span></span>  
 <span data-ttu-id="f7e57-113">Список ассоциаций служб представляет собой список общих служб, предоставляющих ресурсы для других веб-приложений SharePoint в ферме.</span><span class="sxs-lookup"><span data-stu-id="f7e57-113">A service association list is a list of shared services that provide resources to other SharePoint Web applications in the farm.</span></span> <span data-ttu-id="f7e57-114">В ферме может быть только одна группа ассоциаций служб по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f7e57-114">There is one default group of service associations for the farm.</span></span>  
  
 <span data-ttu-id="f7e57-115">Приложение службы PowerPivot можно добавить в список как при создании, так и после него, выполнив следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f7e57-115">To be on the list, a PowerPivot service application can either be added when you create the application or afterwards by using the following steps.</span></span>  
  
1.  <span data-ttu-id="f7e57-116">В центре администрирования в разделе **Управление приложениями**выберите пункт **Настройка связей для приложений-служб**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-116">In Central Administration, in **Application Management**, click **Configure service application associations**.</span></span>  
  
2.  <span data-ttu-id="f7e57-117">В разделе "Группа прокси-серверов приложения" выберите **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-117">In Application Proxy Group, click **default**.</span></span>  
  
3.  <span data-ttu-id="f7e57-118">Выберите флажок рядом с приложением службы PowerPivot (указано именем типа `PowerPivot Service Application Proxy`).</span><span class="sxs-lookup"><span data-stu-id="f7e57-118">Select the checkbox next to the PowerPivot service application (indicated by type name `PowerPivot Service Application Proxy`).</span></span> <span data-ttu-id="f7e57-119">Если есть более одного приложения служб PowerPivot, надо выбрать только одно.</span><span class="sxs-lookup"><span data-stu-id="f7e57-119">If you have more than one PowerPivot service application, choose just one.</span></span>  
  
4.  <span data-ttu-id="f7e57-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-120">Click **OK**.</span></span>  
  
##  <a name="add-powerpivot-services-application-a-custom-service-association-list"></a><a name="custom"></a><span data-ttu-id="f7e57-121">Добавление приложения служб PowerPivot в настраиваемый список ассоциаций служб</span><span class="sxs-lookup"><span data-stu-id="f7e57-121">Add PowerPivot Services Application a Custom Service Association List</span></span>  
 <span data-ttu-id="f7e57-122">Группа по умолчанию может быть заменена пользовательским списком.</span><span class="sxs-lookup"><span data-stu-id="f7e57-122">The default group can be replaced by a custom list.</span></span> <span data-ttu-id="f7e57-123">Пользовательский список создается специально для единичного веб-приложения SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f7e57-123">A custom list is created specifically for a single SharePoint Web application.</span></span> <span data-ttu-id="f7e57-124">Он переопределяет группу по умолчанию и заменяет ее только для тех ассоциаций, которые были указаны администратором фермы или службы.</span><span class="sxs-lookup"><span data-stu-id="f7e57-124">It overrides the default group and replaces it with only those service associations that a farm or service administrator specifies.</span></span> <span data-ttu-id="f7e57-125">Если было создано несколько приложений службы PowerPivot, то необходимо выбрать приложение из пользовательского списка.</span><span class="sxs-lookup"><span data-stu-id="f7e57-125">If you created multiple PowerPivot service applications, you must use a custom list to specify which one to use.</span></span> <span data-ttu-id="f7e57-126">Пользовательский список не может быть повторно использован другими веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="f7e57-126">A custom list cannot be reused by other Web applications.</span></span> <span data-ttu-id="f7e57-127">Он применяется только для тех веб-приложений, для которых он был создан.</span><span class="sxs-lookup"><span data-stu-id="f7e57-127">It applies only to the Web application for which it was created.</span></span>  
  
1.  <span data-ttu-id="f7e57-128">В разделе **Управление приложениями**центра администрирования выберите **Управление веб-приложениями**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-128">In Central Administration, in **Application Management**, click **Manage web applications**.</span></span>  
  
2.  <span data-ttu-id="f7e57-129">Выберите приложение (например, SharePoint 80).</span><span class="sxs-lookup"><span data-stu-id="f7e57-129">Select the application (for example, SharePoint -80).</span></span>  
  
3.  <span data-ttu-id="f7e57-130">В разделе "Веб-приложения" на вкладке "Управление" выберите **Соединения службы**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-130">In Web Applications, in Manage, click **Service Connections**.</span></span>  
  
4.  <span data-ttu-id="f7e57-131">В списке **Изменить следующую группу соединений**выберите **[пользовательское]**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-131">In **Edit the following group of connections**, select **[custom]**.</span></span>  
  
5.  <span data-ttu-id="f7e57-132">Установите флажки для всех соединений приложений служб, которые будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="f7e57-132">Select the checkbox next to each service application connection you want to use.</span></span> <span data-ttu-id="f7e57-133">Если есть несколько приложений службы PowerPivot (обозначены типом `PowerPivot Service Application Proxy`), то должно быть выбрано только одно.</span><span class="sxs-lookup"><span data-stu-id="f7e57-133">If you have multiple PowerPivot service applications (indicated by Type set to `PowerPivot Service Application Proxy`), be sure to choose only one.</span></span>  
  
6.  <span data-ttu-id="f7e57-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f7e57-134">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e57-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7e57-135">See Also</span></span>  
 <span data-ttu-id="f7e57-136">[Создание и настройка приложения службы PowerPivot в центре администрирования](create-and-configure-power-pivot-service-application-in-ca.md) </span><span class="sxs-lookup"><span data-stu-id="f7e57-136">[Create and Configure a PowerPivot Service Application in Central Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span></span>  
 [<span data-ttu-id="f7e57-137">PowerPivot для SharePoint &#40;начальной конфигурации&#41;</span><span class="sxs-lookup"><span data-stu-id="f7e57-137">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
  
