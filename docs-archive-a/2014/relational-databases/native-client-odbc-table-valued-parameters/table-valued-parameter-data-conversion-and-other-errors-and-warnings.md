---
title: Преобразование данных возвращающего табличное значение параметра и другие ошибки и предупреждения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), data conversion
- table-valued parameters (ODBC), error messages
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
author: rothja
ms.author: jroth
ms.openlocfilehash: 45b9ba7f91b54548e096bbe47da6e01ba562f59d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655109"
---
# <a name="table-valued-parameter-data-conversion-and-other-errors-and-warnings"></a><span data-ttu-id="98543-102">Ошибки и предупреждения преобразования данных возвращающих табличное значение параметров и другие</span><span class="sxs-lookup"><span data-stu-id="98543-102">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>
  <span data-ttu-id="98543-103">Значения столбцов возвращающих табличные значения параметров могут преобразовываться из клиентских типов данных в серверные и обратно таким же образом, как и значения других столбцов и параметров.</span><span class="sxs-lookup"><span data-stu-id="98543-103">Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values.</span></span> <span data-ttu-id="98543-104">Но поскольку возвращающий табличное значение параметр может содержать несколько столбцов и несколько строк, важно иметь возможность идентификации фактического значения там, где возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="98543-104">But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.</span></span>  
  
 <span data-ttu-id="98543-105">При обнаружении ошибки или предупреждения в столбце параметра, возвращающего табличное значение, собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] формирует диагностическую запись.</span><span class="sxs-lookup"><span data-stu-id="98543-105">When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record.</span></span> <span data-ttu-id="98543-106">Сообщение об ошибке содержит номер возвращающего табличное значение параметра, а также порядковый номер столбца и номер строки.</span><span class="sxs-lookup"><span data-stu-id="98543-106">The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number.</span></span> <span data-ttu-id="98543-107">Приложение может также использовать диагностические поля SQL_DIAG_SS_TABLE_COLUMN_NUMBER и SQL_DIAG_SS_TABLE_ROW_NUMBER внутри диагностических записей для определения того, какие значения ассоциируются с ошибками и предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="98543-107">An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings.</span></span> <span data-ttu-id="98543-108">Эти диагностические поля доступны в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="98543-108">These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span>  
  
 <span data-ttu-id="98543-109">Во всех прочих отношениях SQLSTATE и компоненты сообщений диагностических записей соответствуют существующим нормам функционирования ODBC.</span><span class="sxs-lookup"><span data-stu-id="98543-109">The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects.</span></span> <span data-ttu-id="98543-110">То есть, за исключением сведений о параметрах, строках и столбцах, сообщения об ошибках имеют одинаковые значения для возвращающих табличное значение параметров, так же как и для параметров, не возвращающих табличное значение.</span><span class="sxs-lookup"><span data-stu-id="98543-110">That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non-table-valued parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98543-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="98543-111">See Also</span></span>  
 [<span data-ttu-id="98543-112">Возвращающие табличное значение параметры &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="98543-112">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
