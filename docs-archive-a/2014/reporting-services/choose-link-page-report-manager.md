---
title: Страница «Выбор ссылки» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a89a555d-efa3-45d6-951e-db78ec6a2c8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc40fe726555babee8d9940e198a93577bd6a09f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657579"
---
# <a name="choose-link-page-report-manager"></a><span data-ttu-id="d0403-102">Страница «Выбор ссылки» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="d0403-102">Choose Link Page (Report Manager)</span></span>
  <span data-ttu-id="d0403-103">Страница «Выбор ссылки» используется для выбора другого отчета, на котором будет строиться текущий выделенный связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="d0403-103">Use the Choose Link page to choose a different report upon which to base the currently selected linked report.</span></span> <span data-ttu-id="d0403-104">Связанные отчеты основаны на других отчетах, уже опубликованных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="d0403-104">Linked reports are based on other reports already published to a report server.</span></span> <span data-ttu-id="d0403-105">В связанном отчете используются макет и данные основного отчета, но имеются отдельные страницы свойств, позволяющие задавать свойства параметров, параметры безопасности, имя, описание и местоположение.</span><span class="sxs-lookup"><span data-stu-id="d0403-105">A linked report uses the layout and data of the base report, but has separate property pages so that you can customize parameter properties, security settings, name, description, and location.</span></span>  
  
 <span data-ttu-id="d0403-106">Страница «Выбор ссылки» позволяет выбрать для использования со связанным отчетом другой опубликованный отчет.</span><span class="sxs-lookup"><span data-stu-id="d0403-106">Through the Choose Link page, you can choose a different published report to use with the linked report.</span></span> <span data-ttu-id="d0403-107">Другие параметры связанного отчета (такие как безопасность и настройки параметров) не зависят от изменений данных о ссылках.</span><span class="sxs-lookup"><span data-stu-id="d0403-107">Other settings of the linked report (such as security and parameter settings) are unaffected by changes to the link information.</span></span> <span data-ttu-id="d0403-108">Сервер отчетов не проверяет правильность этого выбора, поэтому следует обязательно выбирать отчет с такими же параметрами, какие были заданы для связанного отчета.</span><span class="sxs-lookup"><span data-stu-id="d0403-108">The report server will not validate your selection, so be sure to choose a report that has the same parameters as those you specified on the linked report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="d0403-109">Навигация</span><span class="sxs-lookup"><span data-stu-id="d0403-109">Navigation</span></span>  
 <span data-ttu-id="d0403-110">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="d0403-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-link-page"></a><span data-ttu-id="d0403-111">Открытие страницы «Выбор ссылки»</span><span class="sxs-lookup"><span data-stu-id="d0403-111">To open the Choose Link page</span></span>  
  
1.  <span data-ttu-id="d0403-112">Откройте диспетчер отчетов и найдите связанный отчет, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="d0403-112">Open Report Manager, and locate the linked report you want to change.</span></span>  
  
2.  <span data-ttu-id="d0403-113">Подведите курсор к связанному отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d0403-113">Hover over the linked report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="d0403-114">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="d0403-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="d0403-115">Откроется страница свойств связанного отчета **Общие** .</span><span class="sxs-lookup"><span data-stu-id="d0403-115">This opens the **General** properties page for the linked report.</span></span>  
  
4.  <span data-ttu-id="d0403-116">На вкладке страницы свойств **Общее** нажмите кнопку **Изменить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="d0403-116">On the **General** tab, on the properties page, click **Change Link**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0403-117">Варианты</span><span class="sxs-lookup"><span data-stu-id="d0403-117">Options</span></span>  
 <span data-ttu-id="d0403-118">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="d0403-118">**Location**</span></span>  
 <span data-ttu-id="d0403-119">Укажите полное имя опубликованного отчета, включая путь к папке и имя отчета.</span><span class="sxs-lookup"><span data-stu-id="d0403-119">Specify the full name of the published report, including the folder path and report name.</span></span> <span data-ttu-id="d0403-120">Можно ввести полное имя отчета или, используя древовидное представление, перейти к нужному отчету.</span><span class="sxs-lookup"><span data-stu-id="d0403-120">You can type the full name of the report or use the tree view to navigate to the report you want to use.</span></span>  
  
 <span data-ttu-id="d0403-121">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="d0403-121">**Tree view**</span></span>  
 <span data-ttu-id="d0403-122">Показывает все папки в иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d0403-122">Shows all of the folders in the report server folder hierarchy.</span></span> <span data-ttu-id="d0403-123">Чтобы использовать древовидное представление для заполнения поля **Размещение** , щелкните имя отчета.</span><span class="sxs-lookup"><span data-stu-id="d0403-123">To use the tree view to fill in the **Location** field, click the name of the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0403-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0403-124">See Also</span></span>  
 <span data-ttu-id="d0403-125">[Страница «Общие свойства», отчеты &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d0403-125">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="d0403-126">[Страница создания связанного отчета &#40;диспетчер отчетов&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d0403-126">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 [<span data-ttu-id="d0403-127">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="d0403-127">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
