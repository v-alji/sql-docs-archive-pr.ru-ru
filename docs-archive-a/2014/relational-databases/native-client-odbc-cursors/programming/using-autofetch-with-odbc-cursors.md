---
title: Использование автоматической выборки с курсорами ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
author: rothja
ms.author: jroth
ms.openlocfilehash: e3d9374cf9ceab4a7e73cc0059783486f2bf9c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666560"
---
# <a name="using-autofetch-with-odbc-cursors"></a><span data-ttu-id="075f7-102">Использование автоматической выборки с помощью курсоров ODBC</span><span class="sxs-lookup"><span data-stu-id="075f7-102">Using Autofetch with ODBC Cursors</span></span>
  <span data-ttu-id="075f7-103">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента поддерживает параметр автоматической выборки при использовании любого типа серверного курсора.</span><span class="sxs-lookup"><span data-stu-id="075f7-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports an autofetch option when using any server cursor type.</span></span> <span data-ttu-id="075f7-104">При автоматической выборке функция **SQLExecute** или **SQLExecDirect** , открывающая курсор, также имеет неявную функцию [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST).</span><span class="sxs-lookup"><span data-stu-id="075f7-104">With autofetch, the **SQLExecute** or **SQLExecDirect** function that opens the cursor also has an implicit [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) function.</span></span> <span data-ttu-id="075f7-105">Строки, составляющие первый набор строк, возвращаются в привязанные переменные приложения в ходе выполнения инструкции; это позволяет сэкономить одно обращение через сеть к серверу</span><span class="sxs-lookup"><span data-stu-id="075f7-105">The rows comprising the first rowset are returned to the bound application variables as part of the statement execution, saving another roundtrip across the network to the server.</span></span> <span data-ttu-id="075f7-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) не поддерживается, если включен параметр автоматической выборки. столбцы результирующего набора должны быть привязаны к переменным программы.</span><span class="sxs-lookup"><span data-stu-id="075f7-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported when the autofetch option is enabled; the result set columns must be bound to program variables.</span></span>  
  
 <span data-ttu-id="075f7-107">Приложения запрашивают автоматическую выборку, задавая для зависящего от драйвера атрибута инструкции SQL_SOPT_SS_CURSOR_OPTIONS значение SQL_CO_AF.</span><span class="sxs-lookup"><span data-stu-id="075f7-107">Applications request autofetch by setting the driver-specific SQL_SOPT_SS_CURSOR_OPTIONS statement attribute to SQL_CO_AF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="075f7-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="075f7-108">See Also</span></span>  
 [<span data-ttu-id="075f7-109">Сведения о программировании курсора &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="075f7-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
