---
title: Многопоточные приложения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666520"
---
# <a name="multithreaded-applications"></a><span data-ttu-id="3bd64-102">Многопоточные приложения</span><span class="sxs-lookup"><span data-stu-id="3bd64-102">Multithreaded Applications</span></span>
  <span data-ttu-id="3bd64-103">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] является многопоточным драйвером.</span><span class="sxs-lookup"><span data-stu-id="3bd64-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver is a multithreaded driver.</span></span> <span data-ttu-id="3bd64-104">Написание многопоточного приложения — альтернатива использованию асинхронных вызовов для обработки нескольких вызовов ODBC.</span><span class="sxs-lookup"><span data-stu-id="3bd64-104">Writing a multithreaded application is an alternative to using asynchronous calls to process multiple ODBC calls.</span></span> <span data-ttu-id="3bd64-105">Поток может выполнить асинхронный вызов ODBC, а другие потоки могут обрабатываться, пока первый поток ожидает ответа на свой вызов.</span><span class="sxs-lookup"><span data-stu-id="3bd64-105">A thread can make a synchronous ODBC call, and other threads can process while the first thread is blocked waiting for the response to its call.</span></span> <span data-ttu-id="3bd64-106">Эта модель эффективнее по сравнению с асинхронными вызовами, поскольку исключает такие издержки, как сетевой трафик и повторные вызовы функций ODBC с целью проверки значения SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="3bd64-106">This model is more efficient than making asynchronous calls because it eliminates overhead such as network traffic and making repeated ODBC function calls testing for SQL_STILL_EXECUTING.</span></span>  
  
 <span data-ttu-id="3bd64-107">Асинхронный режим все же остается эффективным методом обработки.</span><span class="sxs-lookup"><span data-stu-id="3bd64-107">Asynchronous mode is still an effective method of processing.</span></span> <span data-ttu-id="3bd64-108">Выигрыш в производительности многопоточной модели недостаточен, чтобы стала оправданной переработка асинхронных приложений.</span><span class="sxs-lookup"><span data-stu-id="3bd64-108">The performance improvements of a multithreaded model are not enough to justify rewriting asynchronous applications.</span></span> <span data-ttu-id="3bd64-109">Если пользователям приходится преобразовывать приложения DB-Library, в которых используется асинхронная модель DB-Library, то проще преобразовать их в асинхронную модель ODBC.</span><span class="sxs-lookup"><span data-stu-id="3bd64-109">If users are converting DB-Library applications that use the DB-Library asynchronous model, it is easier to convert them to the ODBC asynchronous model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd64-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="3bd64-110">See Also</span></span>  
 [<span data-ttu-id="3bd64-111">Создание драйвера ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="3bd64-111">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
