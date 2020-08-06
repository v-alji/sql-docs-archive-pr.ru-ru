---
title: SQLForeignKeys | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: rothja
ms.author: jroth
ms.openlocfilehash: a61e80867abb8ecb4d2628b74dc9956051c8e4ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657792"
---
# <a name="sqlforeignkeys"></a><span data-ttu-id="aa83a-102">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="aa83a-102">SQLForeignKeys</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aa83a-103">поддерживает каскадные обновления и удаления через механизм ограничения внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="aa83a-103">supports cascading updates and deletes through the foreign key constraint mechanism.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aa83a-104">возвращает значение SQL_CASCADE для столбцов, имеющих признак UPDATE_RULE и DELETE_RULE, если параметр CASCADE задан в предложении ON UPDATE или ON DELETE ограничения FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="aa83a-104">returns SQL_CASCADE for UPDATE_RULE and/or DELETE_RULE columns if CASCADE option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aa83a-105">возвращает значение SQL_NO_ACTION для столбцов, имеющих признак UPDATE_RULE и DELETE_RULE, если параметр NO ACTION задан в предложении ON UPDATE или ON DELETE ограничения FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="aa83a-105">returns SQL_NO_ACTION for UPDATE_RULE and/or DELETE_RULE columns if NO ACTION option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span>  
  
 <span data-ttu-id="aa83a-106">Если в любом параметре функции **SQLForeignKeys** имеются недопустимые значения, функция **SQLForeignKeys** возвращает значение SQL_SUCCESS.</span><span class="sxs-lookup"><span data-stu-id="aa83a-106">When invalid values are present in any **SQLForeignKeys** parameter, **SQLForeignKeys** returns SQL_SUCCESS on execution.</span></span> <span data-ttu-id="aa83a-107">Функция**SQLFetch** возвращает значение SQL_NO_DATA, если в этих параметрах заданы недопустимые значения.</span><span class="sxs-lookup"><span data-stu-id="aa83a-107">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="aa83a-108">Функцию**SQLForeignKeys** можно выполнять в статическом серверном курсоре.</span><span class="sxs-lookup"><span data-stu-id="aa83a-108">**SQLForeignKeys** can be executed on a static server cursor.</span></span> <span data-ttu-id="aa83a-109">При попытке выполнить функцию **SQLForeignKeys** для обновляемого курсора (динамического или набора ключей) будет возвращено значение SQL_SUCCESS_WITH_INFO, которое указывает на то, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="aa83a-109">An attempt to execute **SQLForeignKeys** on an updatable (dynamic or keyset) cursor returns SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="aa83a-110">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает выдачу сведений о таблицах, находящихся на связанных серверах, принимая двухкомпонентное имя в параметрах *FKCatalogName* и *PKCatalogName* : *Имя_Связанного_Сервера.Имя_Каталога*.</span><span class="sxs-lookup"><span data-stu-id="aa83a-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *FKCatalogName* and *PKCatalogName* parameters: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa83a-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa83a-111">See Also</span></span>  
 <span data-ttu-id="aa83a-112">[Функция SQLForeignKeys](https://go.microsoft.com/fwlink/?LinkId=59344) </span><span class="sxs-lookup"><span data-stu-id="aa83a-112">[SQLForeignKeys Function](https://go.microsoft.com/fwlink/?LinkId=59344) </span></span>  
 [<span data-ttu-id="aa83a-113">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="aa83a-113">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
