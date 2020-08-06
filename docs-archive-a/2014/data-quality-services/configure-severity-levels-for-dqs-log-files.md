---
title: Настройка уровней серьезности для файлов журнала DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.log.f1
helpviewer_keywords:
- severity levels
- log files,severity levels
- dqs log files,severity levels
- logging,severity levels
- configure severity levels
ms.assetid: 66ffcdec-4bf7-4dd5-a221-fd9baefeeef4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 46fb9de1fbe1e3e59b20bb2ac7afeebe19ba2da5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728730"
---
# <a name="configure-severity-levels-for-dqs-log-files"></a><span data-ttu-id="b0ec8-102">Настройка степеней серьезности для файлов журнала DQS</span><span class="sxs-lookup"><span data-stu-id="b0ec8-102">Configure Severity Levels for DQS Log Files</span></span>
  <span data-ttu-id="b0ec8-103">В данном разделе описывается, как настраивать степени серьезности для различных операций и модулей в службе [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) при помощи [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0ec8-103">This topic describes how to configure severity levels for various activities and modules in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="b0ec8-104">Степени серьезности определяют интенсивность событий, которые происходят в DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-104">Severity levels define the intensity of events that occur in DQS.</span></span> <span data-ttu-id="b0ec8-105">События DQS имеют следующие степени серьезности, в порядке убывания серьезности:</span><span class="sxs-lookup"><span data-stu-id="b0ec8-105">DQS events have the following severity levels, in the decreasing order of severity:</span></span>  
  
-   <span data-ttu-id="b0ec8-106">**Неустранимая ошибка**. Критические ошибки времени выполнения, которые могут привести к серьезным/непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-106">**Fatal**: Critical runtime errors that might cause severe/unexpected results.</span></span>  
  
-   <span data-ttu-id="b0ec8-107">**Ошибка**. Другие ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-107">**Error**: Other runtime errors.</span></span>  
  
-   <span data-ttu-id="b0ec8-108">**Предупреждение**. Предупреждение о событиях, которые могут привести к возникновению ошибки.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-108">**Warn**: Warning about events that might result in an error.</span></span>  
  
-   <span data-ttu-id="b0ec8-109">**Информация**. Сведения об общих событиях, которые не являются ни ошибкой, ни предупреждением.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-109">**Info**: Information about general events that is not an error or a warning.</span></span> <span data-ttu-id="b0ec8-110">К примеру, запущен процесс DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-110">For example, a DQS process has started.</span></span>  
  
-   <span data-ttu-id="b0ec8-111">**Отладка**. Подробные (детальные) сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-111">**Debug**: Detailed (verbose) information about the event.</span></span>  
  
 <span data-ttu-id="b0ec8-112">С помощью настройки степеней серьезности для различных операций и модулей DQS осуществляется фильтрация сведений, которые необходимо записать в журнал, и запись в файл журнала DQS для соответствующей операции или модуля DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-112">By configuring severity levels for various DQS activities and modules, you are filtering the information that you want to be logged, and written to the DQS log file for the respective DQS activity or module.</span></span> <span data-ttu-id="b0ec8-113">Например, при установке степени серьезности **Предупреждение**для операции DQS в журнал будут записаны только предупреждения и сообщения более высокой серьезности («Ошибка» или «Неустранимая ошибка»), связанные с операциями DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-113">For example, if you set the severity level of a DQS activity to **Warn**, only warning and higher severity messages (Error and Fatal) associated with the DQS activity will be logged.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b0ec8-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b0ec8-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b0ec8-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="b0ec8-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b0ec8-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="b0ec8-116">Permissions</span></span>  
 <span data-ttu-id="b0ec8-117">Для настройки параметров серьезности для записи в журнал необходимо иметь роль dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-117">You must have the dqs_administrator role on the DQS_MAIN database to configure log severity settings.</span></span>  
  
##  <a name="configure-severity-levels-at-activity-level"></a><a name="ConfigureActivity"></a><span data-ttu-id="b0ec8-118">Настройка степени серьезности на уровне действия</span><span class="sxs-lookup"><span data-stu-id="b0ec8-118">Configure Severity Levels at Activity Level</span></span>  
 <span data-ttu-id="b0ec8-119">Можно настроить параметры серьезности записи в журнал для следующих операций в DQS: управление доменами, обнаружение знаний, политика сопоставления, очистка данных, сопоставление данных и службы ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-119">You can configure log severity settings for the following activities in DQS: domain management, knowledge discovery, matching policy, data cleansing, data matching, and reference data services.</span></span> <span data-ttu-id="b0ec8-120">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-120">To do so:</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="b0ec8-121">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="b0ec8-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="b0ec8-122">На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="b0ec8-123">Затем перейдите на вкладку **Параметры журнала** . Перечислены следующие действия DQS, для которых можно выбрать уровень серьезности: **Управление доменами**, **Обнаружение знаний**, **проект очистки (например, RDS)**, **Политика сопоставления и проект сопоставления**, а также **RDS**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-123">Next, click the **Log Settings** tab. The following DQS activities are listed for which you can select a severity level: **Domain Management**, **Knowledge Discovery**, **Cleansing Project (Ex. RDS)**, **Matching Policy and Matching Project**, and **RDS**.</span></span>  
  
4.  <span data-ttu-id="b0ec8-124">Для операции DQS выберите степень серьезности для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-124">For a DQS activity, select the severity level that you want to be logged.</span></span> <span data-ttu-id="b0ec8-125">Вы можете выбрать один из следующих вариантов: **Неустранимая ошибка**, **Ошибка**, **Предупреждение**, **Информация**и **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-125">You can select one among the following: **Fatal**, **Error**, **Warn**, **Info**, and **Debug**.</span></span> <span data-ttu-id="b0ec8-126">К примеру, при необходимости записи в файлы журнала DQS только сообщений о неустранимых ошибках для операции обнаружения знаний выберите в раскрывающемся списке параметр **Неустранимая ошибка** напротив действия **Обнаружение знаний** .</span><span class="sxs-lookup"><span data-stu-id="b0ec8-126">For example, if you want only fatal messages to be written to the DQS log files for the knowledge discovery activity, select **Fatal** in the drop-down list against the **Knowledge Discovery** activity.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0ec8-127">По умолчанию для всех операций установлена степень серьезности **Ошибка** .</span><span class="sxs-lookup"><span data-stu-id="b0ec8-127">By default, **Error** is selected for each of the activities.</span></span> <span data-ttu-id="b0ec8-128">Это означает, что по умолчанию для всех операций в файлы журнала DQS будут записываться сообщения об ошибках и неустранимых ошибках.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-128">This implies that error and fatal messages will be written to the DQS log files for each activity, by default.</span></span>  
  
5.  <span data-ttu-id="b0ec8-129">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-129">Click **Close**.</span></span>  
  
##  <a name="configure-severity-levels-at-module-level-advanced"></a><a name="ConfigureModule"></a><span data-ttu-id="b0ec8-130">Настройка степени серьезности на уровне модуля (дополнительно)</span><span class="sxs-lookup"><span data-stu-id="b0ec8-130">Configure Severity Levels at Module Level (Advanced)</span></span>  
 <span data-ttu-id="b0ec8-131">Выполнить настройку параметров серьезности записи в журнал на уровне модуля можно в разделе **Дополнительно** на вкладке **Параметры журнала** .</span><span class="sxs-lookup"><span data-stu-id="b0ec8-131">The **Advanced** section in the **Log Settings** tab enables you to configure log severity settings at a module level.</span></span> <span data-ttu-id="b0ec8-132">Модули являются системными сборками DQS, которые реализуют различные функциональные возможности в функции DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-132">Modules are DQS system assemblies that implement various functionalities within a feature in DQS.</span></span> <span data-ttu-id="b0ec8-133">Например, операция управления доменами содержит различные функциональные возможности такие, как правила определения доменов, условия определения правил, правила определения нескольких доменов для составных доменов и т. д.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-133">For example, the domain management activity contains various functionalities such as defining domain rules, defining rule conditions, defining cross-domain rules for composite domains, and so on.</span></span>  
  
 <span data-ttu-id="b0ec8-134">Иногда недостаточно уровня гранулярности на уровне активности.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-134">At times, the granularity level at the activity level is not sufficient.</span></span> <span data-ttu-id="b0ec8-135">Может появиться необходимость исследования проблемы, возникающей в конкретном модуле операции.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-135">You might want to investigate an issue that is occurring in a particular module within an activity.</span></span> <span data-ttu-id="b0ec8-136">Что дает возможность настройки параметров серьезности для записи в журнал на уровне модуля в целях более точной локализации и отслеживания проблемы.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-136">It helps to have an option to configure log severities at the module level to isolate and track the issue more precisely.</span></span>  
  
 <span data-ttu-id="b0ec8-137">Параметр серьезности для записи в журнал, определенный на уровне активности, определяет параметр серьезности для записи в журнал всех модулей, составляющих операцию.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-137">The log severity setting specified at the activity level determines the log severity setting of all the modules that constitute the activity.</span></span> <span data-ttu-id="b0ec8-138">Однако при возникновении любого конфликта между параметрами серьезности для записи в журнал на уровне действия и на уровне модуля рассматриваются параметры серьезности на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-138">However, if there is any conflict between the log severity settings at the activity and module levels, the severity settings at the module level are considered.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="b0ec8-139">По умолчанию модуль **Microsoft.Ssdqs.Core.Startup** предварительно настроен в разделе **Дополнительно** со степенью серьезности установленной в значение **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-139">By default, the **Microsoft.Ssdqs.Core.Startup** module is preconfigured in the **Advanced** section with the severity level set as **Info**.</span></span> <span data-ttu-id="b0ec8-140">Это делается для включения записи в журнал событий со степенью серьезности «Сведения» и выше («Предупреждение», «Ошибка» «Неустранимая ошибка»), связанных с запуском и остановкой служб DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-140">This is done to enable logging of events of severity Info and higher (Warn, Error, and Fatal) that are related to starting and stopping of DQS services.</span></span>  
> -   <span data-ttu-id="b0ec8-141">Настраивать степени серьезности для записи в журнал на уровне модуля необходимо только в том случае, если вы являетесь опытным пользователем служб DQS, знакомым с системными сборками DQS.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-141">You should configure log severity levels at the module level only if you are an advanced DQS user who is familiar with the DQS system assemblies.</span></span>  
  
 <span data-ttu-id="b0ec8-142">Настройка степени серьезности для записи в журнал на уровне модуля</span><span class="sxs-lookup"><span data-stu-id="b0ec8-142">To configure log severity levels at the module level:</span></span>  
  
1.  <span data-ttu-id="b0ec8-143">На вкладке **Параметры журнала** щелкните стрелку вниз возле **Дополнительно** для отображения области.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-143">In the **Log Settings** tab, click the down arrow against **Advanced** to display the area.</span></span>  
  
2.  <span data-ttu-id="b0ec8-144">В появившейся сетке выберите имя модуля из раскрывающегося списка в столбце **Модуль** .</span><span class="sxs-lookup"><span data-stu-id="b0ec8-144">In the grid that appears, select a module name from the drop-down list in the **Module** column.</span></span>  
  
3.  <span data-ttu-id="b0ec8-145">Затем выберите из раскрывающегося списка степень серьезности для модуля в столбце **Серьезность** .</span><span class="sxs-lookup"><span data-stu-id="b0ec8-145">Next, select a severity level for the module from the drop-down list in the **Severity** column.</span></span> <span data-ttu-id="b0ec8-146">Вы можете выбрать один из следующих вариантов: **Неустранимая ошибка**, **Ошибка**, **Предупреждение**, **Информация**и **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-146">You can select one among the following: **Fatal**, **Error**, **Warn**, **Info**, and **Debug**.</span></span>  
  
     <span data-ttu-id="b0ec8-147">К примеру, для действия управления доменами можно установить другой уровень гранулярности для функциональной возможности определения правила домена, чем операция управления доменами, выбрав модуль **Microsoft.Ssdqs.DomainRules.Define** и другая степень серьезности для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-147">For example, within the domain management activity, you can set a different granularity level for the domain rule definition functionality than the domain management activity by selecting the **Microsoft.Ssdqs.DomainRules.Define** module, and selecting a different log severity level.</span></span> <span data-ttu-id="b0ec8-148">Аналогичным образом вы можете установить другой уровень гранулярности для функциональной возможности определения правила нескольких доменов, выбрав модуль **Microsoft.Ssdqs.DomainRules.Condition.CrossDomain** и другую степень серьезности для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-148">Similarly, you can set a different granularity level for the cross-domain rule functionality by selecting the **Microsoft.Ssdqs.DomainRules.Condition.CrossDomain** module, and selecting a different log severity level.</span></span>  
  
4.  <span data-ttu-id="b0ec8-149">При необходимости повторите шаги 2 и 3 для других модулей.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-149">Repeat steps 2 and 3 for other modules, if required.</span></span> <span data-ttu-id="b0ec8-150">Кроме того, можно добавлять или удалять строки из сетки с помощью значков **Добавить модуль** и **Удалить модуль** .</span><span class="sxs-lookup"><span data-stu-id="b0ec8-150">You can also add or delete rows to the grid by clicking the **Add Module** and **Remove Module** icons.</span></span>  
  
5.  <span data-ttu-id="b0ec8-151">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b0ec8-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ec8-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0ec8-152">See Also</span></span>  
 [<span data-ttu-id="b0ec8-153">Configure Advanced Settings for DQS Log Files</span><span class="sxs-lookup"><span data-stu-id="b0ec8-153">Configure Advanced Settings for DQS Log Files</span></span>](../../2014/data-quality-services/configure-advanced-settings-for-dqs-log-files.md)  
  
  
