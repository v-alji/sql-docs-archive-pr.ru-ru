---
title: Обработка результатов хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], results
ms.assetid: 788ef2a4-17de-4526-960b-46bf29aafc9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 5f37a6d8beff88748fa944293bd67f449d29eff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750855"
---
# <a name="processing-stored-procedure-results"></a><span data-ttu-id="19a49-102">Обработка результатов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="19a49-102">Processing Stored Procedure Results</span></span>
  <span data-ttu-id="19a49-103">Хранимые процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используют для возвращения данных следующие четыре механизма.</span><span class="sxs-lookup"><span data-stu-id="19a49-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures have four mechanisms used to return data:</span></span>  
  
-   <span data-ttu-id="19a49-104">Каждая инструкция SELECT в хранимой процедуре формирует результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="19a49-104">Each SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="19a49-105">Процедура может возвращать данные через выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="19a49-105">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="19a49-106">Выходной параметр курсора может передать обратно серверный курсор [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19a49-106">A cursor output parameter can pass back a [!INCLUDE[tsql](../../includes/tsql-md.md)] server cursor.</span></span>  
  
-   <span data-ttu-id="19a49-107">Процедура может иметь целочисленный код возврата.</span><span class="sxs-lookup"><span data-stu-id="19a49-107">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="19a49-108">Приложения должны обрабатывать все эти выходы хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="19a49-108">Applications must be able to handle all these outputs from stored procedures.</span></span> <span data-ttu-id="19a49-109">Инструкции CALL или EXECUTE должны включать маркеры параметров для кода возврата и выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="19a49-109">The CALL or EXECUTE statement should include parameter markers for the return code and output parameters.</span></span> <span data-ttu-id="19a49-110">Используйте [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) , чтобы привязать их все как выходные параметры, а [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента передает выходные значения в привязанные переменные.</span><span class="sxs-lookup"><span data-stu-id="19a49-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind them all as output parameters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will transfer the output values to the bound variables.</span></span> <span data-ttu-id="19a49-111">Выходные параметры и коды возврата — это последние элементы, возвращаемые клиенту [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . они не возвращаются в приложение, пока [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) не возвратит SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="19a49-111">Output parameters and return codes are the last items returned to the client by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they are not returned to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="19a49-112">ODBC не поддерживает привязку параметров курсора [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19a49-112">ODBC does not support binding [!INCLUDE[tsql](../../includes/tsql-md.md)] cursor parameters.</span></span> <span data-ttu-id="19a49-113">Поскольку все выходные параметры должны быть связаны до выполнения процедуры, приложение ODBC не может вызывать хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)], содержащие выходной параметр курсора.</span><span class="sxs-lookup"><span data-stu-id="19a49-113">Because all output parameters must be bound before executing a procedure, any [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure that contains an output cursor parameter cannot be called by ODBC applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a49-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="19a49-114">See Also</span></span>  
 [<span data-ttu-id="19a49-115">Выполнение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="19a49-115">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
