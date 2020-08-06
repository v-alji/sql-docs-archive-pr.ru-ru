---
title: Системные хранимые процедуры XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
author: rothja
ms.author: jroth
ms.openlocfilehash: 2008294fe5bc532dfb6883656420b4189e4da7b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665890"
---
# <a name="xml-system-stored-procedures"></a><span data-ttu-id="65b67-102">Системные хранимые процедуры XML</span><span class="sxs-lookup"><span data-stu-id="65b67-102">XML System Stored Procedures</span></span>
  <span data-ttu-id="65b67-103">СУБД SQL Server предоставляет следующие системные хранимые процедуры, которые используются вместе с инструкцией OPENXML:</span><span class="sxs-lookup"><span data-stu-id="65b67-103">SQL Server provides the following system stored procedures that are used together with OPENXML:</span></span>  
  
-   [<span data-ttu-id="65b67-104">sp_xml_preparedocument (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="65b67-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql)  
  
-   [<span data-ttu-id="65b67-105">sp_xml_removedocument (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="65b67-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql)  
  
 <span data-ttu-id="65b67-106">Чтобы составлять запросы с помощью OPENXML, нужно сначала создать внутреннее представление XML-документа, вызвав процедуру **sp_xml_preparedocument**.</span><span class="sxs-lookup"><span data-stu-id="65b67-106">To write queries by using OPENXML, you must first create an internal representation of the XML document by calling **sp_xml_preparedocument**.</span></span> <span data-ttu-id="65b67-107">Эта хранимая процедура возвращает дескриптор внутреннего представления XML-документа.</span><span class="sxs-lookup"><span data-stu-id="65b67-107">The stored procedure returns a handle to the internal representation of the XML document.</span></span> <span data-ttu-id="65b67-108">Затем этот дескриптор передается инструкции OPENXML.</span><span class="sxs-lookup"><span data-stu-id="65b67-108">This handle is then passed to OPENXML.</span></span> <span data-ttu-id="65b67-109">Инструкция OPENXML предоставляет представления наборов строк документа, основанные на выражениях XPaths.</span><span class="sxs-lookup"><span data-stu-id="65b67-109">OPENXML provides rowset views of the document based on XPaths.</span></span> <span data-ttu-id="65b67-110">Точнее, это одна комбинация для строк и одна или несколько для столбцов.</span><span class="sxs-lookup"><span data-stu-id="65b67-110">Specifically, this is one row pattern and one or more column patterns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65b67-111">Дескриптор документа, возвращаемый процедурой **sp_xml_preparedocument** , действителен в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="65b67-111">The document handle that is returned by **sp_xml_preparedocument** is valid for the duration of the session.</span></span>  
  
 <span data-ttu-id="65b67-112">Внутреннее представление XML-документа можно удалить из памяти вызовом системной хранимой процедуры **sp_xml_removedocument** .</span><span class="sxs-lookup"><span data-stu-id="65b67-112">The internal representation of an XML document can be removed from memory by calling the **sp_xml_removedocument** system stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b67-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="65b67-113">See Also</span></span>  
 <span data-ttu-id="65b67-114">[OPENXML (Transact-SQL)](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="65b67-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="65b67-115">OPENXML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="65b67-115">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
