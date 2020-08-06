---
title: Недопустимые символы и правила экранирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, invalid characters
- FOR XML clause, escape rules
ms.assetid: f2e9b997-f400-4963-b225-59d46c6b93e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8624a31dea4e97e05da6d86c3c0c518b9c4d0aba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750559"
---
# <a name="invalid-characters-and-escape-rules"></a><span data-ttu-id="de9c3-102">Недопустимые символы и правила экранирования</span><span class="sxs-lookup"><span data-stu-id="de9c3-102">Invalid Characters and Escape Rules</span></span>
  <span data-ttu-id="de9c3-103">В данном разделе описана обработка недопустимых символов XML при помощи предложения FOR XML и перечислены правила экранирования для символов, недопустимых в XML-именах.</span><span class="sxs-lookup"><span data-stu-id="de9c3-103">This topic describes how invalid XML characters are handled by the FOR XML clause, and lists the escape rules for characters that are invalid in XML names.</span></span>  
  
## <a name="for-xml-and-invalid-characters"></a><span data-ttu-id="de9c3-104">Предложение FOR XML и недопустимые символы</span><span class="sxs-lookup"><span data-stu-id="de9c3-104">For XML and Invalid Characters</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="de9c3-105">преобразует недопустимые XML-символы в сущности, когда они возвращаются в запросах FOR XML, не содержащих директивы TYPE.</span><span class="sxs-lookup"><span data-stu-id="de9c3-105">entitizes invalid XML characters when they are returned within FOR XML queries that do not use the TYPE directive.</span></span>  
  
 <span data-ttu-id="de9c3-106">Хотя синтаксические анализаторы, следующие стандарту XML 1.0, будут выводить ошибку независимо от того, преобразованы ли такие символы в сущности, это поведение более соответствует XML 1.1.</span><span class="sxs-lookup"><span data-stu-id="de9c3-106">Although XML 1.0 conformant parsers raise parse errors regardless of whether these characters are entitized or not, the entitized form is better aligned with XML 1.1.</span></span> <span data-ttu-id="de9c3-107">Представление таких символов в виде сущностей также может оказаться более согласованным с будущими версиями стандарта XML.</span><span class="sxs-lookup"><span data-stu-id="de9c3-107">The entitized form is also potentially better aligned with future versions of the XML standard.</span></span> <span data-ttu-id="de9c3-108">Кроме того, таким образом упрощается отладка, так как становится виден элемент кода, содержащий недопустимый символ.</span><span class="sxs-lookup"><span data-stu-id="de9c3-108">Additionally, it makes debugging simpler, because the code point of the invalid character becomes visible.</span></span>  
  
 <span data-ttu-id="de9c3-109">Пользователям инструментов XML не требуется делать никаких обновлений, так как анализатор XML в любом случае выдаст ошибку, встретив в потоке данных недопустимый символ.</span><span class="sxs-lookup"><span data-stu-id="de9c3-109">For users of XML tools, no workaround is required, because the XML parser will fail either way at the point where the invalid characters occur in the data stream.</span></span> <span data-ttu-id="de9c3-110">При использовании других инструментов это изменение может потребовать обновления программной логики для поиска таких символов в виде сущностей.</span><span class="sxs-lookup"><span data-stu-id="de9c3-110">If you use non-XML tools, this change can require you to update your programming logic to search for these characters as entitized values.</span></span>  
  
 <span data-ttu-id="de9c3-111">Следующие символы пробела в результатах запросов FOR XML преобразуются в сущности иным образом с целью их сохранения для обратных преобразований.</span><span class="sxs-lookup"><span data-stu-id="de9c3-111">The following white space characters are entitized differently in FOR XML queries to preserve their presence through round-tripping:</span></span>  
  
-   <span data-ttu-id="de9c3-112">В содержимом и атрибутах элементов: **hex(0D)** (возврат каретки)</span><span class="sxs-lookup"><span data-stu-id="de9c3-112">In element content and attributes: **hex(0D)** (carriage return)</span></span>  
  
-   <span data-ttu-id="de9c3-113">В содержимом атрибутов: **hex(09)** (табуляция), **hex(0A)** (перевод строки)</span><span class="sxs-lookup"><span data-stu-id="de9c3-113">In attribute content: **hex(09)** (tab), **hex(0A)** (line feed)</span></span>  
  
 <span data-ttu-id="de9c3-114">Данные символы сохраняются в выходе, и средство синтаксического анализа не выполняет их нормализацию.</span><span class="sxs-lookup"><span data-stu-id="de9c3-114">These characters are preserved in output, and a parser will not normalize them.</span></span>  
  
## <a name="escape-rules"></a><span data-ttu-id="de9c3-115">Правила экранирования</span><span class="sxs-lookup"><span data-stu-id="de9c3-115">Escape Rules</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="de9c3-116">, содержащие недопустимые в именах XML символы, например пробелы, преобразуются в имена XML таким образом, при котором недопустимые символы переводятся в представление соответствующими численными сущностями с экранирующим символом.</span><span class="sxs-lookup"><span data-stu-id="de9c3-116">names that contain characters that are invalid in XML names, such as spaces, are translated into XML names in a way in which the invalid characters are translated into escaped numeric entity encoding.</span></span>  
  
 <span data-ttu-id="de9c3-117">Есть только два небуквенных символа, которые могут встречаться в имени XML: двоеточие (:) и подчеркивание (_).</span><span class="sxs-lookup"><span data-stu-id="de9c3-117">There are only two non-alphabetic characters that can occur within an XML name: the colon (:) and the underscore (_).</span></span> <span data-ttu-id="de9c3-118">Так как двоеточие уже зарезервировано для пространств имен, в качестве escape-символа используется подчеркивание.</span><span class="sxs-lookup"><span data-stu-id="de9c3-118">Because the colon is already reserved for namespaces, the underscore is chosen as the escape character.</span></span> <span data-ttu-id="de9c3-119">Далее перечислены правила кодирования недопустимых символов.</span><span class="sxs-lookup"><span data-stu-id="de9c3-119">Following are the escape rules that are used for encoding:</span></span>  
  
-   <span data-ttu-id="de9c3-120">Все символы UCS-2, которые не могут входить имена XML в соответствии со стандартом XML 1.0, экранируются как _xHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="de9c3-120">Any UCS-2 character that is not a valid XML name character, according to the XML 1.0 specification, is escaped as _xHHHH\_.</span></span> <span data-ttu-id="de9c3-121">Здесь сочетание HHHH будет замещено на четырехразрядный шестнадцатеричный код символа в UCS-2, где самым старшим является первый разряд.</span><span class="sxs-lookup"><span data-stu-id="de9c3-121">The HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="de9c3-122">Например, имя таблицы **Order Details** будет закодировано как Order_x0020_Details.</span><span class="sxs-lookup"><span data-stu-id="de9c3-122">For example, the table name **Order Details** is encoded as Order_x0020_Details.</span></span>  
  
-   <span data-ttu-id="de9c3-123">Символы, не входящие в диапазон UCS-2 (дополнения UCS-4 в диапазоне от U+00010000 до U+0010FFFF), кодируются как _xHHHHHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="de9c3-123">Characters that do not fit into the UCS-2 realm (the UCS-4 additions of the range U+00010000 to U+0010FFFF) are encoded as _xHHHHHHHH\_.</span></span> <span data-ttu-id="de9c3-124">Здесь сочетание HHHHHHHH будет замещено на восьмиразрядный шестнадцатеричный код символа в UCS-4, если используется режим обратной совместимости с SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="de9c3-124">The HHHHHHHH stands for the eight-digit hexadecimal UCS-4 encoding of the character, if under SQL Server 2000 backward compatibility mode.</span></span> <span data-ttu-id="de9c3-125">В иных случаях символы кодируются как _xHHHHHH\_в целях соответствия стандарту ISO.</span><span class="sxs-lookup"><span data-stu-id="de9c3-125">Otherwise, the characters are encoded as_xHHHHHH\_, in order to align with the ISO standard.</span></span>  
  
-   <span data-ttu-id="de9c3-126">Символ нижнего подчеркивания не нуждается в экранировании, если за ним не следует символ x.</span><span class="sxs-lookup"><span data-stu-id="de9c3-126">The underscore character does not have to be escaped unless it is followed by the character x.</span></span> <span data-ttu-id="de9c3-127">Например, имя таблицы **Данные заказа** не будет закодировано.</span><span class="sxs-lookup"><span data-stu-id="de9c3-127">For example, the table name **Order_Details** is not encoded.</span></span>  
  
-   <span data-ttu-id="de9c3-128">Двоеточие в идентификаторах не кодируется. Поэтому запрос FOR XML может формировать элемент пространства имени и имена атрибутов.</span><span class="sxs-lookup"><span data-stu-id="de9c3-128">The colon in identifiers is not escaped As a result, the namespace element and attribute names can be generated by the FOR XML query.</span></span> <span data-ttu-id="de9c3-129">Например, следующий запрос формирует атрибут пространства имен с двоеточием в имени:</span><span class="sxs-lookup"><span data-stu-id="de9c3-129">For example, the following query generates a namespace attribute that has a colon in the name:</span></span>  
  
    ```  
    SELECT 'namespace-urn' as 'xmlns:namespace',   
     1 as 'namespace:a'   
    FOR XML RAW  
    ```  
  
     <span data-ttu-id="de9c3-130">Результат этого запроса будет таким:</span><span class="sxs-lookup"><span data-stu-id="de9c3-130">The query produces this result:</span></span>  
  
    ```  
    <row xmlns:namespace="namespace-urn" namespace:a="1"/>  
    ```  
  
     <span data-ttu-id="de9c3-131">Обратите внимание, что для добавления пространств имен XML рекомендуется использовать предложение WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="de9c3-131">Note that WITH XMLNAMESPACES is the recommended way to add XML namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9c3-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="de9c3-132">See Also</span></span>  
 [<span data-ttu-id="de9c3-133">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="de9c3-133">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
