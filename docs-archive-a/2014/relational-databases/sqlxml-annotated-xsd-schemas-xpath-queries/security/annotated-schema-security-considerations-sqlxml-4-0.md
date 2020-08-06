---
title: Рекомендации по безопасности схемы с заметками (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping schema [SQLXML], security
- annotated XDR schemas, security
- XDR schemas [SQLXML], security
- annotations [SQLXML]
- annotated XSD schemas, security
- SQLXML, annotated XSD schemas
- SQLXML, annotated XDR schemas
- security [SQLXML], annotated schemas
- XSD schemas [SQLXML], security
ms.assetid: 7d7e44dc-b6d3-4e0f-95c7-8f99930c94f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 098f554410a846ed0223d17117b51025dfcf7897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654986"
---
# <a name="annotated-schema-security-considerations-sqlxml-40"></a><span data-ttu-id="d0416-102">Основные понятия о безопасности схемы с заметками (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d0416-102">Annotated Schema Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="d0416-103">Далее приводятся рекомендации по обеспечению безопасности при использовании аннотированных схем.</span><span class="sxs-lookup"><span data-stu-id="d0416-103">The following are security guidelines for using annotated schemas:</span></span>  
  
-   <span data-ttu-id="d0416-104">Избегайте использования сопоставления по умолчанию в схемах сопоставления. </span><span class="sxs-lookup"><span data-stu-id="d0416-104">Avoid using default mapping in the mapping schemas.</span></span> <span data-ttu-id="d0416-105">Сопоставление по умолчанию предоставляет доступ к информации о базе данных (имена таблиц и столбцов) в результирующем XML-документе, поскольку по умолчанию имена элементов сопоставляются именам таблиц, а имена атрибутов — именам столбцов.</span><span class="sxs-lookup"><span data-stu-id="d0416-105">The default mapping exposes the database information (table and column names) in the resulting XML document because, by default, the element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="d0416-106">Поэтому любой пользователь, увидевший XML-документ, получает доступ к информации о таблицах и столбцах базы данных, что представляет собой потенциальную угрозу безопасности. </span><span class="sxs-lookup"><span data-stu-id="d0416-106">Therefore, any user who sees the XML document has access to the table and column information in the database, presenting a potential security risk.</span></span> <span data-ttu-id="d0416-107">Чтобы избежать этого риска, в схеме следует пользоваться произвольными именами элементов и атрибутов и явным образом сопоставлять их с таблицами и столбцами с помощью заметки. </span><span class="sxs-lookup"><span data-stu-id="d0416-107">To avoid this risk, specify arbitrary element and attribute names in the schema and use annotations to explicitly map them to the tables and columns.</span></span> <span data-ttu-id="d0416-108">Дополнительные сведения об использовании сопоставления по умолчанию при создании схем XSD см. [в разделе Сопоставление элементов и АТРИБУТОВ XSD по умолчанию с таблицами и столбцами &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d0416-108">For more information about using default mapping when you create XSD schemas, see [Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="d0416-109">Явное задание сопоставления с помощью заметок предоставляет информацию о базе данных (например, об именах таблиц и столбцов).</span><span class="sxs-lookup"><span data-stu-id="d0416-109">The explicit mapping specified using the annotations exposes the database information (such as table names and column names).</span></span> <span data-ttu-id="d0416-110">Поэтому бывает нежелательно предоставлять публичный доступ к этим схемам.</span><span class="sxs-lookup"><span data-stu-id="d0416-110">Therefore, you may not want to make these schemas available publicly.</span></span>  
  
-   <span data-ttu-id="d0416-111">Некоторые запросы (например, запросы к схеме сопоставления с рекурсией, заданные с помощью заметки `max-depth` с высоким значением) могут выполняться довольно долго.</span><span class="sxs-lookup"><span data-stu-id="d0416-111">Certain queries such as those specified against mapping schema with recursion (specified using `max-depth` annotation set to a higher value) may take longer to execute.</span></span> <span data-ttu-id="d0416-112">При необходимости можно задать предельное время ожидания, задав свойство времени ожидания команды (в секундах).</span><span class="sxs-lookup"><span data-stu-id="d0416-112">You can optionally specify a time-out limit by setting the Command Time Out property (in seconds).</span></span> <span data-ttu-id="d0416-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="d0416-113">For example:</span></span>  
  
    ```  
    cn.Open "Provider=SQLOLEDB;Server=localhost;Database=tempdb;Integrated Security=SSPI;Command Properties='Command Time Out=50';"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d0416-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0416-114">See Also</span></span>  
 [<span data-ttu-id="d0416-115">Схемы XSD с заметками в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="d0416-115">Annotated XSD Schemas in SQLXML 4.0</span></span>](../../sqlxml/annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
  
  
