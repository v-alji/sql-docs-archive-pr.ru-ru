---
title: Устранение неполадок пакетов с помощью отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fc476ac-bd69-434e-9636-70776e0b3b6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b20d9c9c02af3f3df96e2ef46a7b25251793fa55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666120"
---
# <a name="troubleshooting-reports-for-package-execution"></a><span data-ttu-id="4344c-102">Устранение неполадок пакетов с помощью отчетов</span><span class="sxs-lookup"><span data-stu-id="4344c-102">Troubleshooting Reports for Package Execution</span></span>
  <span data-ttu-id="4344c-103">В текущем выпуске служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] доступны стандартные отчеты, упрощающие наблюдение за пакетами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , развернутых в каталоге служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , а также устранение неполадок с пакетами.</span><span class="sxs-lookup"><span data-stu-id="4344c-103">In the current release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to help you monitor and troubleshoot [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that have been deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span> <span data-ttu-id="4344c-104">Два из этих отчетов о пакетах позволяют просматривать состояние выполнения пакетов и выявлять причины ошибок выполнения.</span><span class="sxs-lookup"><span data-stu-id="4344c-104">Two of these package reports in particular help you to view package execution status and identify the cause of execution failures.</span></span>  
  
-   <span data-ttu-id="4344c-105">**Панель мониторинга служб Integration Services** . Этот отчет дает общее представление о выполнении всех пакетов в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] за последние 24 часа.</span><span class="sxs-lookup"><span data-stu-id="4344c-105">**Integration Services Dashboard** - This report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance in the past 24 hours.</span></span> <span data-ttu-id="4344c-106">Отчет включает такие сведения, как состояние, тип операции, имя пакета и др., по каждому из пакетов.</span><span class="sxs-lookup"><span data-stu-id="4344c-106">The report displays information such as Status, Operation Type, Package Name, etc., for each package.</span></span>  
  
     <span data-ttu-id="4344c-107">Время начала, время окончания и продолжительность можно интерпретировать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4344c-107">The Start Time, End Time, and Duration can be interpreted as follows:</span></span>  
  
    -   <span data-ttu-id="4344c-108">Если пакет еще выполняется, то продолжительность = текущее время – время начала</span><span class="sxs-lookup"><span data-stu-id="4344c-108">If the package is still running, then Duration = current time - Start Time</span></span>  
  
    -   <span data-ttu-id="4344c-109">Если пакет завершен, то продолжительность = время окончания – время начала</span><span class="sxs-lookup"><span data-stu-id="4344c-109">If the package has completed, then Duration = End Time - Start Time</span></span>  
  
     <span data-ttu-id="4344c-110">Для каждого пакета, который был запущен на сервере, панель мониторинга позволяет «укрупнить вид» и просмотреть подробные сведения об ошибках, которые могли возникнуть при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="4344c-110">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span> <span data-ttu-id="4344c-111">Например, нажмите кнопку **Общие сведения** , чтобы увидеть высокоуровневые сведения о состоянии выполняемых задач, или кнопку **Все сообщения** , чтобы увидеть подробные сообщения, которые были записаны в ходе выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="4344c-111">For example, click **Overview** to display a high-level overview of the status of the tasks in the execution, or **All Messages** to display the detailed messages that were captured as part of the package execution.</span></span>  
  
     <span data-ttu-id="4344c-112">Вы можете отфильтровать таблицу, отображенную на любой странице, нажав кнопку **Фильтр** и выбрав критерии фильтрации в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="4344c-112">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="4344c-113">Доступные условия фильтрации зависят от отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="4344c-113">The filter criteria available depends on the data being displayed.</span></span> <span data-ttu-id="4344c-114">Чтобы изменить порядок сортировки отчета, вы можете щелкнуть значок сортировки в диалоговом окне **Параметры фильтра** .</span><span class="sxs-lookup"><span data-stu-id="4344c-114">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
-   <span data-ttu-id="4344c-115">**Отчет "Активность — все выполнения"** . В этом отчете дается сводка всех выполнений служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сервере.</span><span class="sxs-lookup"><span data-stu-id="4344c-115">**Activity - All Executions Report** - This report displays a summary of all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="4344c-116">В сводке показываются данные о каждом выполнении: состояние, время начала и время окончания.</span><span class="sxs-lookup"><span data-stu-id="4344c-116">The summary displays information for each execution such as status, start time, and end time.</span></span> <span data-ttu-id="4344c-117">Каждая запись сводки содержит ссылки на дополнительные сведения о выполнении, включая сообщения, которые создаются во время выполнения, и данные о производительности.</span><span class="sxs-lookup"><span data-stu-id="4344c-117">Each summary entry includes links to more information about the execution including messages generated during execution and performance data.</span></span> <span data-ttu-id="4344c-118">Как и в отчете «Панель мониторинга служб Integration Services», здесь вы можете применить фильтр к таблице, чтобы сократить объем информации.</span><span class="sxs-lookup"><span data-stu-id="4344c-118">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4344c-119">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="4344c-119">Related Tasks</span></span>  
 [<span data-ttu-id="4344c-120">Просмотр отчетов для сервера служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="4344c-120">View Reports for the Integration Services Server</span></span>](../view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="4344c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4344c-121">Related Content</span></span>  
 [<span data-ttu-id="4344c-122">Отчеты для сервера Integration Services</span><span class="sxs-lookup"><span data-stu-id="4344c-122">Reports for the Integration Services Server</span></span>](../reports-for-the-integration-services-server.md)  
  
 [<span data-ttu-id="4344c-123">Устранение неполадок инструментов с помощью отчетов</span><span class="sxs-lookup"><span data-stu-id="4344c-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
