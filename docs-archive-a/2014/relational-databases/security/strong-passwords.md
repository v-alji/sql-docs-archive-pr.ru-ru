---
title: Надежные пароли | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730305"
---
# <a name="strong-passwords"></a>Надежные пароли
  Пароли могут быть самым слабым звеном в развертывании системы безопасности сервера. При выборе пароля всегда следует проявлять особую внимательность. Надежный пароль имеет следующие характеристики:  
  
-   содержит как минимум 8 символов;  
  
-   сочетает в себе буквы, числа и специальные символы;  
  
-   не содержится в словарях;  
  
-   не является именем команды;  
  
-   не является именем человека;  
  
-   не является именем пользователя;  
  
-   не является именем компьютера;  
  
-   регулярно меняется;  
  
-   в значительной степени отличается от предыдущих паролей.  
  
 Пароли [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут содержать до 128 символов, включая буквы, знаки и цифры. Поскольку имена входа, имена пользователей, роли и пароли часто используются в инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] , определенные символы должны заключаться в двойные кавычки (") или квадратные скобки ([ ]). Используйте разделители в инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] , если имя входа, пользователь, роль или пароль [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеют следующие характеристики:  
  
-   содержат пробел или начинаются с пробела;  
  
-   начинаются с символа $ или \@.  
  
 При использовании в строке подключения OLE DB или ODBC имя входа или пароль не должны содержать следующие символы: [] {} () , ; ? * ! \@. Эти символы используются для инициализации соединения или для указания его отдельных значений.  
  
## <a name="related-content"></a>См. также  
 [Политика паролей](password-policy.md)  
  
  
