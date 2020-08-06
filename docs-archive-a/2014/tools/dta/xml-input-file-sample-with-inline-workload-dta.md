---
title: Образец входного XML-файла со встроенной рабочей нагрузкой (DTA) | Документы Майкрософт
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
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93b2ab4279378b4cd392d97a9b65f299d0e9c6dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658005"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a><span data-ttu-id="86670-102">Образец входного XML-файла с описанием встроенной рабочей нагрузки (DTA)</span><span class="sxs-lookup"><span data-stu-id="86670-102">XML Input File Sample with Inline Workload (DTA)</span></span>
  <span data-ttu-id="86670-103">Скопируйте и вставьте этот входной XML-файл, задающий рабочую нагрузку элементом **EventString** , в свой привычный редактор XML или текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="86670-103">Copy and paste this sample of an XML input file that specifies a workload with the **EventString** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="86670-104">Элемент **EventString** можно использовать для указания во входном файле XML рабочей нагрузки из скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] вместо использования отдельного файла рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="86670-104">You can use the **EventString** element to specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload in the XML input file instead of using a separate workload file.</span></span> <span data-ttu-id="86670-105">Скопировав данный образец, замените значения, указанные для элементов **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**и **TuningOptions** , значениями, характерными для вашего сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="86670-105">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="86670-106">Дополнительные сведения обо всех атрибутах и дочерних элементах, которые могут использоваться с этими элементами, см. в разделе [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="86670-106">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="86670-107">В следующем образце используется только подмножество доступных атрибутов и параметров дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="86670-107">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="86670-108">Код</span><span class="sxs-lookup"><span data-stu-id="86670-108">Code</span></span>  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a><span data-ttu-id="86670-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="86670-109">Comments</span></span>  
 <span data-ttu-id="86670-110">`USE database_name` EventString **EventString** .</span><span class="sxs-lookup"><span data-stu-id="86670-110">`USE database_name` statements can be specified in the inline workload that is contained in the **EventString** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86670-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="86670-111">See Also</span></span>  
 <span data-ttu-id="86670-112">[Запуск и использование помощника по настройке ядра СУБД](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="86670-112">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="86670-113">[Просмотр и работа с выходными данными помощника по настройке ядра СУБД](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="86670-113">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="86670-114">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="86670-114">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
