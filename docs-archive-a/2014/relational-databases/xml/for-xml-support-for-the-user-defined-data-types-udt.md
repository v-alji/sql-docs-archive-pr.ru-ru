---
title: Поддержка FOR XML для определяемых пользователем типов данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- UDTs [SQL Server], XML
- user-defined types [SQL Server], XML
ms.assetid: 354e2150-fa2a-4583-b1aa-6b78ae4378b6
author: rothja
ms.author: jroth
ms.openlocfilehash: b668ad2da13fdfc880ab26cb2b2759ff3693f7d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751984"
---
# <a name="for-xml-support-for-the-user-defined-data-types-udt"></a><span data-ttu-id="27174-102">Поддержка FOR XML для определяемых пользователем типов данных</span><span class="sxs-lookup"><span data-stu-id="27174-102">FOR XML Support for the User-Defined Data Types (UDT)</span></span>
  <span data-ttu-id="27174-103">FOR XML не поддерживает определяемые пользователем типы данных (UDT) среды CLR.</span><span class="sxs-lookup"><span data-stu-id="27174-103">FOR XML does not support common language runtime (CLR) user-defined data types (UDTs).</span></span>  
  
 <span data-ttu-id="27174-104">Чтобы использовать FOR XML с определяемыми пользователем типами данных среды CRL, убедитесь, что у этих типов данных имеется XML-сериализация, а в предложении SELECT FOR XML используйте явное приведение к типу XML.</span><span class="sxs-lookup"><span data-stu-id="27174-104">To use FOR XML with CLR user-defined data types, make sure that the data type has an XML serialization, and use an explicit cast to XML in the FOR XML select clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27174-105">См. также:</span><span class="sxs-lookup"><span data-stu-id="27174-105">See Also</span></span>  
 [<span data-ttu-id="27174-106">Поддержка FOR XML для различных типов данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="27174-106">FOR XML Support for Various SQL Server Data Types</span></span>](for-xml-support-for-various-sql-server-data-types.md)  
  
  
