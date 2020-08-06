---
title: Образец входного XML-файла с пользовательской конфигурацией (DTA) | Документы Майкрософт
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
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
author: stevestein
ms.author: sstein
ms.openlocfilehash: 121972518aa114e16cc81517d52a9d9656b067c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666306"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a><span data-ttu-id="28628-102">Образец входного XML-файла с пользовательской конфигурацией (DTA)</span><span class="sxs-lookup"><span data-stu-id="28628-102">XML Input File Sample with User-specified Configuration (DTA)</span></span>
  <span data-ttu-id="28628-103">Скопируйте и вставьте этот образец входного XML-файла, определяющего пользовательскую конфигурацию с помощью элемента **Конфигурация** , в свой привычный XML-редактор или редактор текста.</span><span class="sxs-lookup"><span data-stu-id="28628-103">Copy and paste this sample of an XML input file that specifies a user-specified configuration with the **Configuration** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="28628-104">Это позволит выполнить анализ гипотетических вариантов.</span><span class="sxs-lookup"><span data-stu-id="28628-104">This enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="28628-105">Анализ гипотетических вариантов предполагает использование элемента **Конфигурация** , чтобы определить набор гипотетических структур физического проектирования для настраиваемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="28628-105">"What-if" analysis involves using the **Configuration** element to specify a set of hypothetical physical design structures for the database you want to tune.</span></span> <span data-ttu-id="28628-106">Затем можно применить помощник по настройке ядра СУБД для анализа эффекта от запуска рабочей нагрузки с учетом этой гипотетической конфигурации с целью выяснить, насколько повышается производительность выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="28628-106">Then you use Database Engine Tuning Advisor to analyze the effects of running a workload against this hypothetical configuration to find out whether it improves query processing performance.</span></span> <span data-ttu-id="28628-107">Этот тип анализа позволяет проводить оценку новой конфигурации без затрат, связанных с ее фактическим внедрением.</span><span class="sxs-lookup"><span data-stu-id="28628-107">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="28628-108">Если гипотетическая конфигурация не дает желаемого увеличения производительности, ее можно легко изменить и снова проанализировать до получения конфигурации, позволяющей достигнуть желаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="28628-108">If your hypothetical configuration does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="28628-109">После копирования образца в редактор замените значения элементов **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**и **Configuration** значениями, соответствующими конкретным особенностям данного сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="28628-109">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**, and **Configuration** elements with those for your specific tuning session.</span></span> <span data-ttu-id="28628-110">Дополнительные сведения обо всех атрибутах и дочерних элементах, которые могут использоваться с этими элементами, см. в разделе [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="28628-110">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="28628-111">В следующем образце используется только подмножество доступных атрибутов и параметров дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="28628-111">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="28628-112">Код</span><span class="sxs-lookup"><span data-stu-id="28628-112">Code</span></span>  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a><span data-ttu-id="28628-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="28628-113">Comments</span></span>  
  
-   <span data-ttu-id="28628-114">Удаление структур физического проектирования при указании режима **Absolute** элемента **Configuration** (`Configuration SpecificationMode="Absolute"`) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="28628-114">Dropping physical design structures is not supported if you specify the **Absolute** mode for the **Configuration** element (`Configuration SpecificationMode="Absolute"`).</span></span>  
  
-   <span data-ttu-id="28628-115">Нельзя создавать и удалять одинаковые структуры физического проектирования в режимах**Relative** и **Absolute**элемента **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="28628-115">You cannot create and drop the same physical design structure in either mode (**Relative** or **Absolute**) of the **Configuration** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28628-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="28628-116">See Also</span></span>  
 <span data-ttu-id="28628-117">[Запуск и использование помощника по настройке ядра СУБД](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="28628-117">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="28628-118">[Просмотр и работа с выходными данными помощника по настройке ядра СУБД](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="28628-118">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="28628-119">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="28628-119">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
