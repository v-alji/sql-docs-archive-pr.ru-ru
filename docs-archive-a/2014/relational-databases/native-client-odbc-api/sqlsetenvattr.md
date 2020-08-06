---
title: SQLSetEnvAttr | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
author: rothja
ms.author: jroth
ms.openlocfilehash: f0dbd4d01de9ca769c46a93f810f0149f5b86981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668261"
---
# <a name="sqlsetenvattr"></a><span data-ttu-id="9c57f-102">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="9c57f-102">SQLSetEnvAttr</span></span>
  <span data-ttu-id="9c57f-103">[Справочник по программированию ODBC](https://go.microsoft.com/fwlink/?LinkId=45250) определяет способ, с помощью которого драйверы ODBC должны интерпретировать спецификации атрибута **SQLSetEnvAttr** в приложениях, разработанных с использованием API ODBC 2.*x* или ODBC 3.*x* .</span><span class="sxs-lookup"><span data-stu-id="9c57f-103">The [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) defines how ODBC drivers should interpret the **SQLSetEnvAttr** attribute specifications from applications written to either the ODBC 2.*x* or ODBC 3.*x* API.</span></span> <span data-ttu-id="9c57f-104">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] соответствует следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="9c57f-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with those rules.</span></span>  
  
 <span data-ttu-id="9c57f-105">Один из атрибутов, управляемых функцией **SQLSetEnvAttr** , указывает, нужно ли использовать пул соединений.</span><span class="sxs-lookup"><span data-stu-id="9c57f-105">One of the attributes controlled by **SQLSetEnvAttr** is whether connection pooling is to be used.</span></span> <span data-ttu-id="9c57f-106">Если пул соединений используется с ODBC-драйвером собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , то параметр *DriverCompletion* должен быть установлен в значение SQL_DRIVER_NOPROMPT при подключении к [SQLDriverConnect](sqldriverconnect.md) или **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="9c57f-106">If connection pooling is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, the *DriverCompletion* parameter must be set to SQL_DRIVER_NOPROMPT when connecting with either [SQLDriverConnect](sqldriverconnect.md) or **SQLConnect**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c57f-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c57f-107">See Also</span></span>  
 <span data-ttu-id="9c57f-108">[Функция SQLSetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=59369) </span><span class="sxs-lookup"><span data-stu-id="9c57f-108">[SQLSetEnvAttr Function](https://go.microsoft.com/fwlink/?LinkId=59369) </span></span>  
 [<span data-ttu-id="9c57f-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="9c57f-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
