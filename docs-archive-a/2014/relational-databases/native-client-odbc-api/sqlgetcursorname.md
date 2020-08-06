---
title: SQLGetCursorName | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetCursorName function
ms.assetid: 3a427a23-28ef-49aa-b9ec-6cab0914bdf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 01ce6e42b4e8753d07309ec7ce298d4f743d4a6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654262"
---
# <a name="sqlgetcursorname"></a><span data-ttu-id="0d095-102">SQLGetCursorName</span><span class="sxs-lookup"><span data-stu-id="0d095-102">SQLGetCursorName</span></span>
  <span data-ttu-id="0d095-103">Если приложение не указывает имени курсора, драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] формирует его для приложения после создании курсора.</span><span class="sxs-lookup"><span data-stu-id="0d095-103">If the application does not specify a cursor name, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates one for the application upon cursor generation.</span></span> <span data-ttu-id="0d095-104">Приложение может использовать **SQLGetCursorName** , чтобы получить определенное драйвером имя курсора для позиционированных инструкций UPDATE и DELETE.</span><span class="sxs-lookup"><span data-stu-id="0d095-104">The application can use **SQLGetCursorName** to retrieve the driver-defined cursor name for positioned UPDATE and DELETE statements.</span></span> <span data-ttu-id="0d095-105">Приложению не требуется вызывать **SQLSetCursorName** , чтобы использовать преимущества позиционированных инструкций по обработке данных.</span><span class="sxs-lookup"><span data-stu-id="0d095-105">The application does not need to call **SQLSetCursorName** to take advantage of positioned data manipulation statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d095-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d095-106">See Also</span></span>  
 <span data-ttu-id="0d095-107">[Функция SQLGetCursorName](https://go.microsoft.com/fwlink/?LinkId=59349) </span><span class="sxs-lookup"><span data-stu-id="0d095-107">[SQLGetCursorName Function](https://go.microsoft.com/fwlink/?LinkId=59349) </span></span>  
 [<span data-ttu-id="0d095-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="0d095-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
