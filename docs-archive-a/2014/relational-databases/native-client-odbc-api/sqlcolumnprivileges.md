---
title: SQLColumnPrivileges | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: rothja
ms.author: jroth
ms.openlocfilehash: bf46fed47817ed94ea2382f2147df254f2986aec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656393"
---
# <a name="sqlcolumnprivileges"></a><span data-ttu-id="59a42-102">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="59a42-102">SQLColumnPrivileges</span></span>
  <span data-ttu-id="59a42-103">**SQLColumnPrivileges** возвращает значение, SQL_SUCCESS, существуют ли значения для параметров*CatalogName*, *SchemaName*, *TableName*или *ColumnName* .</span><span class="sxs-lookup"><span data-stu-id="59a42-103">**SQLColumnPrivileges** returns SQL_SUCCESS whether or not values exist for the*CatalogName*, *SchemaName*, *TableName*, or *ColumnName* parameters.</span></span> <span data-ttu-id="59a42-104">Функция**SQLFetch** возвращает значение SQL_NO_DATA, если в этих параметрах заданы недопустимые значения.</span><span class="sxs-lookup"><span data-stu-id="59a42-104">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="59a42-105">**SQLColumnPrivileges** может выполняться на статическом серверном курсоре.</span><span class="sxs-lookup"><span data-stu-id="59a42-105">**SQLColumnPrivileges** can be executed on a static server cursor.</span></span> <span data-ttu-id="59a42-106">Попытка выполнить **SQLColumnPrivileges** для обновляемого (динамического или ключевого набора ключей) курсора возвратит SQL_SUCCESS_WITH_INFO, указывающее, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="59a42-106">An attempt to execute **SQLColumnPrivileges** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="59a42-107">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает выдачу сведений о таблицах, находящихся на связанных серверах, принимая двухкомпонентное имя в параметре *CatalogName* : *Имя_Связанного_Сервера.Имя_Каталога*.</span><span class="sxs-lookup"><span data-stu-id="59a42-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a42-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="59a42-108">See Also</span></span>  
 <span data-ttu-id="59a42-109">[Функция SQLColumnPrivileges](https://go.microsoft.com/fwlink/?LinkId=59335) </span><span class="sxs-lookup"><span data-stu-id="59a42-109">[SQLColumnPrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59335) </span></span>  
 [<span data-ttu-id="59a42-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="59a42-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
