---
title: Создание журнала отчета (службы Reporting Services в режиме интеграции с SharePoint) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], SharePoint
ms.assetid: e57ec746-05ae-4ff6-8e39-6cde87310daa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 996202580bbacc24080460c2c43218db27294d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665799"
---
# <a name="create-report-history-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="6613d-102">создать журнал отчета (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6613d-102">Create Report History (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="6613d-103">Журнал отчета — это коллекция моментальных снимков отчета, созданных на протяжении определенного времени.</span><span class="sxs-lookup"><span data-stu-id="6613d-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="6613d-104">Каждый моментальный снимок представляет собой копию отчета в том виде, в котором он был создан.</span><span class="sxs-lookup"><span data-stu-id="6613d-104">Each snapshot is a copy of the report as it existed when it was created.</span></span> <span data-ttu-id="6613d-105">Он включает в себя макет и данные, являвшиеся текущими во время создания моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="6613d-105">It includes the layout and data that was current for the report when the snapshot was created.</span></span> <span data-ttu-id="6613d-106">Сведения о подготовке к просмотру не хранятся вместе с моментальным снимком.</span><span class="sxs-lookup"><span data-stu-id="6613d-106">Rendering information is not stored with the snapshot.</span></span> <span data-ttu-id="6613d-107">При открытии моментального снимка журнала отчета, он открывается в виде HTML-документа в веб-части «Средство просмотра отчетов».</span><span class="sxs-lookup"><span data-stu-id="6613d-107">When you open a snapshot in report history, it opens in HTML in the Report Viewer Web Part.</span></span> <span data-ttu-id="6613d-108">После завершения подготовки к просмотру отчет можно экспортировать в форматы других приложений.</span><span class="sxs-lookup"><span data-stu-id="6613d-108">After it is rendered, you can export it to other application formats.</span></span>  
  
 <span data-ttu-id="6613d-109">Чтобы создать журнал отчета, отчет должен иметь возможность запуска в автоматическом режиме (сервер отчетов должен иметь возможность запустить отчет без взаимодействия с пользователем).</span><span class="sxs-lookup"><span data-stu-id="6613d-109">To create report history, the report must be able to run unattended (that is, the report server must be able to run the report without user interaction).</span></span> <span data-ttu-id="6613d-110">Необходимо иметь разрешение на изменение элементов библиотеки, в которой содержится отчет.</span><span class="sxs-lookup"><span data-stu-id="6613d-110">You must have Edit Items permission on the library that contains the report.</span></span> <span data-ttu-id="6613d-111">Для просмотра или удаления журнала отчета необходимо иметь разрешение на просмотр или удаление версий.</span><span class="sxs-lookup"><span data-stu-id="6613d-111">To view or delete report history, you must have View Versions or Delete Versions permissions.</span></span>  
  
### <a name="to-create-a-snapshot-or-report-history-on-demand"></a><span data-ttu-id="6613d-112">Создание моментального снимка или журнала отчета по требованию</span><span class="sxs-lookup"><span data-stu-id="6613d-112">To create a snapshot or report history on demand</span></span>  
  
1.  <span data-ttu-id="6613d-113">Укажите отчет.</span><span class="sxs-lookup"><span data-stu-id="6613d-113">Point to the report.</span></span>  
  
2.  <span data-ttu-id="6613d-114">Для отображения щелкните стрелку вниз и выберите **Просмотр журнала отчета**.</span><span class="sxs-lookup"><span data-stu-id="6613d-114">Click to display the down arrow, and then select **View Report History**.</span></span>  
  
3.  <span data-ttu-id="6613d-115">Выберите **Создать моментальный снимок**.</span><span class="sxs-lookup"><span data-stu-id="6613d-115">Click **New Snapshot**.</span></span> <span data-ttu-id="6613d-116">Если эта кнопка не видна, то у вас нет разрешения на создание моментальных снимков в журнале отчета.</span><span class="sxs-lookup"><span data-stu-id="6613d-116">If the button is not visible, it is because you do not have permission to create snapshots in report history.</span></span>  
  
4.  <span data-ttu-id="6613d-117">Для просмотра вновь созданного моментального снимка выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="6613d-117">To view the snapshot you just created, select it from the list.</span></span> <span data-ttu-id="6613d-118">Каждый моментальный снимок снабжен отметкой времени, которая показывает, когда он был сделан.</span><span class="sxs-lookup"><span data-stu-id="6613d-118">Each snapshot is identified by a timestamp that shows when the snapshot was created.</span></span> <span data-ttu-id="6613d-119">Переименование моментальных снимков, перемещение их в другое место или изменение не допускается.</span><span class="sxs-lookup"><span data-stu-id="6613d-119">You cannot rename the snapshot, move it to another location, or modify it.</span></span>  
  
### <a name="to-schedule-report-history"></a><span data-ttu-id="6613d-120">Планирование журнала отчета</span><span class="sxs-lookup"><span data-stu-id="6613d-120">To schedule report history</span></span>  
  
1.  <span data-ttu-id="6613d-121">Укажите отчет.</span><span class="sxs-lookup"><span data-stu-id="6613d-121">Point to the report.</span></span>  
  
2.  <span data-ttu-id="6613d-122">Нажмите для отображения стрелку вниз и выберите **Управление параметрами обработки**.</span><span class="sxs-lookup"><span data-stu-id="6613d-122">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="6613d-123">В области **Параметры моментальных снимков в журнале**выберите **Создавать моментальные снимки журнала отчета по расписанию**.</span><span class="sxs-lookup"><span data-stu-id="6613d-123">In **History Snapshot Options**, click **Create report history snapshots on a schedule**.</span></span>  
  
4.  <span data-ttu-id="6613d-124">При работе с общим расписанием, содержащим сведения о расписании, которое нужно использовать, щелкните вариант **По общему расписанию** и выберите расписание, которое будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="6613d-124">If you have a shared schedule that contains the schedule information you want to use, click **On a shared schedule** and select the schedule you want to use.</span></span> <span data-ttu-id="6613d-125">В противном случае щелкните вариант **По нестандартному расписанию**и нажмите кнопку **Настройка** для указания параметров создания журнала отчета на основе регулярного расписания.</span><span class="sxs-lookup"><span data-stu-id="6613d-125">Otherwise, click **On a custom schedule**, and then click **Configure** to specify options to create report history on a recurring schedule.</span></span>  
  
### <a name="to-create-report-history-when-data-is-refreshed-in-a-report"></a><span data-ttu-id="6613d-126">Создание журнала отчета при обновлении данных отчета</span><span class="sxs-lookup"><span data-stu-id="6613d-126">To create report history when data is refreshed in a report</span></span>  
  
1.  <span data-ttu-id="6613d-127">Укажите отчет.</span><span class="sxs-lookup"><span data-stu-id="6613d-127">Point to the report.</span></span>  
  
2.  <span data-ttu-id="6613d-128">Нажмите для отображения стрелку вниз и выберите **Управление параметрами обработки**.</span><span class="sxs-lookup"><span data-stu-id="6613d-128">Click to display the down arrow, and then select **Manage Processing Options**.</span></span>  
  
3.  <span data-ttu-id="6613d-129">В области **Параметры моментальных снимков журнала**выберите **Хранить в журнале отчета все снимки данных отчета**.</span><span class="sxs-lookup"><span data-stu-id="6613d-129">In **History Snapshot Options**, click **Store all report data snapshots in report history**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6613d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="6613d-130">See Also</span></span>  
 [<span data-ttu-id="6613d-131">Установка параметров обработки (службы Reporting Services в режиме интеграции с SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6613d-131">Set Processing Options &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../set-processing-options-reporting-services-in-sharepoint-integrated-mode.md)  
  
  
