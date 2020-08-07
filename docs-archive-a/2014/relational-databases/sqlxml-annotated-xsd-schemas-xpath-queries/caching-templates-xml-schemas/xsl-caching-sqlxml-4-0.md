---
title: Кэширование XSL (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- XSL caching [SQLXML]
ms.assetid: 91994142-32f0-4d8d-a8cf-eb0d8b1f1999
author: rothja
ms.author: jroth
ms.openlocfilehash: e41f247c34c1b40bedfdf6924a45afe5f63735b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732485"
---
# <a name="xsl-caching-sqlxml-40"></a><span data-ttu-id="a1cc5-102">Кэширование XSL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a1cc5-102">XSL Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="a1cc5-103">Кэширование таблиц стилей XSL повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-103">Caching XSL style sheets improves performance.</span></span> <span data-ttu-id="a1cc5-104">Если кэширование XSL включено, то после первого выполнения таблица стилей XSL остается в памяти. Это повышает производительность последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-104">Upon its first execution, an XSL style sheet remains in memory if XSL caching is set to ON; this improves performance for subsequent processing.</span></span> <span data-ttu-id="a1cc5-105">Значение по умолчанию — ON.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-105">The default setting is ON.</span></span>  
  
 <span data-ttu-id="a1cc5-106">Можно задать размер кэша XSL, добавив в реестр следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-106">You can set the XSL cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\XSLCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="a1cc5-107">Размер кэша XSL должен указываться исходя из доступного объема памяти и количества используемых таблиц стилей XSL.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-107">The XSL cache size should be set on the basis of the available memory and the number of XSL style sheets you are using.</span></span> <span data-ttu-id="a1cc5-108">По умолчанию значение **XSLCacheSize** равно 31.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-108">The default of **XSLCacheSize** size is 31.</span></span> <span data-ttu-id="a1cc5-109">Размер кэша можно увеличить, если доступ к XSL кажется медленным, или уменьшить при небольшом объеме памяти.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-109">You can increase the cache size if XSL access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="a1cc5-110">Чтобы обеспечить наилучшую производительность, рекомендуется указывать значение **XSLCacheSize** , превышающее число обычно используемых таблиц стилей XSL.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-110">For better performance, it is recommended that you set **XSLCacheSize** higher than the number of XSL style sheets you usually use.</span></span> <span data-ttu-id="a1cc5-111">Если значение **XSLCacheSize** меньше числа имеющихся таблиц стилей XSL, то производительность снижается по мере увеличения количества таблиц стилей XSL.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-111">If **XSLCacheSize** is less than the number of XSL style sheets you have, the performance degrades as the number of XSL style sheets increases.</span></span> <span data-ttu-id="a1cc5-112">Максимальное значение **XSLCacheSize** — 128.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-112">The **XSLCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="a1cc5-113">При каждом использовании кэшированной таблицы стилей XSL проверяется время изменения файла XSL, чтобы определить необходимость его обновления.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-113">Every time the cached XSL style sheet is used, the modification time of the XSL file is checked to determine whether it needs to be refreshed.</span></span> <span data-ttu-id="a1cc5-114">Это происходит потому, что копия на диске новее копии в кэше.</span><span class="sxs-lookup"><span data-stu-id="a1cc5-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1cc5-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1cc5-115">See Also</span></span>  
 <span data-ttu-id="a1cc5-116">[Кэширование шаблонов &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="a1cc5-116">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="a1cc5-117">Кэширование схемы &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a1cc5-117">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
  
  
