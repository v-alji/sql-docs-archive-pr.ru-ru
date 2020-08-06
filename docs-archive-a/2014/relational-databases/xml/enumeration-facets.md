---
title: Аспекты перечисления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- enumeration facets
ms.assetid: dec23a79-ddd6-4701-9721-55a2c435a34d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e06598890d9b652879327e0351db5113cc17e6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654944"
---
# <a name="enumeration-facets"></a><span data-ttu-id="edb05-102">аспекты перечисления</span><span class="sxs-lookup"><span data-stu-id="edb05-102">Enumeration Facets</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="edb05-103">отклоняет XML-схемы с типами, которые имеют шаблоны аспектов или перечислений, нарушающих эти аспекты.</span><span class="sxs-lookup"><span data-stu-id="edb05-103">rejects XML schemas with types that have pattern facets or enumerations that violate those facets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edb05-104">Пример</span><span class="sxs-lookup"><span data-stu-id="edb05-104">Example</span></span>  
 <span data-ttu-id="edb05-105">Следующая схема была бы отклонена, потому что показанное значение перечисления включает значение, содержащее символы в разных регистрах.</span><span class="sxs-lookup"><span data-stu-id="edb05-105">The following schema would be rejected, because the featured enumeration value includes a mixed-case value.</span></span> <span data-ttu-id="edb05-106">Она также была бы отклонена, потому что это значение нарушает значение шаблона, которое ограничивает значения только символами нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="edb05-106">It would also be rejected because this value violates the pattern value that limits values to only lowercase letters.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MySampleCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" xmlns:ns="http://ns">  
    <simpleType name="MyST">  
       <restriction base="string">  
          <pattern value="[a-z]*"/>  
       </restriction>  
    </simpleType>  
  
    <simpleType name="MyST2">  
       <restriction base="ns:MyST">  
           <enumeration value="mYstring"/>  
       </restriction>  
    </simpleType>  
</schema>'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="edb05-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="edb05-107">See Also</span></span>  
 [<span data-ttu-id="edb05-108">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="edb05-108">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
