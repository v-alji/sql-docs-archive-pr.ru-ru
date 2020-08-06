---
title: Источник OData | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ODATASOURCE.F1
ms.assetid: cc9003c9-638e-432b-867e-e949d50cec90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 98b14ef034597f6098f70386ca41c1b90be86500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750036"
---
# <a name="odata-source"></a><span data-ttu-id="8aecb-102">Источник OData</span><span class="sxs-lookup"><span data-stu-id="8aecb-102">OData Source</span></span>
  <span data-ttu-id="8aecb-103">Компонент источника OData используется в пакете служб SSIS для получения данных от служб OData.</span><span class="sxs-lookup"><span data-stu-id="8aecb-103">You use the OData Source component in an SSIS package to consume data from Open Data Protocol (OData) services.</span></span> <span data-ttu-id="8aecb-104">Компонент поддерживает протоколы OData v2 и v3, а также форматы данных ATOM и JSON.</span><span class="sxs-lookup"><span data-stu-id="8aecb-104">The component supports the OData v2 and v3 protocols, as well as the ATOM and JSON data formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8aecb-105">Источник OData можно использовать для чтения данных из списков SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8aecb-105">The OData Source can be used to read from SharePoint lists.</span></span> <span data-ttu-id="8aecb-106">Чтобы просмотреть все списки на сервере SharePoint, используйте следующий URL-адрес: http:// \<server> /_vti_bin/листдата.СВК.</span><span class="sxs-lookup"><span data-stu-id="8aecb-106">To see all lists on your SharePoint server, use the following URL: http://\<server>/_vti_bin/ListData.svc.</span></span> <span data-ttu-id="8aecb-107">Дополнительные сведения о соглашениях об URL-адресах SharePoint см. в разделе [Интерфейс REST SharePoint Foundation](https://msdn.microsoft.com/library/ff521587.aspx).</span><span class="sxs-lookup"><span data-stu-id="8aecb-107">For more information about SharePoint URL conventions, see [SharePoint Foundation REST Interface](https://msdn.microsoft.com/library/ff521587.aspx).</span></span>  
  
## <a name="odata-format"></a><span data-ttu-id="8aecb-108">Формат OData</span><span class="sxs-lookup"><span data-stu-id="8aecb-108">OData Format</span></span>  
 <span data-ttu-id="8aecb-109">Большинство служб OData возвращают результаты в различных форматах.</span><span class="sxs-lookup"><span data-stu-id="8aecb-109">Most OData services return results in multiple formats.</span></span> <span data-ttu-id="8aecb-110">Можно указать формат результирующего набора с помощью параметра $format запроса.</span><span class="sxs-lookup"><span data-stu-id="8aecb-110">You can specify the format of the result set by using the $format query option.</span></span> <span data-ttu-id="8aecb-111">Такие форматы, как JSON и JSON Light, более эффективны, чем ATOM/XML, и способны обеспечить более высокую производительность при передаче больших объемов данных.</span><span class="sxs-lookup"><span data-stu-id="8aecb-111">Formats such as JSON and JSON Light are more efficient than ATOM/XML, and may give you better performance when transferring large amounts of data.</span></span> <span data-ttu-id="8aecb-112">В следующей таблице отображаются результаты типовых тестов.</span><span class="sxs-lookup"><span data-stu-id="8aecb-112">The following table provides results from sample tests.</span></span> <span data-ttu-id="8aecb-113">Как видно, выигрыш в производительности при переключении с ATOM на JSON составил 30–53 и 67 % при переходе с ATOM на новый формат JSON Light (доступный в WCF Data Services 5.1).</span><span class="sxs-lookup"><span data-stu-id="8aecb-113">As you can see, there was a 30-53% performance gain when switching from ATOM to JSON and 67% performance gain when switching from ATOM to the new JSON light format (available in WCF Data Services 5.1).</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="8aecb-114">Строки</span><span class="sxs-lookup"><span data-stu-id="8aecb-114">Rows</span></span>|<span data-ttu-id="8aecb-115">ATOM</span><span class="sxs-lookup"><span data-stu-id="8aecb-115">ATOM</span></span>|<span data-ttu-id="8aecb-116">JSON</span><span class="sxs-lookup"><span data-stu-id="8aecb-116">JSON</span></span>|<span data-ttu-id="8aecb-117">JSON (Light)</span><span class="sxs-lookup"><span data-stu-id="8aecb-117">JSON (Light)</span></span>|  
|<span data-ttu-id="8aecb-118">10000</span><span class="sxs-lookup"><span data-stu-id="8aecb-118">10000</span></span>|<span data-ttu-id="8aecb-119">113 секунд</span><span class="sxs-lookup"><span data-stu-id="8aecb-119">113 seconds</span></span>|<span data-ttu-id="8aecb-120">74 секунды</span><span class="sxs-lookup"><span data-stu-id="8aecb-120">74 seconds</span></span>|<span data-ttu-id="8aecb-121">68 секунд</span><span class="sxs-lookup"><span data-stu-id="8aecb-121">68 seconds</span></span>|  
|<span data-ttu-id="8aecb-122">1000000</span><span class="sxs-lookup"><span data-stu-id="8aecb-122">1000000</span></span>|<span data-ttu-id="8aecb-123">1110 секунд</span><span class="sxs-lookup"><span data-stu-id="8aecb-123">1110 seconds</span></span>|<span data-ttu-id="8aecb-124">853 секунды</span><span class="sxs-lookup"><span data-stu-id="8aecb-124">853 seconds</span></span>|<span data-ttu-id="8aecb-125">665 с</span><span class="sxs-lookup"><span data-stu-id="8aecb-125">665 seconds</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="8aecb-126">Источник OData служб SSIS использует ODataLib 5.5.0 для синтаксического анализа каналов OData и может считывать все форматы, поддерживаемые этой библиотекой.</span><span class="sxs-lookup"><span data-stu-id="8aecb-126">The SSIS OData Source uses ODataLib 5.5.0 to parse OData feeds and it can read all formats supported by this library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8aecb-127">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8aecb-127">In This Section</span></span>  
  
-   [<span data-ttu-id="8aecb-128">Установка и удаление компонента источника OData</span><span class="sxs-lookup"><span data-stu-id="8aecb-128">Install and Uninstall OData Source Component</span></span>](../install-and-uninstall-odata-source-component.md)  
  
-   [<span data-ttu-id="8aecb-129">Учебник. Использование источника OData &#91;SSIS&#93;</span><span class="sxs-lookup"><span data-stu-id="8aecb-129">Tutorial: Using the OData Source &#91;SSIS&#93;</span></span>](tutorial-using-the-odata-source.md)  
  
-   [<span data-ttu-id="8aecb-130">Изменение запроса источника OData во время выполнения</span><span class="sxs-lookup"><span data-stu-id="8aecb-130">Modify OData Source Query at Runtime</span></span>](modify-odata-source-query-at-runtime.md)  
  
-   [<span data-ttu-id="8aecb-131">Редактор источника OData (страница "Подключение")</span><span class="sxs-lookup"><span data-stu-id="8aecb-131">OData Source Editor &#40;Connection Page&#41;</span></span>](../odata-source-editor-connection-page.md)  
  
-   [<span data-ttu-id="8aecb-132">Редактор источника OData (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="8aecb-132">OData Source Editor &#40;Columns Page&#41;</span></span>](../odata-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="8aecb-133">Редактор источника OData (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="8aecb-133">OData Source Editor &#40;Error Output Page&#41;</span></span>](../odata-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="8aecb-134">Свойства источника OData</span><span class="sxs-lookup"><span data-stu-id="8aecb-134">OData Source Properties</span></span>](odata-source-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="8aecb-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="8aecb-135">See Also</span></span>  
 [<span data-ttu-id="8aecb-136">Диспетчер соединений OData</span><span class="sxs-lookup"><span data-stu-id="8aecb-136">OData Connection Manager</span></span>](../connection-manager/odata-connection-manager.md)  
  
  
