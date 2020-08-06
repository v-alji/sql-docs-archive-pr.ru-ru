---
title: Кэширование схем (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- schemas [SQLXML]
ms.assetid: 7e5fda21-b435-41fd-b637-8b616560a93f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e36711955fa28bafd3b0996b1a02f6cd71f3c4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667638"
---
# <a name="schema-caching-sqlxml-40"></a><span data-ttu-id="8fd2e-102">Кэширование схем (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="8fd2e-102">Schema Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="8fd2e-103">При параллельной установке XML для Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0 и SQLXML 3.0 можно в явном виде контролировать кэширование схем всех версий с помощью следующих разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-103">With a side-by-side installation of XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0, and SQLXML 3.0, you can explicitly control the schema caching in all versions by using the following registry keys:</span></span>  
  
 <span data-ttu-id="8fd2e-104">Web Release 1.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-104">Web Release 1:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX\SchemaCacheSize  
```  
  
 <span data-ttu-id="8fd2e-105">SQLXML 2,0:</span><span class="sxs-lookup"><span data-stu-id="8fd2e-105">SQLXML 2.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML2\SchemaCacheSize  
```  
  
 <span data-ttu-id="8fd2e-106">SQLXML 3.0:</span><span class="sxs-lookup"><span data-stu-id="8fd2e-106">SQLXML 3.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML3\SchemaCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="8fd2e-107">Дополнительные сведения о параллельной установке см. [в статье новые возможности SQLXML 4,0 с пакетом обновления 1 (SP1)](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span><span class="sxs-lookup"><span data-stu-id="8fd2e-107">For more information about side-by-side installation, see [What's New in SQLXML 4.0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span></span>  
  
 <span data-ttu-id="8fd2e-108">Кэширование схем значительно повышает производительность запроса XPath.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-108">Schema caching significantly improves the performance of an XPath query.</span></span> <span data-ttu-id="8fd2e-109">При выполнении запроса XPath к схеме сопоставления эта схема хранится в памяти, и необходимые структуры данных строятся в памяти.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-109">When an XPath query is executed against a mapping schema, the schema is stored in memory, and the necessary data structures are built in memory.</span></span> <span data-ttu-id="8fd2e-110">Если задано кэширование схем, то схема остается в памяти, тем самым повышая производительность последующих запросов XPath.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-110">If schema caching is set, the schema remains in memory, thereby improving performance for subsequent XPath queries.</span></span>  
  
 <span data-ttu-id="8fd2e-111">Размер кэша для схем можно задать, добавив в реестр указанный выше раздел.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-111">You can set the schema cache size by adding the above key in the registry</span></span>  
  
 <span data-ttu-id="8fd2e-112">Размер схемы устанавливается в зависимости от доступной памяти и количества используемых схем.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-112">The schema size is set based on the available memory and the number of schemas you are using.</span></span> <span data-ttu-id="8fd2e-113">Размер **счемакачесизе** по умолчанию — 31.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-113">The default **SchemaCacheSize** size is 31.</span></span> <span data-ttu-id="8fd2e-114">Если задать **счемакачесизе** выше, будет использоваться больше памяти.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-114">If you set **SchemaCacheSize** higher, more memory is used.</span></span> <span data-ttu-id="8fd2e-115">Поэтому можно увеличить размер кэша, если доступ к схеме происходит медленно, и уменьшить его при нехватке памяти.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-115">Therefore, you can increase the cache size if schema access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="8fd2e-116">По соображениям производительности рекомендуется задавать **счемакачесизе** выше числа используемых схем сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-116">For performance reasons, it is recommended that you set **SchemaCacheSize** higher than the number of mapping schemas you usually use.</span></span> <span data-ttu-id="8fd2e-117">При увеличении числа схем, если **счемакачесизе** меньше числа схем, производительность снижается.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-117">As the number of schemas increase, if **SchemaCacheSize** is less than the number of schemas you have, the performance degrades.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fd2e-118">Не рекомендуется кэшировать схемы во время разработки программ, поскольку изменения, вносимые в схемы, отражаются в кэше примерно через две минуты.</span><span class="sxs-lookup"><span data-stu-id="8fd2e-118">During development, it is recommended that you do not cache the schemas, because the changes to the schemas are not reflected in the cache for about two minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd2e-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="8fd2e-119">See Also</span></span>  
 <span data-ttu-id="8fd2e-120">[Кэширование шаблонов &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="8fd2e-120">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="8fd2e-121">Кэширование XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8fd2e-121">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
