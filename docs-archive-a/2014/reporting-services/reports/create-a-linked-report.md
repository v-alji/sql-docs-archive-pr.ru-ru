---
title: Создание связанного отчета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed5e70c9ff8179ae05186685e21303693fc9aed7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665787"
---
# <a name="create-a-linked-report"></a><span data-ttu-id="7e66e-102">Создание связанного отчета</span><span class="sxs-lookup"><span data-stu-id="7e66e-102">Create a Linked Report</span></span>
  <span data-ttu-id="7e66e-103">Связанный отчет является элементом сервера отчетов, обеспечивающим точку доступа к существующему отчету.</span><span class="sxs-lookup"><span data-stu-id="7e66e-103">A linked report is a report server item that provides an access point to an existing report.</span></span> <span data-ttu-id="7e66e-104">Концептуально связанный отчет можно сравнить с ярлыком, который используется для запуска программы или открытия файла.</span><span class="sxs-lookup"><span data-stu-id="7e66e-104">Conceptually, it is similar to a program shortcut that you use to run a program or open a file.</span></span>

 <span data-ttu-id="7e66e-105">Связанный отчет создается из существующего отчета и сохраняет определение оригинального отчета.</span><span class="sxs-lookup"><span data-stu-id="7e66e-105">A linked report is derived from an existing report and retains the original's report definition.</span></span> <span data-ttu-id="7e66e-106">Связанный отчет всегда наследует макет отчета и свойства источника данных у оригинального отчета.</span><span class="sxs-lookup"><span data-stu-id="7e66e-106">A linked report always inherits report layout and data source properties of the original report.</span></span> <span data-ttu-id="7e66e-107">Все остальные свойства и настройки могут отличаться от свойств и настроек оригинального отчета, включая настройки безопасности, параметры, месторасположение, подписки и расписания.</span><span class="sxs-lookup"><span data-stu-id="7e66e-107">All other properties and settings can be different from those of the original report, including security, parameters, location, subscriptions, and schedules.</span></span>

 <span data-ttu-id="7e66e-108">Связанный отчет может быть создан в тех случаях, когда необходимо создать дополнительные версии существующего отчета.</span><span class="sxs-lookup"><span data-stu-id="7e66e-108">You can create a linked report when you want to create additional versions of an existing report.</span></span> <span data-ttu-id="7e66e-109">Например, можно использовать один отчет о региональных продажах для создания региональных отчетов для всех территорий продаж.</span><span class="sxs-lookup"><span data-stu-id="7e66e-109">For example, you could use a single regional sales report to create region-specific reports for all of your sales territories.</span></span>

 <span data-ttu-id="7e66e-110">Хотя связанные отчеты обычно основаны на параметризованных отчетах, параметризованный отчет не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="7e66e-110">Although linked reports are typically based on parameterized reports, a parameterized report is not required.</span></span> <span data-ttu-id="7e66e-111">Можно создавать связанные отчеты, когда необходимо развернуть существующий отчет с различными параметрами.</span><span class="sxs-lookup"><span data-stu-id="7e66e-111">You can create linked reports whenever you want to deploy an existing report with different settings.</span></span>

### <a name="to-create-a-linked-report"></a><span data-ttu-id="7e66e-112">Создание связанного отчета</span><span class="sxs-lookup"><span data-stu-id="7e66e-112">To create a linked report</span></span>

1.  <span data-ttu-id="7e66e-113">В диспетчере отчетов перейдите к папке с отчетом, с которым требуется установить связь, откройте меню параметров и выберите **Создать связанный отчет**.</span><span class="sxs-lookup"><span data-stu-id="7e66e-113">In Report Manager, navigate to the folder containing the report that you want to link to, and then open the options menu can click **Create Linked Report**.</span></span>

2.  <span data-ttu-id="7e66e-114">Введите имя нового связанного отчета.</span><span class="sxs-lookup"><span data-stu-id="7e66e-114">Type a name for the new linked report.</span></span> <span data-ttu-id="7e66e-115">При необходимости введите также описание.</span><span class="sxs-lookup"><span data-stu-id="7e66e-115">Optionally type a description.</span></span>

3.  <span data-ttu-id="7e66e-116">Чтобы выбрать иную папку для отчета, щелкните **Изменить местоположение**.</span><span class="sxs-lookup"><span data-stu-id="7e66e-116">To select a different folder for the report, click **Change Location**.</span></span> <span data-ttu-id="7e66e-117">Щелкните папку, которую нужно использовать, или введите имя папки в поле **Местоположение** .</span><span class="sxs-lookup"><span data-stu-id="7e66e-117">Click the folder you want to use, or type the folder name in the **Location** box.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="7e66e-118">Если не выбрана иная папка, то связанный отчет создается в текущей папке (где хранится отчет, на основе которого создается связанный отчет).</span><span class="sxs-lookup"><span data-stu-id="7e66e-118">If you do not select a different folder, the linked report is created in the current folder (where the report it is based on is stored).</span></span>

4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="7e66e-119">Откроется связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="7e66e-119">The linked report opens.</span></span>

     <span data-ttu-id="7e66e-120">Значок связанного отчета отличается от других элементов, управляемых сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="7e66e-120">A linked report's icon differs from other items managed by a report server.</span></span> <span data-ttu-id="7e66e-121">Следующий значок указывает на связанный отчет:</span><span class="sxs-lookup"><span data-stu-id="7e66e-121">The following icon indicates a linked report:</span></span>

     <span data-ttu-id="7e66e-122">![Значок связанного отчета](../media/hlp-16linked.gif "Значок связанного отчета")</span><span class="sxs-lookup"><span data-stu-id="7e66e-122">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>

## <a name="see-also"></a><span data-ttu-id="7e66e-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e66e-123">See Also</span></span>
 <span data-ttu-id="7e66e-124">[Открытие и закрытие отчета &#40;диспетчер отчетов&#41;](../reports/open-and-close-a-report-report-manager.md) [новой связанной странице отчета &#40;диспетчер отчетов](../new-linked-report-page-report-manager.md)&#41;страница " [выбор расположения элемента" &#40;диспетчер отчетов](../choose-item-location-page-report-manager.md)&#41;[Общие страницы свойств, отчеты &#40;диспетчер отчетов&#41;,](../general-properties-page-reports-report-manager.md) [Основные понятия Reporting Services ssrs &#40;](../reporting-services-concepts-ssrs.md) [&#41;диспетчер отчетов служб SSRS в основном режиме &#40;](../report-manager-ssrs-native-mode.md)</span><span class="sxs-lookup"><span data-stu-id="7e66e-124">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [New Linked Report Page &#40;Report Manager&#41;](../new-linked-report-page-report-manager.md) [Choose Item Location Page &#40;Report Manager&#41;](../choose-item-location-page-report-manager.md) [General Properties Page, Reports &#40;Report Manager&#41;](../general-properties-page-reports-report-manager.md) [Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md)</span></span>


