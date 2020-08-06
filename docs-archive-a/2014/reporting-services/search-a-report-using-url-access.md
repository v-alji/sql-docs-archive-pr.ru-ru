---
title: Поиск отчета с использованием URL-адресов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- searching reports
- text searches [Reporting Services]
- URL access [Reporting Services], report searches
ms.assetid: 6f3410c4-7944-448f-bae8-bab3e8152d46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b45f3fabf58a0980d41ee7b4b89a771655477d02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739191"
---
# <a name="search-a-report-using-url-access"></a><span data-ttu-id="0295d-102">Поиск отчета с использованием URL-адресов</span><span class="sxs-lookup"><span data-stu-id="0295d-102">Search a Report Using URL Access</span></span>
  <span data-ttu-id="0295d-103">URL-адрес можно использовать для поиска в отчете определенного текста.</span><span class="sxs-lookup"><span data-stu-id="0295d-103">You can search a report for a specific set of text using URL access.</span></span> <span data-ttu-id="0295d-104">Для поиска в отчете задайте в качестве значения параметра *rc:FindString* в URL-адресе текст, который необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="0295d-104">To search a report, set the value of the *rc:FindString* parameter on the URL equal to the text for which you want to search.</span></span> <span data-ttu-id="0295d-105">Можно также использовать параметры *rc:StartFind* и *rc:EndFind* , чтобы сузить поиск определенными страницами внутри отчета.</span><span class="sxs-lookup"><span data-stu-id="0295d-105">Additionally, use the *rc:StartFind* and *rc:EndFind* parameters to narrow your search to specific pages within the report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0295d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0295d-106">Example</span></span>  
 <span data-ttu-id="0295d-107">В следующем примере выполняется поиск первого упоминания текста «Mountain-400» в образце отчета «Каталог продукции», начиная с первой страницы и заканчивая пятой:</span><span class="sxs-lookup"><span data-stu-id="0295d-107">The following URL access example searches for the first occurrence of the text "Mountain-400" in the Product Catalog sample report starting with page one and ending with page five:</span></span>  
  
```  
http://server/Reportserver?/SampleReports/Product Catalog&rs:Command=Render&rc:StartFind=1&rc:EndFind=5&rc:FindString=Mountain-400  
```  
  
## <a name="see-also"></a><span data-ttu-id="0295d-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="0295d-108">See Also</span></span>  
 <span data-ttu-id="0295d-109">[Доступ по URL-адресу (службы SSRS)](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0295d-109">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="0295d-110">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="0295d-110">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
