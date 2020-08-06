---
title: Метод SQLParamData | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: rothja
ms.author: jroth
ms.openlocfilehash: a4e0e8b31a65f28ce83e0d114231bdedd7a35a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668281"
---
# <a name="sqlparamdata"></a><span data-ttu-id="b09f3-102">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="b09f3-102">SQLParamData</span></span>
  <span data-ttu-id="b09f3-103">Когда метод SQLParamData возвращает *валуептрптр* , связанный с возвращающим табличное значение параметром, приложение должно вызвать SQLPutData с *StrLen_Or_Ind*.</span><span class="sxs-lookup"><span data-stu-id="b09f3-103">When SQLParamData returns the *ValuePtrPtr* associated with a table-valued parameter, the application should call SQLPutData with *StrLen_Or_Ind*.</span></span> <span data-ttu-id="b09f3-104">Если *StrLen_Or_Ind* имеет значение больше 0, это означает, что приложение готово для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента, чтобы собрать данные параметров для следующей строки возвращающего табличные значения параметра.</span><span class="sxs-lookup"><span data-stu-id="b09f3-104">If *StrLen_Or_Ind* has a value greater than 0, it means that the application is ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to gather parameter data for the next table-valued parameter row.</span></span> <span data-ttu-id="b09f3-105">Если *StrLen_Or_Ind* имеет значение 0, значит, больше нет строк данных для возвращающего табличные значения параметра.</span><span class="sxs-lookup"><span data-stu-id="b09f3-105">If *StrLen_Or_Ind* has a value of 0, it means there are no more rows of data for the table-valued parameter.</span></span> <span data-ttu-id="b09f3-106">Дополнительные сведения см. в разделе [Привязка и передача данных значений параметров и столбцов, возвращающих](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)табличное значение.</span><span class="sxs-lookup"><span data-stu-id="b09f3-106">For more information, see [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="b09f3-107">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b09f3-107">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09f3-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="b09f3-108">See Also</span></span>  
 <span data-ttu-id="b09f3-109">[Метод SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span><span class="sxs-lookup"><span data-stu-id="b09f3-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span></span>  
 [<span data-ttu-id="b09f3-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="b09f3-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
