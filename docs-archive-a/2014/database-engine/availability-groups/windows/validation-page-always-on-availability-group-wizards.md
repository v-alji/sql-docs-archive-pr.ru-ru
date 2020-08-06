---
title: Страница "Проверка" (мастера групп доступности AlwaysOn) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f2010074a357932f8af7358a05ee6ed16f5c0881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655376"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a><span data-ttu-id="ce02d-102">Страница проверки (мастера групп доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="ce02d-102">Validation Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="ce02d-103">В этом разделе описываются параметры, приведенные на странице **Проверка** .</span><span class="sxs-lookup"><span data-stu-id="ce02d-103">This help topic describes the options of the **Validation** page.</span></span> <span data-ttu-id="ce02d-104">Эта тема относится к [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)]и [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce02d-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ce02d-105">Используйте эту страницу для проверки поддержки средой всех вариантов конфигурации, выбранных на предыдущей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="ce02d-105">Use this page to validate that your environment supports all the configuration choices you made on previous pages of the wizard.</span></span>  
  
##  <a name="validation-page-options"></a><a name="PageOptions"></a><span data-ttu-id="ce02d-106">Параметры страницы проверки</span><span class="sxs-lookup"><span data-stu-id="ce02d-106">Validation Page Options</span></span>  
 <span data-ttu-id="ce02d-107">**Результаты проверки группы доступности.**</span><span class="sxs-lookup"><span data-stu-id="ce02d-107">**Results of availability group validation.**</span></span>  
 <span data-ttu-id="ce02d-108">В этой сетке отображаются результаты каждого завершенного этапа проверки.</span><span class="sxs-lookup"><span data-stu-id="ce02d-108">This grid displays the results of each completed validation step.</span></span> <span data-ttu-id="ce02d-109">Сетка содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="ce02d-109">The grid columns are as follows:</span></span>  
  
 <span data-ttu-id="ce02d-110">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ce02d-110">**Name**</span></span>  
 <span data-ttu-id="ce02d-111">Отображает фразу, которая описывает конкретный шаг.</span><span class="sxs-lookup"><span data-stu-id="ce02d-111">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="ce02d-112">**Результат**</span><span class="sxs-lookup"><span data-stu-id="ce02d-112">**Result**</span></span>  
 <span data-ttu-id="ce02d-113">Отображает один из следующих текстов гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="ce02d-113">Displays one of the following hyperlink texts.</span></span> <span data-ttu-id="ce02d-114">Дополнительные сведения данного шага проверки можно просмотреть, щелкнув гиперссылку.</span><span class="sxs-lookup"><span data-stu-id="ce02d-114">For more information about the result of given validation step, click the hyperlink.</span></span>  
  
|<span data-ttu-id="ce02d-115">Результат</span><span class="sxs-lookup"><span data-stu-id="ce02d-115">Result</span></span>|<span data-ttu-id="ce02d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ce02d-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ce02d-117">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="ce02d-117">**Error**</span></span>|<span data-ttu-id="ce02d-118">Указывает, что шаг проверки выполнен неудачно.</span><span class="sxs-lookup"><span data-stu-id="ce02d-118">Indicates that the validation step failed.</span></span> <span data-ttu-id="ce02d-119">Щелкните ссылку, чтобы просмотреть сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ce02d-119">Click the link to view the error message.</span></span>|  
|<span data-ttu-id="ce02d-120">**Пропущено**</span><span class="sxs-lookup"><span data-stu-id="ce02d-120">**Skipped**</span></span>|<span data-ttu-id="ce02d-121">Указывает, что шаг проверки был пропущен, поскольку он не был отмечен в параметрах как необходимый.</span><span class="sxs-lookup"><span data-stu-id="ce02d-121">Indicates that the validation step was skipped because it is not required by your selections.</span></span> <span data-ttu-id="ce02d-122">Щелкните ссылку для просмотра причины, по которой шаг был пропущен.</span><span class="sxs-lookup"><span data-stu-id="ce02d-122">Click the link to view the reason that a step was skipped.</span></span>|  
|<span data-ttu-id="ce02d-123">**Успешно**</span><span class="sxs-lookup"><span data-stu-id="ce02d-123">**Success**</span></span>|<span data-ttu-id="ce02d-124">Указывает, что шаг проверки завершен удачно.</span><span class="sxs-lookup"><span data-stu-id="ce02d-124">Indicates that the validation step completed successfully</span></span>|  
|<span data-ttu-id="ce02d-125">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="ce02d-125">**Warning**</span></span>|<span data-ttu-id="ce02d-126">Указывает на наличие потенциальной проблемы с конфигурацией группы доступности.</span><span class="sxs-lookup"><span data-stu-id="ce02d-126">Indicates a potential issue with the availability group configuration.</span></span>  <span data-ttu-id="ce02d-127">Щелкните ссылку, чтобы просмотреть предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ce02d-127">Click the link to view the warning message.</span></span>|  
  
 <span data-ttu-id="ce02d-128">**Запустите проверку повторно**</span><span class="sxs-lookup"><span data-stu-id="ce02d-128">**Re-run Validation**</span></span>  
 <span data-ttu-id="ce02d-129">Щелкните, чтобы повторить шаги проверки, если в ответ на выявленную ошибку были внесены изменения без использования средств мастера.</span><span class="sxs-lookup"><span data-stu-id="ce02d-129">Click to repeat the validation steps if you make a change outside of the wizard in response to a validation error.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ce02d-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="ce02d-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ce02d-131">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ce02d-131">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ce02d-132">Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ce02d-132">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ce02d-133">Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ce02d-133">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="ce02d-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce02d-134">See Also</span></span>  
 [<span data-ttu-id="ce02d-135">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ce02d-135">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
