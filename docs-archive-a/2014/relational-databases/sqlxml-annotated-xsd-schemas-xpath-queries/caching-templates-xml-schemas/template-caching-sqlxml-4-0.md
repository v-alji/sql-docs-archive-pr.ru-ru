---
title: Кэширование шаблонов (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- templates [SQLXML], caching
ms.assetid: 73e151c6-b24e-4422-a116-51e0846bc6f5
author: rothja
ms.author: jroth
ms.openlocfilehash: b2ea8a539086ada1b15abbb9cff4f838af45818c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664098"
---
# <a name="template-caching-sqlxml-40"></a><span data-ttu-id="b7320-102">Кэширование шаблонов (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b7320-102">Template Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="b7320-103">Кэширование шаблонов значительно повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="b7320-103">Template caching significantly improves performance.</span></span> <span data-ttu-id="b7320-104">Если установлено кэширование шаблонов, при первом выполнении шаблон располагается в памяти.</span><span class="sxs-lookup"><span data-stu-id="b7320-104">If template caching is set, the template remains in memory upon its first execution.</span></span> <span data-ttu-id="b7320-105">Это повышает производительность последующего выполнения шаблона.</span><span class="sxs-lookup"><span data-stu-id="b7320-105">This improves the performance for the subsequent execution of the template.</span></span>  
  
 <span data-ttu-id="b7320-106">Размер кэша шаблонов можно задать, добавив в реестр следующий ключ:</span><span class="sxs-lookup"><span data-stu-id="b7320-106">You can set the template cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\TemplateCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="b7320-107">Размер кэша необходимо указывать, исходя из объема доступной памяти и количества используемых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7320-107">The template size should be set on the basis of the available memory and the number of templates you are using.</span></span> <span data-ttu-id="b7320-108">По умолчанию размер **темплатекачесизе** равен 31.</span><span class="sxs-lookup"><span data-stu-id="b7320-108">The default of **TemplateCacheSize** size is 31.</span></span> <span data-ttu-id="b7320-109">Размер кэша можно увеличить, если доступ к шаблону кажется медленным, или уменьшить при небольшом объеме памяти.</span><span class="sxs-lookup"><span data-stu-id="b7320-109">You can increase the cache size if template access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="b7320-110">Для повышения производительности рекомендуется задать **темплатекачесизе** выше, чем количество шаблонов, которые обычно используются.</span><span class="sxs-lookup"><span data-stu-id="b7320-110">For better performance, it is recommended that you set **TemplateCacheSize** higher than the number of templates you usually use.</span></span> <span data-ttu-id="b7320-111">Если **темлатекачесизе** меньше числа шаблонов, производительность снижается по мере увеличения количества шаблонов.</span><span class="sxs-lookup"><span data-stu-id="b7320-111">If **TemlateCacheSize** is less than the number of templates you have, performance degrades as the number of templates increase.</span></span> <span data-ttu-id="b7320-112">Для **темплатекачесизе** можно задать не более 128.</span><span class="sxs-lookup"><span data-stu-id="b7320-112">The **TemplateCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="b7320-113">При каждом использовании кэшированного шаблона проверяется время изменения файла шаблона, чтобы при необходимости его обновить.</span><span class="sxs-lookup"><span data-stu-id="b7320-113">Every time a cached template is used, the modification time of the template file is checked to see whether it needs to be refreshed.</span></span> <span data-ttu-id="b7320-114">Это происходит потому, что копия на диске новее копии в кэше.</span><span class="sxs-lookup"><span data-stu-id="b7320-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7320-115">Параметры шаблона и свойства команд не кэшируются.</span><span class="sxs-lookup"><span data-stu-id="b7320-115">Template parameters and command properties are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7320-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7320-116">See Also</span></span>  
 <span data-ttu-id="b7320-117">[Кэширование схемы &#40;SQLXML 4,0&#41;](schema-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b7320-117">[Schema Caching &#40;SQLXML 4.0&#41;](schema-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="b7320-118">Кэширование XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b7320-118">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
