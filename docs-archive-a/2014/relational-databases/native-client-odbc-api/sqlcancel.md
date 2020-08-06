---
title: SQLCancel | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658708"
---
# <a name="sqlcancel"></a>SQLCancel
  В разделе [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) говорится о том, что в ODBC 2. x, если приложение вызывает, `SQLCancel` когда в инструкции не выполняется обработка, `SQLCancel` имеет тот же результат, что `SQLFreeStmt` `SQL_CLOSE` и параметр. это поведение определено только для полноты, и приложения должны вызывать `SQLFreeStmt` или `SQLCloseCursor` закрывать курсоры. Но даже если приложение собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет версию ODBC API 3.5.x или более позднюю, функция `SQLCancel` будет использовать поведение ODBC 2.x.  
  
## <a name="see-also"></a>См. также:  
 [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516)   
 [ODBC API Implementation Details](odbc-api-implementation-details.md)  
  
  
