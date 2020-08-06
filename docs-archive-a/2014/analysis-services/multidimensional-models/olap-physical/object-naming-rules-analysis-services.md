---
title: Правила именования объектов (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], naming
ms.assetid: b338a60d-4802-4b68-862a-6dc6a3f75e48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adfd4b23b6fe9129641271fc3c2381e161119ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666809"
---
# <a name="object-naming-rules-analysis-services"></a><span data-ttu-id="0bd47-102">Правила именования объектов (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="0bd47-102">Object Naming Rules (Analysis Services)</span></span>
  <span data-ttu-id="0bd47-103">В этом разделе описаны соглашения об именах объектов, а также зарезервированные слова и символы, которые нельзя использовать в именах объектов, в коде или в скриптах служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bd47-103">This topic describes object naming conventions, as well as the reserved words and characters that cannot be used in any object name, in code or script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
##  <a name="naming-conventions"></a><a name="bkmk_Names"></a><span data-ttu-id="0bd47-104">Соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="0bd47-104">Naming Conventions</span></span>  
 <span data-ttu-id="0bd47-105">Каждый объект имеет свойства `Name` и `ID`, которые должны быть уникальными в области определения родительской коллекции.</span><span class="sxs-lookup"><span data-stu-id="0bd47-105">Every object has a `Name` and `ID` property that must be unique within the scope of the parent collection.</span></span> <span data-ttu-id="0bd47-106">Например, два измерения могут иметь одинаковое имя, только если они находятся в разных базах данных.</span><span class="sxs-lookup"><span data-stu-id="0bd47-106">For example, two dimensions can have same name as long as each one resides in a different database.</span></span>  
  
 <span data-ttu-id="0bd47-107">Хотя значение свойства `ID` можно указать вручную, обычно оно указывается автоматически при создании объекта.</span><span class="sxs-lookup"><span data-stu-id="0bd47-107">Although you can specify it manually, the `ID` is typically auto-generated when the object is created.</span></span> <span data-ttu-id="0bd47-108">После начала разработки модели изменять значение свойства `ID` не следует.</span><span class="sxs-lookup"><span data-stu-id="0bd47-108">You should never change the `ID` once you have begun building a model.</span></span> <span data-ttu-id="0bd47-109">Все ссылки на объекты во всей модели создаются на основе `ID`.</span><span class="sxs-lookup"><span data-stu-id="0bd47-109">All object references throughout a model are based on the `ID`.</span></span> <span data-ttu-id="0bd47-110">Поэтому изменение значения свойства `ID` может легко привести к повреждению всей модели.</span><span class="sxs-lookup"><span data-stu-id="0bd47-110">Thus, changing an `ID` can easily result in model corruption.</span></span>  
  
 <span data-ttu-id="0bd47-111">Для объектов `DataSource` и `DataSourceView` предусмотрены заметные исключения из соглашений об именовании.</span><span class="sxs-lookup"><span data-stu-id="0bd47-111">`DataSource` and `DataSourceView` objects have notable exceptions to naming conventions.</span></span> <span data-ttu-id="0bd47-112">В качестве идентификатора объекта `DataSource` в качестве ссылки на текущую базу данных может быть задана одна точка (.), которая не является уникальной.</span><span class="sxs-lookup"><span data-stu-id="0bd47-112">`DataSource` ID can be set to a single dot (.), which is not unique, as a reference to the current database.</span></span> <span data-ttu-id="0bd47-113">Вторым исключением является объект `DataSourceView`, который следует соглашениям об именовании, определенным для объектов `DataSet` в платформе .NET Framework, где в качестве идентификатора используется свойство `Name`.</span><span class="sxs-lookup"><span data-stu-id="0bd47-113">A second exception is `DataSourceView`, which adheres to the naming conventions defined for `DataSet` objects in the .NET Framework, where the `Name` is used as the identifier.</span></span>  
  
 <span data-ttu-id="0bd47-114">Следующие правила относятся к свойствам `Name` и `ID`.</span><span class="sxs-lookup"><span data-stu-id="0bd47-114">The following rules apply to `Name` and `ID` properties.</span></span>  
  
-   <span data-ttu-id="0bd47-115">В именах учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="0bd47-115">Names are case insensitive.</span></span> <span data-ttu-id="0bd47-116">В той же базе данных нельзя иметь куб с именем «Sales» и другой с именем «Sales».</span><span class="sxs-lookup"><span data-stu-id="0bd47-116">You cannot have a cube named "sales" and another named "Sales" in the same database.</span></span>  
  
-   <span data-ttu-id="0bd47-117">В имени объекта нельзя использовать начальные или конечные пробелы, однако их можно указывать внутри имени.</span><span class="sxs-lookup"><span data-stu-id="0bd47-117">No leading or trailing spaces allowed in an object name, although you can embed spaces within a name.</span></span> <span data-ttu-id="0bd47-118">Происходит неявное отсечение ведущих и конечных пробелов.</span><span class="sxs-lookup"><span data-stu-id="0bd47-118">Leading and trailing spaces are implicitly trimmed.</span></span> <span data-ttu-id="0bd47-119">Это относится как к свойству `Name`, так и к свойству `ID` объекта.</span><span class="sxs-lookup"><span data-stu-id="0bd47-119">This applies to both the `Name` and `ID` of an object.</span></span>  
  
-   <span data-ttu-id="0bd47-120">Максимальное количество символов равно 100.</span><span class="sxs-lookup"><span data-stu-id="0bd47-120">The maximum number of characters is 100.</span></span>  
  
-   <span data-ttu-id="0bd47-121">Какие-либо специальные требования к первому символу идентификатора не предъявляются.</span><span class="sxs-lookup"><span data-stu-id="0bd47-121">There is no special requirement for the first character of an identifier.</span></span> <span data-ttu-id="0bd47-122">В качестве первого символа может применяться любой допустимый символ.</span><span class="sxs-lookup"><span data-stu-id="0bd47-122">The first character may be any valid character.</span></span>  
  
##  <a name="reserved-words-and-characters"></a><a name="bkmk_reserved"></a><span data-ttu-id="0bd47-123">Зарезервированные слова и символы</span><span class="sxs-lookup"><span data-stu-id="0bd47-123">Reserved Words and Characters</span></span>  
 <span data-ttu-id="0bd47-124">Зарезервированными являются английские слова, при этом использовать их нельзя только в именах объектов, а не в заголовках.</span><span class="sxs-lookup"><span data-stu-id="0bd47-124">Reserved words are in English, and apply to object names, not Captions.</span></span> <span data-ttu-id="0bd47-125">В случае непреднамеренного использования зарезервированного слова в имени объекта возникнет ошибка проверки.</span><span class="sxs-lookup"><span data-stu-id="0bd47-125">If you inadvertently use a reserved word in an object name, a validation error will occur.</span></span> <span data-ttu-id="0bd47-126">В многомерных моделях и моделях интеллектуального анализа данных описанные далее зарезервированные слова нельзя использовать в именах любых объектов.</span><span class="sxs-lookup"><span data-stu-id="0bd47-126">For multidimensional and data mining models, the reserved words described below cannot be used in any object name, at any time.</span></span>  
  
 <span data-ttu-id="0bd47-127">Что касается табличных моделей, то при уровне совместимости базы данных 1103 правила проверки смягчаются для некоторых объектов с целью обеспечения соответствия требованиям для символов национального алфавита и соглашениям об именах некоторых клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="0bd47-127">For tabular models, where the database compatibility is set to 1103, validation rules have been relaxed for certain objects, out of compliance for the extended character requirements and naming conventions of certain client applications.</span></span> <span data-ttu-id="0bd47-128">На базы данных, которые удовлетворяют этим критериям, распространяются менее строгие правила проверки.</span><span class="sxs-lookup"><span data-stu-id="0bd47-128">Databases that meet these criteria are subject to less stringent validation rules.</span></span> <span data-ttu-id="0bd47-129">В этом случае в имени объекта может содержаться зарезервированный символ, но проверка будет пройдена.</span><span class="sxs-lookup"><span data-stu-id="0bd47-129">In this case, it's possible for an object name to include a restricted character and still pass validation.</span></span>  
  
 <span data-ttu-id="0bd47-130">**Зарезервированные слова**</span><span class="sxs-lookup"><span data-stu-id="0bd47-130">**Reserved Words**</span></span>  
  
-   <span data-ttu-id="0bd47-131">AUX</span><span class="sxs-lookup"><span data-stu-id="0bd47-131">AUX</span></span>  
  
-   <span data-ttu-id="0bd47-132">CLOCK$</span><span class="sxs-lookup"><span data-stu-id="0bd47-132">CLOCK$</span></span>  
  
-   <span data-ttu-id="0bd47-133">COM1-COM9 (COM1, COM2, COM3 и т. д.)</span><span class="sxs-lookup"><span data-stu-id="0bd47-133">COM1 through COM9 (COM1, COM2, COM3, and so on)</span></span>  
  
-   <span data-ttu-id="0bd47-134">CON</span><span class="sxs-lookup"><span data-stu-id="0bd47-134">CON</span></span>  
  
-   <span data-ttu-id="0bd47-135">LPT1-LPT9 (LPT1, LPT2, LPT3 и т. д.)</span><span class="sxs-lookup"><span data-stu-id="0bd47-135">LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)</span></span>  
  
-   <span data-ttu-id="0bd47-136">NUL</span><span class="sxs-lookup"><span data-stu-id="0bd47-136">NUL</span></span>  
  
-   <span data-ttu-id="0bd47-137">PRN</span><span class="sxs-lookup"><span data-stu-id="0bd47-137">PRN</span></span>  
  
-   <span data-ttu-id="0bd47-138">Не допускается использование значения NULL в качестве символа ни в одной строке в коде XML</span><span class="sxs-lookup"><span data-stu-id="0bd47-138">NULL is not allowed as a character in any string within the XML</span></span>  
  
 <span data-ttu-id="0bd47-139">**Зарезервированные символы**</span><span class="sxs-lookup"><span data-stu-id="0bd47-139">**Reserved Characters**</span></span>  
  
 <span data-ttu-id="0bd47-140">В следующей таблице перечислены символы, которые являются недопустимыми для конкретных объектов.</span><span class="sxs-lookup"><span data-stu-id="0bd47-140">The following table lists invalid characters for specific objects.</span></span>  
  
|<span data-ttu-id="0bd47-141">Объект</span><span class="sxs-lookup"><span data-stu-id="0bd47-141">Object</span></span>|<span data-ttu-id="0bd47-142">Недопустимые знаки</span><span class="sxs-lookup"><span data-stu-id="0bd47-142">Invalid characters</span></span>|  
|------------|------------------------|  
|`Server`|<span data-ttu-id="0bd47-143">При именовании серверных объектов следуйте соглашению об именах для сервера Windows.</span><span class="sxs-lookup"><span data-stu-id="0bd47-143">Follow Windows server naming conventions when naming a server object.</span></span> <span data-ttu-id="0bd47-144">Дополнительные сведения см. в разделе [Соглашения об именах (Windows)](/windows/desktop/DNS/naming-conventions) .</span><span class="sxs-lookup"><span data-stu-id="0bd47-144">See [Naming Conventions (Windows)](/windows/desktop/DNS/naming-conventions) for details.</span></span>|  
|`DataSource`| `: / \ * \| ? " () [] {} <>` |  
|<span data-ttu-id="0bd47-145">`Level` или `Attribute`</span><span class="sxs-lookup"><span data-stu-id="0bd47-145">`Level` or `Attribute`</span></span>|````. , ; ' ` : / \ * & \| ? " & % $ ! + = [] {} < >````|  
|<span data-ttu-id="0bd47-146">`Dimension` или `Hierarchy`</span><span class="sxs-lookup"><span data-stu-id="0bd47-146">`Dimension` or `Hierarchy`</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} <,>````|  
|<span data-ttu-id="0bd47-147">Все прочие объекты</span><span class="sxs-lookup"><span data-stu-id="0bd47-147">All other objects</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} < >````|  
  
 <span data-ttu-id="0bd47-148">**Исключения: Когда зарезервированные символы разрешены**</span><span class="sxs-lookup"><span data-stu-id="0bd47-148">**Exceptions: When Reserved Characters are Allowed**</span></span>  
  
 <span data-ttu-id="0bd47-149">Как уже упоминалось, базы данных с определенной модальностью и уровнем совместимости могут иметь имена объектов, которые содержат зарезервированные символы.</span><span class="sxs-lookup"><span data-stu-id="0bd47-149">As noted, databases of a specific modality and compatibility level can have object names that include reserved characters.</span></span> <span data-ttu-id="0bd47-150">Имена объектов атрибута измерения, иерархии, уровня меры и KPI, которые находятся в табличных базах данных (1103 или более), где допускается использование символов национального алфавита, могут содержать зарезервированные символы.</span><span class="sxs-lookup"><span data-stu-id="0bd47-150">Dimension attribute, hierarchy, level, measure and KPI object names can include reserved characters, for tabular databases (1103 or higher) that allow the use of extended characters:</span></span>  
  
|<span data-ttu-id="0bd47-151">Режим сервера и уровень совместимости базы данных</span><span class="sxs-lookup"><span data-stu-id="0bd47-151">Server mode and database compatibility level</span></span>|<span data-ttu-id="0bd47-152">Зарезервированные символы разрешены?</span><span class="sxs-lookup"><span data-stu-id="0bd47-152">Reserved characters allowed?</span></span>|  
|--------------------------------------------------|----------------------------------|  
|<span data-ttu-id="0bd47-153">MOLAP (все версии)</span><span class="sxs-lookup"><span data-stu-id="0bd47-153">MOLAP (all versions)</span></span>|<span data-ttu-id="0bd47-154">Нет</span><span class="sxs-lookup"><span data-stu-id="0bd47-154">No</span></span>|  
|<span data-ttu-id="0bd47-155">Табличные — 1050</span><span class="sxs-lookup"><span data-stu-id="0bd47-155">Tabular - 1050</span></span>|<span data-ttu-id="0bd47-156">Нет</span><span class="sxs-lookup"><span data-stu-id="0bd47-156">No</span></span>|  
|<span data-ttu-id="0bd47-157">Табличные — 1100</span><span class="sxs-lookup"><span data-stu-id="0bd47-157">Tabular - 1100</span></span>|<span data-ttu-id="0bd47-158">Нет</span><span class="sxs-lookup"><span data-stu-id="0bd47-158">No</span></span>|  
|<span data-ttu-id="0bd47-159">Табличный — 1130 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="0bd47-159">Tabular - 1130 and higher</span></span>|<span data-ttu-id="0bd47-160">Да</span><span class="sxs-lookup"><span data-stu-id="0bd47-160">Yes</span></span>|  
  
 <span data-ttu-id="0bd47-161">Базы данных могут иметь ModelType по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0bd47-161">Databases can have a ModelType of default.</span></span> <span data-ttu-id="0bd47-162">Типом по умолчанию является многомерная база данных, в связи с чем использование зарезервированных символов в именах столбцов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0bd47-162">Default is equivalent to multidimensional, and thus does not support the use of reserved characters in column names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd47-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="0bd47-163">See Also</span></span>  
 <span data-ttu-id="0bd47-164">[Зарезервированные слова многомерных выражений](/sql/mdx/mdx-reserved-words) </span><span class="sxs-lookup"><span data-stu-id="0bd47-164">[MDX Reserved Words](/sql/mdx/mdx-reserved-words) </span></span>  
 <span data-ttu-id="0bd47-165">[Переводы &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span><span class="sxs-lookup"><span data-stu-id="0bd47-165">[Translations &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span></span>  
 [<span data-ttu-id="0bd47-166">Соответствие XML для аналитики &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="0bd47-166">XML for Analysis Compliance &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-compliance-xmla)  
  
  
