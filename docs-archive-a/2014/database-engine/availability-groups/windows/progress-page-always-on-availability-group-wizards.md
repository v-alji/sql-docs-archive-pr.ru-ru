---
title: Страница "выполнение" (мастера групп доступности AlwaysOn) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.progress.f1
- sql12.swb.newagwizard.progress.f1
- sql11.swb.failoverwizard.progress.f1
- sql11.swb.adddatabasewizard.progress.f1
- sql11.swb.addreplicawizard.progress.f1
- sql11.swb.newagwizard.progress.f1
- sql12.swb.adddatabasewizard.progress.f1
- sql12.swb.failoverwixard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7de8df6906d930215d71a0adc562bd7cef961ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740493"
---
# <a name="progress-page-alwayson-availability-group-wizards"></a><span data-ttu-id="966fe-102">Страница «Выполнение» (мастера групп доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="966fe-102">Progress Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="966fe-103">Используйте это диалоговое окно для просмотра шагов мастера [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , запущенного в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="966fe-103">Use this dialog box to view the progress of a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard that you are running in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="966fe-104">Индикатор выполнения указывает относительный прогресс шагов мастера.</span><span class="sxs-lookup"><span data-stu-id="966fe-104">The progress bar indicates the relative progress of the steps that the wizard is performing.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="966fe-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="966fe-105">UI element list</span></span>  
 <span data-ttu-id="966fe-106">**Дополнительные сведения**</span><span class="sxs-lookup"><span data-stu-id="966fe-106">**More details**</span></span>  
 <span data-ttu-id="966fe-107">Щелкните стрелку вниз, чтобы отобразить сетку выполнения, в которой по порядку отображены любые завершенные шаги, за которыми отображается текущая операция.</span><span class="sxs-lookup"><span data-stu-id="966fe-107">Click the down arrow to display a progress grid that lists any completed steps, in order, followed by the current in-progress operation.</span></span> <span data-ttu-id="966fe-108">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="966fe-108">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="966fe-109">**имя**;</span><span class="sxs-lookup"><span data-stu-id="966fe-109">**Name**</span></span>  
 <span data-ttu-id="966fe-110">Отображает фразу, которая описывает конкретный шаг.</span><span class="sxs-lookup"><span data-stu-id="966fe-110">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="966fe-111">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="966fe-111">**Status**</span></span>  
 <span data-ttu-id="966fe-112">Показывает результат завершенных шагов и процент завершения текущего шага.</span><span class="sxs-lookup"><span data-stu-id="966fe-112">Indicates the outcome of completed steps and the percentage of completion of the current step, as follows:</span></span>  
  
|<span data-ttu-id="966fe-113">Результат</span><span class="sxs-lookup"><span data-stu-id="966fe-113">Result</span></span>|<span data-ttu-id="966fe-114">Описание</span><span class="sxs-lookup"><span data-stu-id="966fe-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="966fe-115">**Error**</span><span class="sxs-lookup"><span data-stu-id="966fe-115">**Error**</span></span>|<span data-ttu-id="966fe-116">Указывает, что при выполнении операции в этом шаге произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="966fe-116">Indicates the operation for this step experienced an error.</span></span> <span data-ttu-id="966fe-117">Щелкните ссылку, чтобы отобразить диалоговое окно с сообщением, описывающим ошибку.</span><span class="sxs-lookup"><span data-stu-id="966fe-117">Click the link to display a message dialog box that describes the error.</span></span>|  
|<span data-ttu-id="966fe-118">**Выполняется (** *процент завершения* **)**</span><span class="sxs-lookup"><span data-stu-id="966fe-118">**In Progress (** *percentage-completed* **)**</span></span>|<span data-ttu-id="966fe-119">Указывает, что операция происходит сейчас и выполняет оценку процентной доли завершения этого шага.</span><span class="sxs-lookup"><span data-stu-id="966fe-119">Indicates that the operation is occurring now and estimates the percentage of this step that has completed.</span></span>|  
|<span data-ttu-id="966fe-120">**Успешно**</span><span class="sxs-lookup"><span data-stu-id="966fe-120">**Success**</span></span>|<span data-ttu-id="966fe-121">Указывает, что операция, выполнявшаяся в этом шаге, завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="966fe-121">Indicates the operation for this step completed successfully.</span></span>|  
  
 <span data-ttu-id="966fe-122">**Меньше сведений**</span><span class="sxs-lookup"><span data-stu-id="966fe-122">**Fewer Details**</span></span>  
 <span data-ttu-id="966fe-123">Выберите, чтобы скрыть сетку хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="966fe-123">Click to hide the progress grid.</span></span>  
  
 <span data-ttu-id="966fe-124">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="966fe-124">**Cancel**</span></span>  
 <span data-ttu-id="966fe-125">Нажмите, чтобы пропустить любые остающиеся операции и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="966fe-125">Click to skip any remaining operations and then exit the wizard.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="966fe-126">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="966fe-126">Related Tasks</span></span>  
  
-   [<span data-ttu-id="966fe-127">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="966fe-127">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="966fe-128">Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="966fe-128">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="966fe-129">Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="966fe-129">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="966fe-130">Использование мастера отработки отказа группы доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="966fe-130">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="966fe-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="966fe-131">See Also</span></span>  
 [<span data-ttu-id="966fe-132">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="966fe-132">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
