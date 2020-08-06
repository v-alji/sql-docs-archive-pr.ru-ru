---
title: Доступ к консоли конструктора CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750099"
---
# <a name="access-the-cdc-designer-console"></a>Доступ к консоли конструктора CDC
  Доступ к консоли конструктора CDC осуществляется с компьютера, где установлена консоль. Дополнительные сведения об установке см. в разделе «Установка».  
  
 При запуске консоли конструктора CDC открывается диалоговое окно «Подключение к SQL Server».  
  
 Имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с помощью которого осуществляется доступ к конструктору CDC, должно обладать разрешениями UPDATE на базу данных MSXDBCDC. Кроме того, это имя входа должно быть членом предопределенной роли сервера `dbcreator` для создания новых экземпляров Oracle CDC. Рекомендуется, чтобы имя входа также имело доступ SELECT ко всем используемым базам данных CDC, иначе пользователь не сможет видеть состояние этих баз данных.  
  
 В диалоговом окне «Подключение к SQL Server» введите следующие данные.  
  
### <a name="server-name"></a>Имя сервера  
 Введите имя сервера, на котором находится экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
### <a name="authentication"></a>Аутентификация  
 Выберите один из следующих вариантов:  
  
-   **Проверка подлинности Windows.**  
  
-   **Аутентификация SQL Server**: если вы выберете этот вариант, необходимо будет ввести **имя для входа** и **пароль** в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], к которому вы подключаетесь.  
  
 Имя входа должно иметь роль базы данных, которая обеспечивает доступ к базе данных MSXCDCDB. Рекомендуется, чтобы имя входа также имело доступ ко всем другим используемым базам данных. В противном случае пользователь не сможет просматривать данные из этих баз данных.  
  
### <a name="options"></a>Параметры  
 Чтобы просмотреть доступные для настройки параметры, щелкните стрелку. Для них можно оставить значения по умолчанию. Доступные параметры:  
  
 **Время ожидания соединения**  
 Введите время (в секундах), в течение которого служба CDC для Oracle ожидает установления соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Значение по умолчанию ― **15**.  
  
 **Время ожидания выполнения**  
 Введите время (в секундах), в течение которого служба Windows CDC Oracle ожидает выполнения команды. Значение по умолчанию — **30**.  
  
 **Шифровать соединение**  
 Выберите параметр **Шифровать соединение[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы обмен данными между Oracle CDC Service и целевым экземпляром**  выполнялся по зашифрованному соединению. **Дополнительно**. Нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".  
  
 **Дополнительно**  
 Нажмите кнопку **Дополнительно** и при необходимости введите любые дополнительные свойства подключения в диалоговом окне "Дополнительные свойства подключения".  
  
 Дополнительные сведения о диалоговом окне «Дополнительные свойства подключения» см. в разделе [Advanced Connection Properties](advanced-connection-properties.md).  
  
## <a name="see-also"></a>См. также:  
 [Разрешения, необходимые конструктору CDC для соединения с SQL Server](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  