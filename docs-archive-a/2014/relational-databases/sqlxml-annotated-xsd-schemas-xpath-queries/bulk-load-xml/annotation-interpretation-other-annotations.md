---
title: Другие заметки (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: rothja
ms.author: jroth
ms.openlocfilehash: b654568c93df0a0c3e08cf6eaa615b7026a9c18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664106"
---
# <a name="other-annotations-sqlxml-40"></a><span data-ttu-id="05559-102">Другие заметки (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="05559-102">Other Annotations (SQLXML 4.0)</span></span>
  <span data-ttu-id="05559-103">Помимо заметок, описанных в предыдущих подразделах этого раздела, массовая загрузка XML интерпретирует ниже приведенные заметки.</span><span class="sxs-lookup"><span data-stu-id="05559-103">In addition to the annotations discussed in the previous topics in this section, XML Bulk Load interprets these other annotations, as follows:</span></span>  
  
 `sql:id-prefix`  
 <span data-ttu-id="05559-104">Если схема указывает префиксы к XML-данным, то перед передачей данных в Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]массовая загрузка XML удаляет эти префиксы.</span><span class="sxs-lookup"><span data-stu-id="05559-104">If the schema specifies prefixes to the XML data, XML Bulk Load removes the prefixes before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:use-cdata`  
 <span data-ttu-id="05559-105">Массовая загрузка XML считывает текст, хранящийся в разделах CDATA, и отправляет его в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05559-105">XML Bulk Load reads the text that is stored in the CDATA sections and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:url-encode`  
 <span data-ttu-id="05559-106">Массовая загрузка XML не поддерживает эту заметку.</span><span class="sxs-lookup"><span data-stu-id="05559-106">XML Bulk Load does not support this annotation.</span></span> <span data-ttu-id="05559-107">Например, в выходных XML-данных нельзя указать URL-адрес и ожидать, что массовая загрузка XML считает данные из местоположения и сохранит их в базе данных.</span><span class="sxs-lookup"><span data-stu-id="05559-107">For example, you cannot specify a URL in the XML data input and expect XML Bulk Load to read data from that location to store it in the database.</span></span>  
  
 `sql:is-mapping-schema`  
 <span data-ttu-id="05559-108">Массовая загрузка XML не поддерживает ни эту заметку, ни `sql:id`.</span><span class="sxs-lookup"><span data-stu-id="05559-108">XML Bulk Load does not support this annotation, nor does it support `sql:id`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05559-109">Массовая загрузка XML не поддерживает встроенные схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="05559-109">XML Bulk Load does not support inline mapping schemas.</span></span>  
  
 `sql:key-fields`  
 <span data-ttu-id="05559-110">Массовая загрузка XML никогда не обрабатывает эту заметку.</span><span class="sxs-lookup"><span data-stu-id="05559-110">XML Bulk Load always ignores this annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05559-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="05559-111">See Also</span></span>  
 [<span data-ttu-id="05559-112">Интерпретация аннотации &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="05559-112">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
  
  
