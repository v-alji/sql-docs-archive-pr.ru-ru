---
title: Поддерживаемые конструкции для хранимых процедур, скомпилированных в собственном виде | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658266"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a><span data-ttu-id="bab5f-102">Поддерживаемые конструкции для хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="bab5f-102">Supported Constructs on Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="bab5f-103">В этом разделе перечислены поддерживаемые конструкции в хранимых процедурах, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="bab5f-103">This topic lists the supported constructs on natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="bab5f-104">Дополнительные сведения о неподдерживаемых конструкциях см. в разделе [Конструкции языка Transact-SQL, не поддерживаемые в In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="bab5f-104">For information about unsupported constructs, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="procedure-ddl"></a><span data-ttu-id="bab5f-105">Процедура DDL</span><span class="sxs-lookup"><span data-stu-id="bab5f-105">Procedure DDL</span></span>  
 <span data-ttu-id="bab5f-106">Поддерживаются следующие конструкции:</span><span class="sxs-lookup"><span data-stu-id="bab5f-106">The following are supported:</span></span>  
  
-   <span data-ttu-id="bab5f-107">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="bab5f-107">CREATE PROCEDURE</span></span>  
  
-   <span data-ttu-id="bab5f-108">DROP PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="bab5f-108">DROP PROCEDURE</span></span>  
  
-   <span data-ttu-id="bab5f-109">SCHEMABINDING (требуется для хранимых процедур, скомпилированных в собственном коде)</span><span class="sxs-lookup"><span data-stu-id="bab5f-109">SCHEMABINDING (required for natively compiled stored procedures)</span></span>  
  
-   <span data-ttu-id="bab5f-110">NATIVE_COMPILATION</span><span class="sxs-lookup"><span data-stu-id="bab5f-110">NATIVE_COMPILATION</span></span>  
  
-   <span data-ttu-id="bab5f-111">Параметры могут быть объявлены как NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="bab5f-111">Parameters can be declared as NOT NULL.</span></span>  
  
-   <span data-ttu-id="bab5f-112">Возвращающие табличные значения параметры</span><span class="sxs-lookup"><span data-stu-id="bab5f-112">Table-valued parameters.</span></span>  
  
## <a name="security"></a><span data-ttu-id="bab5f-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="bab5f-113">Security</span></span>  
 <span data-ttu-id="bab5f-114">Поддерживаются следующие конструкции:</span><span class="sxs-lookup"><span data-stu-id="bab5f-114">The following are supported:</span></span>  
  
-   <span data-ttu-id="bab5f-115">Для процедур: EXECUTE от имени владельца, себя и пользователя.</span><span class="sxs-lookup"><span data-stu-id="bab5f-115">For procedures: EXECUTE AS OWNER, SELF, and user.</span></span>  
  
-   <span data-ttu-id="bab5f-116">Разрешения GRANT и DENY для таблиц и процедур.</span><span class="sxs-lookup"><span data-stu-id="bab5f-116">GRANT and DENY permissions on tables and procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab5f-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bab5f-117">See Also</span></span>  
 [<span data-ttu-id="bab5f-118">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="bab5f-118">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
