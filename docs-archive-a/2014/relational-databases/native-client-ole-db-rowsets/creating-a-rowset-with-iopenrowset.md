---
title: Создание набора строк с помощью интерфейса IOpenRowset | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
author: rothja
ms.author: jroth
ms.openlocfilehash: bf74466a698d39f74b9531adaa54c79c75e50ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739812"
---
# <a name="creating-a-rowset-with-iopenrowset"></a><span data-ttu-id="41322-102">Создание набора строк с помощью интерфейса IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="41322-102">Creating a Rowset with IOpenRowset</span></span>
  <span data-ttu-id="41322-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB Native Client поддерживает метод **IOpenRowset:: OPENROWSET** со следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="41322-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the **IOpenRowset::OpenRowset** method with the following restrictions:</span></span>  
  
-   <span data-ttu-id="41322-104">Базовая таблица или представление должны быть определены в структуре идентификатора базы данных (DBID), на которую указывает параметр *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="41322-104">A base table or view must be specified in a database ID (DBID) structure that the *pTableID* parameter points to.</span></span>  
  
-   <span data-ttu-id="41322-105">Член DBID *eKind* должен указывать DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="41322-105">The DBID *eKind* member must indicate DBKIND_NAME.</span></span>  
  
-   <span data-ttu-id="41322-106">Член DBID *uName* должен содержать имя существующей базовой таблицы или представления в виде строки в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="41322-106">The DBID *uName* member must specify the name of an existing base table or a view as a Unicode character string.</span></span>  
  
-   <span data-ttu-id="41322-107">Параметр *pIndexID* компонента **OpenRowset** должен иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41322-107">The *pIndexID* parameter of **OpenRowset** must be NULL.</span></span>  
  
 <span data-ttu-id="41322-108">Результирующий набор интерфейса **IOpenRowset::OpenRowset** содержит один набор строк.</span><span class="sxs-lookup"><span data-stu-id="41322-108">The result set of **IOpenRowset::OpenRowset** contains a single rowset.</span></span> <span data-ttu-id="41322-109">Результирующие наборы, содержащие один набор строк, могут поддерживаться [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] курсорами.</span><span class="sxs-lookup"><span data-stu-id="41322-109">Result sets that contain a single rowset can be supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="41322-110">Благодаря поддержке курсоров разработчик может использовать механизмы параллелизма [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41322-110">Cursor support allows the developer to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41322-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="41322-111">See Also</span></span>  
 [<span data-ttu-id="41322-112">Наборы строк</span><span class="sxs-lookup"><span data-stu-id="41322-112">Rowsets</span></span>](rowsets.md)  
  
  
