---
title: Связывание отчета с моделью в качестве отчета с дополнительной информацией | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- customizing clickthrough reports
- clickthrough reports, customizing
- clickthrough reports, templates
ms.assetid: 3af42de3-67ef-41c2-bc8a-7045baec6f63
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb84f8036dbe5a1694628144f0b948452261ca75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656215"
---
# <a name="link-a-report-to-a-model-as-a-clickthrough-report"></a><span data-ttu-id="1e0d5-102">Связывание отчета с моделью в качестве отчета с дополнительной информацией</span><span class="sxs-lookup"><span data-stu-id="1e0d5-102">Link a Report to a Model as a Clickthrough Report</span></span>
  <span data-ttu-id="1e0d5-103">Вместо использования применяемых по умолчанию шаблонов отчетов с дополнительной информацией можно создать отчет в построителе отчетов, а затем установить его связь с конкретной сущностью в модели отчета.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-103">Instead of using the default clickthrough report templates, you can create a Report Builder report and then link it to a specific entity in the report model.</span></span> <span data-ttu-id="1e0d5-104">Когда пользователь, просматривающий отчет, щелкает мышью интерактивные данные в основном отчете, отчет отображается как отчет с дополнительной информацией.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-104">When the person viewing the report clicks the interactive data in the main report, this report is displayed as a clickthrough report.</span></span> <span data-ttu-id="1e0d5-105">Для установления связи между отчетом и сущностью используется диспетчер отчетов служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e0d5-105">To link a report to an entity, use [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e0d5-106">Первичной, или базовой сущностью, используемой в отчете, должна быть та, с которой отчет связан.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-106">The primary, or base, entity that is used in the report must to be the same entity to which the report is linked.</span></span>  
  
### <a name="to-start-report-manager-from-a-browser"></a><span data-ttu-id="1e0d5-107">Запуск диспетчера отчетов из браузера</span><span class="sxs-lookup"><span data-stu-id="1e0d5-107">To start Report Manager from a browser</span></span>  
  
1.  <span data-ttu-id="1e0d5-108">Откройте браузер [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer версии 6.0 или выше.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-108">Open [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 or later.</span></span>  
  
2.  <span data-ttu-id="1e0d5-109">В адресной строке веб-браузера введите URL-адрес диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-109">In the address bar of the Web browser, type the Report Manager URL.</span></span> <span data-ttu-id="1e0d5-110">URL-адрес по умолчанию — http:// \<*ComputerName*> /Reports.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-110">By default, the URL is http://\<*ComputerName*>/reports.</span></span>  
  
### <a name="to-create-a-customized-clickthrough-report"></a><span data-ttu-id="1e0d5-111">Создание пользовательского отчета с дополнительной информацией</span><span class="sxs-lookup"><span data-stu-id="1e0d5-111">To create a customized clickthrough report</span></span>  
  
1.  <span data-ttu-id="1e0d5-112">Перейдите к модели отчета, к которой нужно добавить пользовательский отчет с дополнительной информацией.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-112">Navigate to the report model to which you want to add the customized clickthrough report.</span></span>  
  
2.  <span data-ttu-id="1e0d5-113">Дважды щелкните эту модель.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-113">Double-click the report model.</span></span>  
  
3.  <span data-ttu-id="1e0d5-114">Выберите **Дополнительная информация**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-114">Click **Clickthrough**.</span></span>  
  
4.  <span data-ttu-id="1e0d5-115">Выберите сущность, к которой нужно присоединить пользовательский отчет с дополнительной информацией.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-115">Select the entity to which you want to attach the customized clickthrough report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e0d5-116">Выбранная сущность должна быть базовой для пользовательского отчета с дополнительной информацией.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-116">This entity must be the same as the base entity of the customized clickthrough report.</span></span>  
  
5.  <span data-ttu-id="1e0d5-117">Для просмотра пользовательского отчета нужно выбрать один экземпляр выбранной сущности и нажать кнопку **Обзор** для одного экземпляра отчета.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-117">To display the customized report when a single instance of the selected entity is clicked, click the Single instance report **Browse** button.</span></span>  
  
     <span data-ttu-id="1e0d5-118">-или-</span><span class="sxs-lookup"><span data-stu-id="1e0d5-118">-or-</span></span>  
  
     <span data-ttu-id="1e0d5-119">Для просмотра пользовательского отчета нужно выбрать несколько экземпляров выбранной сущности и нажать кнопку **Обзор** для нескольких экземпляров отчета.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-119">To display the customized report when a multiple instance of the selected entity is clicked, click the Multiple instance report **Browse** button.</span></span>  
  
6.  <span data-ttu-id="1e0d5-120">Выберите отчет, а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-120">Select the report and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1e0d5-121">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="1e0d5-121">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0d5-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e0d5-122">See Also</span></span>  
 [<span data-ttu-id="1e0d5-123">Отчеты с дополнительной информацией &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1e0d5-123">Clickthrough Reports &#40;SSRS&#41;</span></span>](reports/clickthrough-reports-ssrs.md)  
  
  
