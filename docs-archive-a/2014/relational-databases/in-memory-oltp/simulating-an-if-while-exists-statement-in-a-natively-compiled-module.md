---
title: Имитация предложения EXISTs в скомпилированной в собственном код хранимой процедуре | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0e187c1-cbd9-463c-b417-8a734574f102
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b16491b9a3729ad4df71c7ddceaee6db21777ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750952"
---
# <a name="simulating-an-exists-clause-in-a-natively-compiled-stored-procedure"></a>Имитация предложения EXISTS в скомпилированной в собственном коде хранимой процедуре
  Скомпилированные в собственном коде хранимые процедуры не поддерживают предложение `EXISTS`, однако эту проблему можно решить:  
  
```sql  
DECLARE @exists BIT = 0  
SELECT TOP 1 @exists = 1 FROM MyTable WHERE ...  
IF @exists = 1  
```  
  
## <a name="see-also"></a>См. также:  
 [Проблемы миграции, связанные с хранимыми процедурами, скомпилированными в собственном коде](migration-issues-for-natively-compiled-stored-procedures.md)   
 [Конструкции языка Transact-SQL, не поддерживаемые в выполняющейся в памяти OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
