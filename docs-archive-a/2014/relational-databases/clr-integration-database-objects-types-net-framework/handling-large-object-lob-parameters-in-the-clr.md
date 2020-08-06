---
title: Обработка параметров больших объектов (LOB) в среде CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- large data, CLR integration
- LOB data [SQL Server], CLR integration
- SqlBytes data type
- SqlChars data type
ms.assetid: d07956f6-9543-4476-9426-536f95991150
author: rothja
ms.author: jroth
ms.openlocfilehash: ee791c73a6610761c2086723f9e41c2351b37dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751175"
---
# <a name="handling-large-object-lob-parameters-in-the-clr"></a><span data-ttu-id="c4019-102">Обработка параметров больших объектов в среде CLR</span><span class="sxs-lookup"><span data-stu-id="c4019-102">Handling Large Object (LOB) Parameters in the CLR</span></span>
  <span data-ttu-id="c4019-103">Используйте `SqlBytes` и `SqlChars` для передачи параметров больших объектов (LOB) двоичного типа (`varbinary(max)`) и символьного типа (`nvarchar(max)`) соответственно.</span><span class="sxs-lookup"><span data-stu-id="c4019-103">Use `SqlBytes` and `SqlChars` to pass large object (LOB) binary type (`varbinary(max)`) and LOB character type (`nvarchar(max)`) parameters, respectively.</span></span> <span data-ttu-id="c4019-104">Эти типы позволяют передавать значения LOB в потоке из базы данных в процедуры среды CLR, не копируя все значение в управляемое пространство.</span><span class="sxs-lookup"><span data-stu-id="c4019-104">These types allow streaming the LOB values from the database to the common language runtime (CLR) routine, instead of copying the entire value into managed space.</span></span> <span data-ttu-id="c4019-105">Типы данных `SqlBinary` и `SqlString` должны использоваться только для небольших двоичных и строковых значений.</span><span class="sxs-lookup"><span data-stu-id="c4019-105">`SqlBinary` and `SqlString` should be used only for small binary and character string values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4019-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4019-106">See Also</span></span>  
 [<span data-ttu-id="c4019-107">Типы данных SQL Server в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c4019-107">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
