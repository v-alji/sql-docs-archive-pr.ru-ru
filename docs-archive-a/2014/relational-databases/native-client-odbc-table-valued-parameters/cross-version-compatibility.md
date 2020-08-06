---
title: Совместимость между версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), cross-version compatibility
ms.assetid: 5f14850b-b85c-41e2-8116-6f5b3f5e0856
author: rothja
ms.author: jroth
ms.openlocfilehash: af434713946f5c568ee71644a7403f9496a8c16f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667076"
---
# <a name="cross-version-compatibility"></a><span data-ttu-id="ba704-102">Совместимость версий</span><span class="sxs-lookup"><span data-stu-id="ba704-102">Cross-Version Compatibility</span></span>
  <span data-ttu-id="ba704-103">Конфликты между версиями могут происходить, если экземпляры клиента или сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], предшествующие [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], участвуют в обработке возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="ba704-103">Cross-version conflicts can occur when client or server instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] are expected to process table-valued parameters.</span></span>  
  
 <span data-ttu-id="ba704-104">В общем случае функциональные возможности возвращающих табличное значение параметров доступны только клиентам [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (с помощью собственного клиента SQL Server версии 10.0) или более поздних версий, соединенных с серверами [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="ba704-104">In general, table-valued parameter functionality is only available to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] clients (using SQL Server Native Client 10.0) or later that are connected to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) servers.</span></span> <span data-ttu-id="ba704-105">Новые столбцы в результирующих наборах функций каталога будут представлены только при подключении к [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] серверу (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="ba704-105">New columns in catalog function result sets will only be present when connected to a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) server.</span></span>  
  
 <span data-ttu-id="ba704-106">Если клиентское приложение, скомпилированное с помощью собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предыдущей версии, выполняет инструкции, которые ожидают возвращающие табличное значение параметры, то сервер определяет это условие как ошибку преобразования данных, и ODBC возвращает код SQLSTATE 07006 и сообщение «Нарушение атрибута ограниченного типа данных».</span><span class="sxs-lookup"><span data-stu-id="ba704-106">If a client application compiled with an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client executes statements that expect table-valued parameters, the server detects this condition through a data conversion error, and ODBC returns this as a SQLSTATE 07006 and the message "Restricted data type attribute violation".</span></span>  
  
 <span data-ttu-id="ba704-107">Если клиентское приложение, скомпилированное с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента 10,0 или более поздней версии, пытается использовать возвращающие табличное значение параметры при соединении с экземпляром сервера, выпущенным ранее [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент обнаружит это, а вызовы SQLBindCol, SQLBindParameter, склсетдескфиелдс и SQLSetDescRec будут завершаться ошибкой с кодом SQLSTATE 07006, а сообщение "нарушение атрибута ограниченного типа данных (версия SQL Server для этого соединения не поддерживает</span><span class="sxs-lookup"><span data-stu-id="ba704-107">If a client application that was compiled with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 or later tries to use table-valued parameters when connected to a server instance earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will detect this, and SQLBindCol, SQLBindParameter, SQLSetDescFields, and SQLSetDescRec calls will fail with SQLSTATE 07006 and the message "Restricted data type attribute violation (the version of SQL Server for this connection does not support table-valued parameters)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba704-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba704-108">See Also</span></span>  
 [<span data-ttu-id="ba704-109">Возвращающие табличное значение параметры &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ba704-109">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
