---
title: Образец простого входного файла XML (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: 5b00e4eb-1742-43ec-98d8-d84216b6b840
author: stevestein
ms.author: sstein
ms.openlocfilehash: 00a973732c296cadd3d38a6ac7d9c50b7da3c90b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666308"
---
# <a name="simple-xml-input-file-sample-dta"></a><span data-ttu-id="46bc0-102">Образец простого входного файла XML (DTA)</span><span class="sxs-lookup"><span data-stu-id="46bc0-102">Simple XML Input File Sample (DTA)</span></span>
  <span data-ttu-id="46bc0-103">Скопируйте и вставьте этот образец простого входного файла XML, используемого для настройки рабочих нагрузок, в любой текстовый или XML-редактор.</span><span class="sxs-lookup"><span data-stu-id="46bc0-103">Copy and paste this sample of a simple XML input file to use for tuning workloads into your favorite XML editor or text editor.</span></span> <span data-ttu-id="46bc0-104">Затем замените значения, заданные для элементов **Server**, **Database**, **Schema**, **Table**, **Workload**и **TuningOptions** , значениями для конкретного сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="46bc0-104">Then replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="46bc0-105">Дополнительные сведения об атрибутах и дочерних элементах, которые могут использоваться с этими элементами, см. в разделе [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="46bc0-105">For more information about the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="46bc0-106">В следующем образце используется только подмножество доступных атрибутов и параметров дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="46bc0-106">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="46bc0-107">Код</span><span class="sxs-lookup"><span data-stu-id="46bc0-107">Code</span></span>  
 [!code-xml[InputFileSamples#SimpleXMLInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#simplexmlinputfile)]  
  
## <a name="see-also"></a><span data-ttu-id="46bc0-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="46bc0-108">See Also</span></span>  
 <span data-ttu-id="46bc0-109">[Запуск и использование помощника по настройке ядра СУБД](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="46bc0-109">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="46bc0-110">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="46bc0-110">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
