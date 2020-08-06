---
title: Управление полнотекстовым поиском и наблюдение за ним для экземпляра сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], about
- full-text search [SQL Server], server management
ms.assetid: 2733ed78-6d33-4bf9-94da-60c3141b87c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1ba4b2f081047f25fa775e0c8754caa4ce643e70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733770"
---
# <a name="manage-and-monitor-full-text-search-for-a-server-instance"></a>Управление и наблюдение за полнотекстовым поиском для экземпляра сервера
  С полнотекстовым администрированием нескольких экземпляров связаны следующие задачи.  
  
-   Задачи управления системой, например управление службой средства запуска FDHOST (MSSQLFDLauncher), повторный запуск процесса узла управляющей программы фильтрации при изменении учетных данных учетной записи службы, настройка свойств полнотекстового поиска на уровне сервера и создание резервных копий полнотекстовых каталогов. На уровне сервера, к примеру, можно указать язык полнотекстового поиска по умолчанию, отличающийся от языка экземпляра сервера по умолчанию.  
  
-   Настройка полнотекстовых лингвистических компонентов (средств разбиения по словам, парадигматических модулей, файла тезауруса, стоп-слов и списков стоп-слов).  
  
-   Настройка полнотекстового поиска в пользовательской базе данных. Такая настройка включает в себя создание одного или нескольких полнотекстовых каталогов для базы данных и определение полнотекстового индекса на каждой таблице или на индексированном представлении, где требуется выполнять полнотекстовые запросы.  
  
##  <a name="viewing-or-changing-server-properties-for-full-text-search"></a><a name="props"></a> Просмотр или изменение свойств сервера для средств полнотекстового поиска  
 В среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно просматривать свойства полнотекстового поиска в экземпляре [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
#### <a name="to-view-and-change-server-properties-for-full-text-search"></a>Просмотр и изменение свойств сервера для полнотекстового поиска  
  
1.  В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.  
  
2.  В диалоговом окне **Свойства сервера** щелкните страницу **Дополнительно** , чтобы просмотреть сведения о полнотекстовом поиске на сервере. Ниже приведены свойства полнотекстового поиска.  
  
    -   **Язык полнотекстового поиска по умолчанию**  
  
         Укажите язык, используемый по умолчанию для полнотекстовых индексированных столбцов. Лингвистический анализ полнотекстовых индексированных данных зависит от языка данных. Значением по умолчанию для этого параметра является язык сервера. Дополнительные сведения о языке, соответствующем отображаемой настройке, см. в разделе [sys.fulltext_languages (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).  
  
    -   **Параметр обновления полнотекстового поиска**  
  
         Это свойство сервера управляет миграцией полнотекстовых индексов во время обновления базы данных с [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] до более поздней версии. Это свойство применяется к обновлению, выполняемому путем присоединения базы данных, восстановления базы данных из резервной копии или восстановления файла из резервной копии, а также в случае, если база данных копируется мастером копирования баз данных.  
  
         Существуют следующие варианты.  
  
         **Импорт**  
         Полнотекстовые индексы импортируются. Обычно импорт производится значительно быстрее перестроения. Например, если используется только один ЦП, то импорт выполняется в 10 раз быстрее, чем перестроение. Однако в импортированных полнотекстовых каталогах не используются новые улучшенные средства разбиения по словам, добавленные в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], поэтому со временем рекомендуется произвести перестроение полнотекстовых каталогов.  
  
        > [!NOTE]  
        >  Перестроение может выполняться в многопоточном режиме; если доступно более 10 процессоров, то перестроение может выполниться быстрее импорта, если будет разрешено использовать все процессоры.  
  
         Если полнотекстовый каталог недоступен, перестраиваются связанные полнотекстовые индексы. Этот параметр доступен только для баз данных [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .  
  
         **Перестроение**  
         Полнотекстовые каталоги перестраиваются с помощью новых и улучшенных средств разбиения по словам. Перестроение индексов может занять длительное время, а после обновления может потребоваться значительный объем ресурсов ЦП и памяти.  
  
         **Сброс**  
         Полнотекстовые каталоги сбрасываются. [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Полнотекстовые файлы каталога удалены, но метаданные для полнотекстовых каталогов и полнотекстовых индексов сохранены. После обновления для всех полнотекстовых индексов отключается отслеживание изменений и сканирование не запускается автоматически. После завершения обновления каталог останется пустым, пока не будет вручную запущено полное заполнение.  
  
         Сведения о выборе режима полнотекстового обновления см. в разделе [Обновление полнотекстового поиска](upgrade-full-text-search.md).  
  
        > [!NOTE]  
        >  Режим полнотекстового обновления также можно задать с помощью действия **upgrade_option** процедуры [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).  
  
##  <a name="viewing-additional-full-text-server-properties"></a><a name="metadata"></a> Просмотр дополнительных свойств сервера полнотекстового поиска  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)] Функции могут использоваться для получения значений различных свойств полнотекстового поиска уровня сервера. Данные сведения касаются прежде всего администрирования и устранения неполадок в полнотекстовом поиске.  
  
 В следующей таблице перечислены полнотекстовые свойства экземпляра сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и соответствующие функции [!INCLUDE[tsql](../../../includes/tsql-md.md)] .  
  
|Свойство|Description|Компонент|  
|--------------|-----------------|--------------|  
|`IsFullTextInstalled`|Указывает, установлен ли компонент Full-Text Search в текущем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|[FULLTEXTSERVICEPROPERTY](/sql/t-sql/functions/fulltextserviceproperty-transact-sql)<br /><br /> [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql)|  
|`LoadOSResources`|Указывает, зарегистрированы ли средства разбиения по словам и фильтры операционной системы и используются ли они в этом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|FULLTEXTSERVICEPROPERTY|  
|`VerifySignature`|Указывает, загружает ли средство полнотекстового поиска только подписанные двоичные файлы.|FULLTEXTSERVICEPROPERTY|  
  
##  <a name="monitoring-full-text-search-activity"></a><a name="monitor"></a>Наблюдение за операциями полнотекстового поиска  
 Для наблюдения за действиями полнотекстового поиска на экземпляре сервера могут оказаться полезными несколько функций и динамических административных представлений.  
  
 **Просмотр сведений о полнотекстовых каталогах, в которых в данный момент выполняются действия по заполнению**  
  
-   [sys.dm_fts_active_catalogs (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-active-catalogs-transact-sql)  
  
 **Просмотр текущих действий процесса в узле управляющей программы фильтрации**  
  
-   [sys.dm_fts_fdhosts (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-fdhosts-transact-sql)  
  
 **Просмотр сведений о текущих заполнениях индексов**  
  
-   [sys.dm_fts_index_population (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql)  
  
 **Просмотр буферов в пуле памяти, которые используются в процессе сканирования или диапазона сканирования.**  
  
-   [sys.dm_fts_memory_buffers (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-buffers-transact-sql)  
  
 **Просмотр пулов общей памяти, доступных сборщику полнотекстовых данных для полнотекстового сканирования или диапазона полнотекстового сканирования**  
  
-   [sys.dm_fts_memory_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-pools-transact-sql)  
  
 **Просмотр сведений о каждом пакете полнотекстового индексирования**  
  
-   [sys.dm_fts_outstanding_batches (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-outstanding-batches-transact-sql)  
  
 **Просмотр сведений о конкретных диапазонах, связанных с текущим заполнением**  
  
-   [sys.dm_fts_population_ranges (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-population-ranges-transact-sql)  
  
  