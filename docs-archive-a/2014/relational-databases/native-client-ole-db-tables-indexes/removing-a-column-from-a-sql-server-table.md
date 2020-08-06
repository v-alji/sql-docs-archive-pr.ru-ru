---
title: Удаление столбца из таблицы SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: rothja
ms.author: jroth
ms.openlocfilehash: 8f40c466910aae7e0d349cd4a65ab265282bc8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665301"
---
# <a name="removing-a-column-from-a-sql-server-table"></a><span data-ttu-id="89f4a-102">Удаление столбца из таблицы SQL Server</span><span class="sxs-lookup"><span data-stu-id="89f4a-102">Removing a Column from a SQL Server Table</span></span>
  <span data-ttu-id="89f4a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DBа собственного клиента предоставляет функцию **ITableDefinition::D ропколумн** .</span><span class="sxs-lookup"><span data-stu-id="89f4a-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropColumn** function.</span></span> <span data-ttu-id="89f4a-104">Она позволяет пользователю удалить столбец из таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89f4a-104">This allows consumers to remove a column from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="89f4a-105">Пользователь задает имя таблицы в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* в параметре *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="89f4a-105">Consumers specify the table name as a Unicode character string in the *pwszName*member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="89f4a-106">Элемент *eKind* параметра *pTableID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="89f4a-106">The *eKind*member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="89f4a-107">Пользователь задает имя столбца в элементе *pwszName* объединения *uName*, передаваемого в параметре *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="89f4a-107">The consumer indicates a column name in the *pwszName*member of the *uName* union in the *pColumnID* parameter.</span></span> <span data-ttu-id="89f4a-108">Имя столбца задается в виде символьной строки в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="89f4a-108">The column name is a Unicode character string.</span></span> <span data-ttu-id="89f4a-109">Элемент *eKind* параметра *pColumnID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="89f4a-109">The *eKind* member of *pColumnID* must be DBKIND_NAME.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89f4a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="89f4a-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="89f4a-111">Код</span><span class="sxs-lookup"><span data-stu-id="89f4a-111">Code</span></span>  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a><span data-ttu-id="89f4a-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="89f4a-112">See Also</span></span>  
 [<span data-ttu-id="89f4a-113">Таблицы и индексы</span><span class="sxs-lookup"><span data-stu-id="89f4a-113">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
