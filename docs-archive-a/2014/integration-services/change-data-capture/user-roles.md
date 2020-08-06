---
title: Роли пользователей для Change Data Capture Service для Oracle по Attunity | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: be0ec384-e03b-4483-96ca-02b289804d6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e694da0cfd8645fe594b049b6dc2394b55d1bb55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735505"
---
# <a name="user-roles-for-change-data-capture-service-for-oracle-by-attunity"></a>Роли пользователя для изменения служб отслеживания данных для Oracle от Attunity.
  В этом разделе описываются роли пользователей для службы системы отслеживания измененных данных для Oracle компании Attunity. Описываемые роли — это роли базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , роли Windows или роли базы данных Oracle.  
  
## <a name="windows-user-roles"></a>Роли пользователей Windows  
 Ниже описываются роли пользователей Windows, которые используются службой Oracle CDC.  
  
### <a name="computer-administrator-oracle-cdc-service"></a>Администратор компьютера: служба Oracle CDC Service  
 Администратор компьютера — это пользователь Windows, который отвечает за создание и поддержание службы CDC на компьютере. Этот пользователь должен принадлежать к группе администраторов локального компьютера.  
  
 Задачи, выполняемые администратором компьютера, на котором запущены службы Oracle CDC, включают в себя следующее:  
  
-   Установка службы CDC для программного обеспечения Oracle  
  
-   Создание службы Oracle CDC для Windows  
  
-   Установка подключения службы CDC к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (строка подключения и учетные данные)  
  
-   Обеспечение защиты главного пароля службы CDC, используемого для интеллектуального анализа журнала Oracle  
  
-   Удаление службы CDC в Windows  
  
-   Удаление программного обеспечения службы CDC для Oracle  
  
-   Поддержка службы CDC для ПО Oracle (например, установка обновлений)  
  
-   Запуск и остановка службы Windows CDC  
  
 При работе с конфигурациями, обеспечивающими высокий уровень доступности, например с отказоустойчивыми кластерами Microsoft, администратор компьютера должен обладать дополнительными разрешениями, а также на него возлагаются дополнительные задачи, такие как:  
  
-   Установка и сопровождение службы CDC для программного обеспечения Oracle на всех узлах кластера.  
  
-   Определение ресурсов службы общих кластеров для службы CDC в Windows на различных узлах кластера.  
  
-   Выполнение действий администратора компьютера, прошедшего проверку подлинности в качестве администратора на компьютере, на котором установлена служба CDC для Oracle. Это лицо устанавливает службу CDC для Oracle и использует консоль конфигурации службы CDC для настройки службы CDC для Oracle на локальном компьютере.  
  
### <a name="service-account-oracle-cdc-service"></a>Учетная запись службы: служба Oracle CDC Service  
 Это учетная запись службы Windows для службы Oracle CDC, которая является учетной записью Windows, используемой для запуска службы Oracle CDC (учетная запись службы).  
  
 Единственные необходимые права для этой учетной записи службы заключаются в разрешении на использование клиента Oracle и собственного клиента Native Client источника данных ODBC для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Этой учетной записи не нужен доступ к файлам, если это не требуется для конкретных поставщиков (например, если строка подключения клиента Oracle обращается к экземплярам базы данных Oracle в файле **tnsnames.ora** , то к этому файлу необходим доступ учетной записи службы для чтения).  
  
 При создании службы Oracle CDC в среде Windows Vista или Windows Server 2008 учетной записью службы по умолчанию является NETWORK SERVICE.  
  
 В Windows 7, Windows Server 2008 R2 и более поздних версиях в качестве учетной записи службы по умолчанию используется NT Service\\<имя-службы>.  
  
 Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запущен на другом компьютере или является кластеризованным экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого необходимо подключение службы к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при использовании проверки подлинности Windows, то учетная запись службы должна быть доменной учетной записью.  
  
## <a name="sql-server-user-roles"></a>Роли пользователей SQL Server  
 Ниже описываются роли пользователей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используются службой Oracle CDC.  
  
### <a name="oracle-cdc-service-administrator"></a>Администратор службы Oracle CDC  
 Администратор службы CDC — это пользователь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , обладающий правами полного доступа к артефактам службы Oracle CDC в целевом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Администратор службы CDC использует консоль конструктора Oracle CDC для разработки экземпляров Oracle CDC.  
  
 Администратору службы CDC необходимо предоставить предопределенные роли сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**public** и **dbcreator**.  
  
 Среди задач, выполняемых администратором службы CDC, имеются следующие:  
  
-   Подготовка экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для размещения экземпляров Oracle CDC (представляющих собой базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ). Для решения этой задачи на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создается специальная база данных с именем MSXDBCDC.  
  
-   Создание базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра Oracle CDC. Задача включает использование созданной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для CDC, для чего необходима роль системного администратора [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (**sysadmin**).  
  
-   Проектирование экземпляра Oracle CDC. Эта задача включает в себя предоставление информации об исходной базе данных Oracle и отслеживаемых таблицах, а для этого необходима роль администратора базы данных Oracle.  
  
-   Поддержка экземпляра Oracle CDC в течение длительного периода, которая подразумевает добавление/удаление отслеживаемых экземпляров и обновление конфигурации.  
  
-   Включение или отключение экземпляра Oracle CDC.  
  
-   Мониторинг состояния экземпляра Oracle CDC.  
  
-   Устранение неполадок, которые влияют на экземпляр CDC Oracle.  
  
 Администратор службы CDC обладает, по крайней мере первоначально, предопределенной ролью базы данных **db_owner** в базе данных CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , связанной с экземпляром Oracle CDC. Это дает администратору службы CDC необходимый доступ к информации об изменениях, хранящихся в базе CDC. Роль **db_owner** для базы данных CDC после создания можно назначить другому пользователю, который может выполнять все указанные выше задачи, кроме подготовки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и создания другого экземпляра Oracle CDC.  
  
 Администратору службы CDC не обязательно знать главный пароль, создаваемый одновременно со службой Windows для Oracle CDC.  
  
### <a name="system-administrator"></a>Системный администратор  
 Системный администратор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] — это пользователь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которому необходимо назначить предопределенную роль сервера **sysadmin** в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , связанном со службами Oracle CDC.  
  
 Существует только одна специальная задача Oracle CDC, которая должна выполняться системным администратором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и она состоит в том, чтобы включить базу данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для взаимодействия с экземпляром Oracle CDC для CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Эта задача выполняется с помощью консоли конструктора Oracle CDC при создании нового экземпляра Oracle CDC.  
  
### <a name="oracle-cdc-service-user"></a>Пользователь службы Oracle CDC  
 Пользователь службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC — это имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемое службой Oracle CDC для выполнения задач при взаимодействии с MSXDBCDC и всеми экземплярами Oracle CDC (базами данных CDC), обрабатываемыми этой службой.  
  
 Пользователю службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC необходимо предоставить следующие права:  
  
-   Членство в предопределенных ролях **db_dlladmin**, **db_datareader**и **db_datawriter** для всех баз данных CDC, обрабатываемых этим сервером.  
  
-   Членство в предопределенных ролях баз данных **db_datareader** и **db_datawriter** для базы данных MSXDBCDC.  
  
 Поскольку служба Oracle CDC использует одно имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для работы со всеми базами данных CDC и базы данных MSXDBCDC, это имя входа необходимо назначить для всех этих баз данных.  
  
### <a name="oracle-cdc-change-consumer"></a>Потребитель изменений Oracle CDC  
 Потребитель изменений Oracle CDC Change Consumer — это пользователь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который потребляет изменения, сохраняемые в таблицах CDC в базе данных экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.  
  
 Этот пользователь определяет роль пользователя, необходимую для доступа к каждой из таблиц CDC при помощи функций CDC, создаваемых в пределах инфраструктуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC. Если роль пользователя не задана, а отслеживаемый экземпляр указан, доступ к изменениям ограничен только членами предопределенной роли базы данных **db_owner** в базе данных CDC.  
  
## <a name="oracle-user-roles"></a>Роли пользователей Oracle  
 Ниже описываются роли пользователей Oracle, которые используются службой Oracle CDC.  
  
### <a name="database-administrator-dba"></a>Администратор базы данных (DBA)  
 Администратор базы данных Oracle (DBA) — это пользователь базы данных Oracle. Среди задач, выполняемых администратором базы данных Oracle, имеются следующие:  
  
-   Настройка исходной базы данных Oracle для работы в режиме ARCHIVELOG.  
  
-   Настройка пользователя интеллектуального анализа журнала с необходимыми разрешениями.  
  
-   Установка дополнительного ведения журнала для отслеживаемых таблиц.  
  
-   Помощь в восстановлении архивированных файлов журнала транзакций, которые больше не доступны, для последующей обработки.  
  
 Администратор базы данных Oracle может извлекать скрипты Oracle SQL, которые необходимо запустить для оценки перед их запуском. Администратор базы данных Oracle может также непосредственно запускать скрипты Oracle SQL при помощи консоли конструктора Oracle CDC.  
  
 Если администратор базы данных Oracle решит использовать консоль конструктора Oracle CDC, учетные данные администратора не будут сохраняться, кроме как в контексте (диалоге), в котором они используются.  
  
 Администратор базы данных Oracle работает над конфигурацией экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC, координируя свои действия с администратором службы Oracle CDC.  
  
### <a name="log-mining-user"></a>Пользователь интеллектуального анализа журнала  
 Пользователь средства интеллектуального анализа журнала Oracle — это особый пользователь базы данных Oracle, которому предоставлены привилегии, необходимые для доступа и обработки журналов транзакций Oracle.  
  
 Учетные данные для этого пользователя сохраняются в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC с использованием асимметричного ключа шифрования. Они доступны только для службы Oracle CDC, но недоступны для владельца экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.  
  
 В следующем списке описаны необходимые привилегии пользователя функции интеллектуального анализа журнала:  
  
-   SELECT на \<any-captured-table>  
  
-   SELECT ANY TRANSACTION  
  
-   EXECUTE на DBMS_LOGMNR  
  
-   SELECT на V$LOGMNR_CONTENTS  
  
-   SELECT на V$ARCHIVED_LOG  
  
-   SELECT на V$LOG  
  
-   SELECT на V$LOGFILE  
  
-   SELECT на V$DATABASE  
  
-   SELECT на V$THREAD  
  
-   SELECT на V$PARAMETER  
  
-   SELECT на DBA_REGISTRY  
  
-   SELECT на ALL_INDEXES  
  
-   SELECT на ALL_OBJECTS  
  
-   SELECT на DBA_OBJECTS  
  
-   SELECT на ALL_TABLES  
  
 Если какие-либо из прав доступа нельзя предоставить для V$xxx, то их необходимо предоставить для V $xxx.  
  
### <a name="schema-user"></a>Пользователь схемы  
 Пользователь схемы Oracle — это пользователь Oracle, обладающий правами доступа для чтения к схемам таблиц Oracle, которые должны отслеживаться. Создание этого пользователя необходимо при работе с консолью конструктора Oracle CDC для извлечения списка схем Oracle, таблиц для отслеживания и их столбцов, индексов и ключей.  
  
 Учетные данные этого пользователя никогда не сохраняются. Их при необходимости запрашивает консоль конструктора CDC, и они хранятся до завершения сеансов пользовательского интерфейса.  
  
  