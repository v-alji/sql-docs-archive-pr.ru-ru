---
title: Выделение маркера среды | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, environment handles
- ODBC applications, connections
- handles [SQL Server Native Client]
- environment handles [SQLNCLI]
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c655b5e9a406c3e1881c9dd199a92666377918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665321"
---
# <a name="allocating-an-environment-handle"></a><span data-ttu-id="a38a3-102">Выделение дескриптора среды</span><span class="sxs-lookup"><span data-stu-id="a38a3-102">Allocating an Environment Handle</span></span>
  <span data-ttu-id="a38a3-103">Прежде чем в приложении появится возможность вызвать какую-либо функцию ODBC, необходимо инициализировать среду ODBC и выделить дескриптор среды.</span><span class="sxs-lookup"><span data-stu-id="a38a3-103">Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle.</span></span> <span data-ttu-id="a38a3-104">Это — глобальный дескриптор контекста и заполнитель для других дескрипторов в ODBC.</span><span class="sxs-lookup"><span data-stu-id="a38a3-104">This is the global context handle and placeholder for the other handles in ODBC.</span></span> <span data-ttu-id="a38a3-105">Это делается путем вызова **функцию SQLAllocHandle** с параметром *параметром handletype* , для которого задано значение SQL_HANDLE_ENV, а *инпусандле* — значение SQL_NULL_HANDLE.</span><span class="sxs-lookup"><span data-stu-id="a38a3-105">You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.</span></span>  
  
 <span data-ttu-id="a38a3-106">После выделения дескриптора среды приложение должно установить атрибуты среды, чтобы указать, какая версия вызовов функций ODBC будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="a38a3-106">After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using.</span></span> <span data-ttu-id="a38a3-107">Для использования ODBC 3. функции *x* , вызовите [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) с параметром *Attribute* , для которого задано значение SQL_ATTR_ODBC_VERSION, а *ValuePtr* — значение SQL_OV_ODBC3.</span><span class="sxs-lookup"><span data-stu-id="a38a3-107">To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38a3-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="a38a3-108">See Also</span></span>  
 [<span data-ttu-id="a38a3-109">Взаимодействие с SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a38a3-109">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
