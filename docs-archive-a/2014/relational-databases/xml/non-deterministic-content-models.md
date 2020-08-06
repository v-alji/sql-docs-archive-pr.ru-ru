---
title: Недетерминированные модели содержимого | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729150"
---
# <a name="non-deterministic-content-models"></a><span data-ttu-id="310a1-102">недетерминированные модели содержимого</span><span class="sxs-lookup"><span data-stu-id="310a1-102">Non-Deterministic Content Models</span></span>
  <span data-ttu-id="310a1-103">В версиях, предшествующих [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 1 (SP1), схемы XML, содержащие недетерминированные модели содержимого, отклонялись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="310a1-103">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejected XML schemas that had non-deterministic content models.</span></span>  
  
 <span data-ttu-id="310a1-104">Начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 1 (SP1) недетерминированные модели содержимого принимаются, если ограничение вхождений равно 0, 1 или без ограничений.</span><span class="sxs-lookup"><span data-stu-id="310a1-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, however, non-deterministic content models are accepted if the occurrence constraints are 0,1, or unbounded.</span></span>  
  
## <a name="example-non-deterministic-content-model-rejected"></a><span data-ttu-id="310a1-105">Пример Недетерминированные модели содержимого отклоняются</span><span class="sxs-lookup"><span data-stu-id="310a1-105">Example: Non-deterministic content model rejected</span></span>  
 <span data-ttu-id="310a1-106">В следующем примере предпринимается попытка создать XML-схему с недетерминированной моделью содержимого.</span><span class="sxs-lookup"><span data-stu-id="310a1-106">The following example attempts to create an XML schema with a non-deterministic content model.</span></span> <span data-ttu-id="310a1-107">Выполнение этого кода приведет к ошибке, поскольку неясно, должен ли элемент `<root>` содержать последовательность из двух элементов `<a>` или же элемент `<root>` должен содержать две последовательности, состоящие из элемента `<a>` .</span><span class="sxs-lookup"><span data-stu-id="310a1-107">The code fails because it is not clear whether the `<root>` element should have a sequence of two `<a>` elements or if the `<root>` element should have two sequences, each with an `<a>` element.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 <span data-ttu-id="310a1-108">Эту схему можно исправить перемещением ограничения вхождения в однозначное расположение.</span><span class="sxs-lookup"><span data-stu-id="310a1-108">The schema can be fixed by moving the occurrence constraint to a unique location.</span></span> <span data-ttu-id="310a1-109">Например, ограничение можно переместить в содержащий последовательность примитив:</span><span class="sxs-lookup"><span data-stu-id="310a1-109">For example, the constraint can be moved to the containing sequence particle:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 <span data-ttu-id="310a1-110">Ограничение можно также переместить во вложенный элемент:</span><span class="sxs-lookup"><span data-stu-id="310a1-110">Or the constraint can be moved to the contained element:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a><span data-ttu-id="310a1-111">Пример Недетерминированные модели содержимого принимаются</span><span class="sxs-lookup"><span data-stu-id="310a1-111">Example: Non-deterministic content model accepted</span></span>  
 <span data-ttu-id="310a1-112">Следующая схема отклоняется в версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , предшествующих [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="310a1-112">The following schema would be rejected in versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="310a1-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="310a1-113">See Also</span></span>  
 [<span data-ttu-id="310a1-114">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="310a1-114">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
