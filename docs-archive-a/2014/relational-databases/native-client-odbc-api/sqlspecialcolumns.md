---
title: SQLSpecialColumns | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: rothja
ms.author: jroth
ms.openlocfilehash: c36ff73606e95ed7ee5e713b81acf7c177a42563
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664177"
---
# <a name="sqlspecialcolumns"></a><span data-ttu-id="92a4d-102">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="92a4d-102">SQLSpecialColumns</span></span>
  <span data-ttu-id="92a4d-103">При запросе идентификаторов строк (*идентифиертипе* SQL_BEST_ROWID) **SQLSpecialColumns** возвращает пустой результирующий набор (без строк данных) для запрошенной области, отличной от SQL_SCOPE_CURROW.</span><span class="sxs-lookup"><span data-stu-id="92a4d-103">When requesting row identifiers (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** returns an empty result set (no data rows) for any requested scope other than SQL_SCOPE_CURROW.</span></span> <span data-ttu-id="92a4d-104">Сформированный результирующий набор определяет, что столбцы допустимы только внутри этой области.</span><span class="sxs-lookup"><span data-stu-id="92a4d-104">The generated result set indicates that the columns are only valid within this scope.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="92a4d-105">не поддерживает псевдостолбцы для идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="92a4d-105">does not support pseudocolumns for identifiers.</span></span> <span data-ttu-id="92a4d-106">Результирующий набор **SQLSpecialColumns** будет обозначать все столбцы как SQL_PC_NOT_PSEUDO.</span><span class="sxs-lookup"><span data-stu-id="92a4d-106">The **SQLSpecialColumns** result set will identify all columns as SQL_PC_NOT_PSEUDO.</span></span>  
  
 <span data-ttu-id="92a4d-107">**SQLSpecialColumns** может выполняться для статического курсора.</span><span class="sxs-lookup"><span data-stu-id="92a4d-107">**SQLSpecialColumns** can be executed on a static cursor.</span></span> <span data-ttu-id="92a4d-108">Попытка выполнить **SQLSpecialColumns** на обновляемом (управляемом набором ключей или динамическом) методе возвращает SQL_SUCCESS_WITH_INFO, указывающее, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="92a4d-108">An attempt to execute **SQLSpecialColumns** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="92a4d-109">Поддержка функцией SQLSpecialColumns улучшенных функций работы с данными в формате даты-времени</span><span class="sxs-lookup"><span data-stu-id="92a4d-109">SQLSpecialColumns Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="92a4d-110">Сведения о значениях, возвращаемых для столбцов DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH и DECIMAL_DIGTS для типов даты и времени см. в разделе [метаданные каталога](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="92a4d-110">For information about the values returned for the columns DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH, and DECIMAL_DIGTS for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="92a4d-111">Дополнительные общие сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="92a4d-111">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a><span data-ttu-id="92a4d-112">Поддержка функцией SQLSpecialColumns определяемых пользователем типов больших данных CLR</span><span class="sxs-lookup"><span data-stu-id="92a4d-112">SQLSpecialColumns Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="92a4d-113">**SQLSpecialColumns** поддерживает большие определяемые пользователем типы данных CLR (UDT).</span><span class="sxs-lookup"><span data-stu-id="92a4d-113">**SQLSpecialColumns** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="92a4d-114">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="92a4d-114">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a4d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="92a4d-115">See Also</span></span>  
 <span data-ttu-id="92a4d-116">[Функция SQLSpecialColumns](https://go.microsoft.com/fwlink/?LinkId=59371) </span><span class="sxs-lookup"><span data-stu-id="92a4d-116">[SQLSpecialColumns Function](https://go.microsoft.com/fwlink/?LinkId=59371) </span></span>  
 [<span data-ttu-id="92a4d-117">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="92a4d-117">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
