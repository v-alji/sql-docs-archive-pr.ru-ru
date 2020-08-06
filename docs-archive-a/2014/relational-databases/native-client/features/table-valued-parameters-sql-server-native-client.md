---
title: Возвращающие табличные значения параметры (SQL Server Native Client) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, table-valued parameters
- table-valued parameters (SQL Server Native Client)
ms.assetid: 5ee6bdcd-0309-4a20-b5c2-0e6b6839f34f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6af4979b9a77c94f52be5197b01179007a971283
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656373"
---
# <a name="table-valued-parameters-sql-server-native-client"></a><span data-ttu-id="29cc3-102">Возвращающие табличное значение параметры (собственный клиент SQL Server)</span><span class="sxs-lookup"><span data-stu-id="29cc3-102">Table-Valued Parameters (SQL Server Native Client)</span></span>
  <span data-ttu-id="29cc3-103">Возвращающие табличное значение параметры появились в [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], и обеспечивают эффективный способ передачи нескольких строк данных на сервер.</span><span class="sxs-lookup"><span data-stu-id="29cc3-103">Table-valued parameters were introduced in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], and provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="29cc3-104">Возвращающие табличное значение параметры предоставляют функциональные возможности, схожие с массивами параметров, но предлагают большую гибкость и более тесную интеграцию с [!INCLUDE[tsql](../../../includes/tsql-md.md)], и могут значительно улучшить производительность.</span><span class="sxs-lookup"><span data-stu-id="29cc3-104">Table-valued parameters provide functionality similar to parameter arrays, but they offer more flexibility and closer integration with [!INCLUDE[tsql](../../../includes/tsql-md.md)], and can frequently improve performance.</span></span> <span data-ttu-id="29cc3-105">Возвращающие табличное значение параметры также могут участвовать в операциях на основе набора, а массивы параметров не могут.</span><span class="sxs-lookup"><span data-stu-id="29cc3-105">Table-valued parameters can also participate in set-based operations, whereas parameter arrays cannot.</span></span>  
  
 <span data-ttu-id="29cc3-106">Дополнительные сведения о возвращающих табличные значения параметрах и ODBC см. в разделе [возвращающие табличное значение параметры &#40;odbc&#41;](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="29cc3-106">For information about table-valued parameters and ODBC, see [Table-Valued Parameters &#40;ODBC&#41;](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
 <span data-ttu-id="29cc3-107">Сведения о параметрах, возвращающих табличное значение, и OLE DB см. этой [статье](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="29cc3-107">For information about table-valued parameters and OLE DB, see [Table-Valued Parameters &#40;OLE DB&#41;](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29cc3-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="29cc3-108">See Also</span></span>  
 [<span data-ttu-id="29cc3-109">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="29cc3-109">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
