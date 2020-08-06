---
title: SQLTablePrivileges | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTablePrivileges function
ms.assetid: 8cce22d5-28b1-4b50-a5bc-1de03e0ffd6b
author: rothja
ms.author: jroth
ms.openlocfilehash: 63298330d3f0ebf707dbb42c337553c1f363deab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664176"
---
# <a name="sqltableprivileges"></a><span data-ttu-id="afc86-102">SQLTablePrivileges</span><span class="sxs-lookup"><span data-stu-id="afc86-102">SQLTablePrivileges</span></span>
  <span data-ttu-id="afc86-103">Функция**SQLTablePrivileges** может быть выполнена для статического курсора.</span><span class="sxs-lookup"><span data-stu-id="afc86-103">**SQLTablePrivileges** can be executed on a static cursor.</span></span> <span data-ttu-id="afc86-104">При попытке выполнить метод **SQLTablePrivileges** для обновляемого курсора (динамического или управляемого набором ключей) будет возвращено значение SQL_SUCCESS_WITH_INFO, которое указывает на то, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="afc86-104">An attempt to execute **SQLTablePrivileges** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="afc86-105">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает выдачу сведений о таблицах, находящихся на связанных серверах, принимая двухкомпонентное имя в параметре *CatalogName* : *Имя_Связанного_Сервера.Имя_Каталога*.</span><span class="sxs-lookup"><span data-stu-id="afc86-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc86-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="afc86-106">See Also</span></span>  
 <span data-ttu-id="afc86-107">[Функция SQLTablePrivileges] (https://go.microsoft.com/fwlink/?LinkId=59373\)</span><span class="sxs-lookup"><span data-stu-id="afc86-107">[SQLTablePrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59373\)</span></span>   
 [<span data-ttu-id="afc86-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="afc86-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
