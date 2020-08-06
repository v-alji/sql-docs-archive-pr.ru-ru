---
title: Создание встроенных схем XDR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XDR schemas [SQL Server]
- inline XDR schema generation [SQL Server]
- XMLDATA option
- FOR XML clause, inline XDR schema generation
ms.assetid: 2a40d617-9724-4f7d-80a4-a85c702f14d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e2bb7b4b482b79ab5550540dd5b24ffdd8d6636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751972"
---
# <a name="generate-an-inline-xdr-schema"></a><span data-ttu-id="aefa4-102">Создание встроенных схем XDR</span><span class="sxs-lookup"><span data-stu-id="aefa4-102">Generate an Inline XDR Schema</span></span>
  <span data-ttu-id="aefa4-103">При указании в предложении FOR XML директивы **XMLDATA** вместе с результатом запроса возвращается встроенная XDR-схема.</span><span class="sxs-lookup"><span data-stu-id="aefa4-103">The **XMLDATA** directive in FOR XML returns an inline XDR schema together with the query result.</span></span> <span data-ttu-id="aefa4-104">Однако XDR-схема не поддерживает какие-либо новые типы данных и другие усовершенствования в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="aefa4-104">However, the XDR schema does not support all the new data types and other enhancements introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="aefa4-105">Вместо этого с помощью директивы [XMLSCHEMA](generate-an-inline-xsd-schema.md)можно запрашивать встроенную XSD-схему.</span><span class="sxs-lookup"><span data-stu-id="aefa4-105">Instead, you can request an inline XSD schema by using [the XMLSCHEMA directive](generate-an-inline-xsd-schema.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aefa4-106">Директива XMLDATA для параметра XML FOR является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="aefa4-106">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="aefa4-107">В режимах RAW и AUTO следует использовать создание XSD-схем.</span><span class="sxs-lookup"><span data-stu-id="aefa4-107">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="aefa4-108">В режиме EXPLICIT для директивы XMLDATA замены нет.</span><span class="sxs-lookup"><span data-stu-id="aefa4-108">There is no replacement for the XMLDATA directive in EXPLICIT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="aefa4-109">Также имейте в виду следующие сведения, касающиеся поддержки встроенной XSD-схемы:</span><span class="sxs-lookup"><span data-stu-id="aefa4-109">Also note the following about the inline XDR schema support:</span></span>  
  
-   <span data-ttu-id="aefa4-110">Если результат выполнения запроса FOR XML включает в себя столбцы типа **xml** и при этом запрашивается встроенная XSD-схема, будет возвращено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="aefa4-110">If the FOR XML query result includes columns of **xml** type and you request an inline XDR schema, an error is returned.</span></span> <span data-ttu-id="aefa4-111">Встроенная XSD-схема не поддерживает эти типы данных.</span><span class="sxs-lookup"><span data-stu-id="aefa4-111">Inline XDR does not support these types.</span></span>  
  
-   <span data-ttu-id="aefa4-112">Типы данных **(n)varchar(max)** и **(n)varbinary(max)** будут сопоставлены с данными типа **(n)varchar(n)** и **varbinary(n)** соответственно.</span><span class="sxs-lookup"><span data-stu-id="aefa4-112">The **(n)varchar(max)** and **(n)varbinary(max)** types will be mapped to **(n)varchar(n)** and **varbinary(n)**, respectively.</span></span>  
  
-   <span data-ttu-id="aefa4-113">При уровне совместимости 90 или выше значения типа **timestamp** рассматриваются как данные типа **varbinary(8)** , обрабатываются как двоичные данные, а результат обработки возвращается в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="aefa4-113">When compatibility mode is set to 90 or higher, **timestamp** values are considered as **varbinary(8)** data, are treated like binary data, and are returned in the result as follows:</span></span>  
  
    -   <span data-ttu-id="aefa4-114">Если указан параметр **binary base64** , используется кодировка Base 64.</span><span class="sxs-lookup"><span data-stu-id="aefa4-114">Base 64 encoding is used when **binary base64** is specified.</span></span>  
  
    -   <span data-ttu-id="aefa4-115">Если параметр **binary base64** не указан, используется кодировка URL в режиме AUTO.</span><span class="sxs-lookup"><span data-stu-id="aefa4-115">URL encoding is used in AUTO mode when **binary base64** is not specified.</span></span>  
  
  
