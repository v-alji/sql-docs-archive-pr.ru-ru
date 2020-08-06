---
title: Свойства сервера (страница "Журнал") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665229"
---
# <a name="server-properties-history-page"></a><span data-ttu-id="fef8a-102">Свойства сервера (страница «Журнал»)</span><span class="sxs-lookup"><span data-stu-id="fef8a-102">Server Properties (History Page)</span></span>
  <span data-ttu-id="fef8a-103">Используйте эту страницу для задания значения по умолчанию для количества сохраняемых копий журнала отчета.</span><span class="sxs-lookup"><span data-stu-id="fef8a-103">Use this page to set a default value for the number of copies of report history to retain.</span></span> <span data-ttu-id="fef8a-104">Значение по умолчанию предоставляет начальный параметр, который задает пределы объема журнала отчета для всех отчетов.</span><span class="sxs-lookup"><span data-stu-id="fef8a-104">The default value provides an initial setting that establishes report history limits for all reports.</span></span> <span data-ttu-id="fef8a-105">Эти настройки можно изменить для отдельных отчетов.</span><span class="sxs-lookup"><span data-stu-id="fef8a-105">You can vary these settings for individual reports.</span></span>  
  
 <span data-ttu-id="fef8a-106">Журнал отчета представляет собой коллекцию моментальных снимков отчета, включающих данные отчета и макет на момент создания моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="fef8a-106">Report history is a collection of report snapshots that include report data and layout that is current for the report at the time the snapshot is created.</span></span> <span data-ttu-id="fef8a-107">Журнал отчета можно использовать для сохранения копии отчета в том виде, какой он имел на конкретную дату и время.</span><span class="sxs-lookup"><span data-stu-id="fef8a-107">You can use report history to keep a copy of a report as it was on a specific date or time.</span></span> <span data-ttu-id="fef8a-108">Можно создавать и управлять журналом отчета для отдельных отчетов, выполняемых на сервере отчетов, работающем в собственном режиме, или на сервере отчетов, работающем в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fef8a-108">You can create and manage report history for individual reports that run on a native mode report server or a report server that is configured for SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="fef8a-109">Моментальные снимки журнала отчета хранятся в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="fef8a-109">Report history snapshots are stored in the report server database.</span></span> <span data-ttu-id="fef8a-110">Если количество хранимых моментальных снимков не ограничено, то следует периодически проверять размер базы данных, чтобы убедиться в том, что она не увеличивается слишком быстро и не занимает чрезмерно большой объем дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="fef8a-110">If you keep an unlimited number of snapshots, be sure to periodically check the database size to ensure it is not growing too fast or consuming too much disk space.</span></span>  
  
 <span data-ttu-id="fef8a-111">Чтобы открыть эту страницу, в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру сервера отчетов, щелкните его правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fef8a-111">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="fef8a-112">Нажмите кнопку **Журнал** , чтобы открыть эту страницу.</span><span class="sxs-lookup"><span data-stu-id="fef8a-112">Click **History** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fef8a-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="fef8a-113">Options</span></span>  
 <span data-ttu-id="fef8a-114">**Хранить в журнале отчета неограниченное количество моментальных снимков**</span><span class="sxs-lookup"><span data-stu-id="fef8a-114">**Keep an unlimited number of snapshots in report history**</span></span>  
 <span data-ttu-id="fef8a-115">Сохранение всех моментальных снимков журнала отчета.</span><span class="sxs-lookup"><span data-stu-id="fef8a-115">Retain all report history snapshots.</span></span> <span data-ttu-id="fef8a-116">Для уменьшения размера журнала отчетов моментальные снимки нужно удалять вручную.</span><span class="sxs-lookup"><span data-stu-id="fef8a-116">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
 <span data-ttu-id="fef8a-117">**Ограничить количество копий журнала отчета**</span><span class="sxs-lookup"><span data-stu-id="fef8a-117">**Limit the copies of report history**</span></span>  
 <span data-ttu-id="fef8a-118">Сохранение заданного количества моментальных снимков журнала отчета.</span><span class="sxs-lookup"><span data-stu-id="fef8a-118">Retain a set number of report history snapshots.</span></span> <span data-ttu-id="fef8a-119">По достижении предела старые копии будут удаляться из журнала отчетов, чтобы освободить место для новых.</span><span class="sxs-lookup"><span data-stu-id="fef8a-119">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="fef8a-120">Если объем журнала отчета будет ограничен позже, при превышении указанного предела объема существующего журнала отчета сервер отчетов сокращает объем журнала до нового предела.</span><span class="sxs-lookup"><span data-stu-id="fef8a-120">If you limit report history later, when the existing report history exceeds the limit you specify, the report server reduces the existing report history to the new limit.</span></span> <span data-ttu-id="fef8a-121">Первыми удаляются наиболее старые моментальные снимки отчетов.</span><span class="sxs-lookup"><span data-stu-id="fef8a-121">The oldest report snapshots are deleted first.</span></span> <span data-ttu-id="fef8a-122">Если журнал отчетов отсутствует или его объем меньше заданного предела, добавляются новые моментальные снимки отчетов.</span><span class="sxs-lookup"><span data-stu-id="fef8a-122">If report history is empty or below the limit, new report snapshots are added.</span></span> <span data-ttu-id="fef8a-123">По достижении предела при добавлении новых моментальных снимков отчетов удаляются наиболее старые моментальные снимки.</span><span class="sxs-lookup"><span data-stu-id="fef8a-123">When the limit is reached, the oldest snapshot is deleted when a new report snapshot is added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef8a-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="fef8a-124">See Also</span></span>  
 <span data-ttu-id="fef8a-125">[Установка свойств сервера отчетов &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="fef8a-125">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="fef8a-126">[Соединение с сервером отчетов в Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="fef8a-126">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="fef8a-127">Справка F1 по использованию сервера отчетов среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="fef8a-127">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
