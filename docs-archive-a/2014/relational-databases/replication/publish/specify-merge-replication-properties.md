---
title: Указание свойств репликации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 11/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication [SQL Server replication], about merge replication
- merge replication [SQL Server replication]
ms.assetid: ff87c368-4c00-4e48-809d-ea752839551e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b2e66b7ed26420093166445a478bfec7f1dd21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735210"
---
# <a name="specify-merge-replication-properties"></a>Указание свойств репликации слиянием
Этот раздел описывает, как определить различные свойства для репликации слиянием. 


## <a name="download-only"></a>Только для загрузки
  В этом разделе описывается, как указать, что статья слияния таблиц доступна только для загрузки в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)] . Статьи, предназначенные только для загрузки, создаются для приложений с данными, не обновляемыми на подписчиках. Дополнительные сведения см. в статье [Оптимизация производительности репликации слиянием при работе со статьями, доступными только для загрузки](../merge/optimize-merge-replication-performance-with-download-only-articles.md).  
 
  
###  <a name="limitations-and-restrictions"></a>Ограничения  
  
-   Если указать, что статья доступна только для загрузки после инициализации подписок, потребуется провести повторную инициализацию всех клиентских подписок, получивших эту статью. В повторной инициализации серверных подписок необходимости нет. Дополнительные сведения о последствиях изменения свойств см. в статье [Изменение свойств публикации и статьи](change-publication-and-article-properties.md).  
  
### <a name="using-sql-server-management-studio"></a>Использование среды SQL Server Management Studio  
 Укажите, что статья доступна только для загрузки, на странице **статьи** мастера создания публикаций или на вкладке **Свойства** диалогового окна **Свойства статьи — \<Article> ** . Это диалоговое окно доступно в мастере создания публикаций и в диалоговом окне **Свойства публикации — \<Publication>** . Дополнительные сведения об использовании мастера и доступе к этому диалоговому окну см. в статьях [Создание публикации](../publish/create-a-publication.md) и [Просмотр и изменение свойств публикации](../publish/view-and-modify-publication-properties.md).  
  
#### <a name="to-specify-that-an-article-is-download-only-on-the-articles-page"></a>Указание на странице «Статьи», что статья доступна только для загрузки  
  
-   На странице **Статьи** мастера создания публикаций выберите таблицу, затем установите флажок **Выделенная таблица предназначена только для загрузки**. 
  
#### <a name="to-specify-that-an-article-is-download-only-on-the-properties-tab-of-the-article-properties---article-dialog-box"></a>Указание того, что статья доступна только для загрузки, на вкладке «Свойства \<Article> » диалогового окна Свойства статьи —  
  
1.  На странице **Статьи** мастера создания публикаций или в диалоговом окне **Свойства публикации — \<Publication>** выберите таблицу и щелкните **Свойства статьи**.    
2.  Щелкните **Указать свойства выделенной статьи таблицы** или **Указать свойства всех статей таблиц**.    
3.  В разделе **Целевой объект** вкладки **Свойства** диалогового окна **Свойства статьи — \<Article>** укажите одно из следующих значений для параметра **Направление синхронизации**.    
    -   **Загрузка на подписчик, запретить изменения на подписчике**    
    -   **Загрузка на подписчик, разрешить изменения на подписчике**  
  
4.  Если вы находитесь в диалоговом окне **Свойства публикации — \<Publication>** , нажмите кнопку **ОК**, чтобы сохранить результаты и закрыть диалоговое окно.    

###  <a name="using-transact-sql"></a>Использование Transact-SQL  
  
#### <a name="to-specify-that-a-new-merge-table-article-is-download-only"></a>Указание того, что новая статья таблицы публикации слиянием предназначена только для загрузки    
1.  Выполните [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql), указав значение **1** или **2** для параметра ** \@ subscriber_upload_options**. Числа соответствуют следующему поведению.  
  
    -   **0** = без ограничений (по умолчанию). Изменения, произведенные на подписчике, передаются на издатель.    
    -   **1** — изменения на подписчике разрешены, но они не передаются на издатель.    
    -   **2** — изменения на подписчике не разрешены.  
  
        > [!NOTE]  
        >  Если исходная таблица для статьи уже опубликована в другой публикации, то значение ** \@ subscriber_upload_options** должно быть одинаковым для обеих статей.  
  
#### <a name="to-modify-an-existing-merge-table-article-to-be-download-only"></a>Изменение существующей статьи публикации слиянием с целью сделать ее доступной только для загрузки  
  
1.  Чтобы определить, является ли статья доступной только для загрузки, выполните хранимую процедуру [sp_helpmergearticle](/sql/relational-databases/system-stored-procedures/sp-helpmergearticle-transact-sql). Запомните значение **upload_options** для статьи в результирующем наборе.    
2.  Если значение, возвращаемое на шаге 1, равно **0**, выполните [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), указав значение **subscriber_upload_options** для ** \@ Свойства**, значение **1** для ** \@ force_invalidate_snapshot** и ** \@ force_reinit_subscription**и значение **1** или **2** в качестве ** \@ значения**, которое соответствует следующему поведению:  
  
    -   **1** — изменения на подписчике разрешены, но они не передаются на издатель.    
    -   **2** — изменения на подписчике не разрешены.  
  
        > [!NOTE]  
        >  Если исходная таблица для статьи уже опубликована в другой публикации, доступность только для загрузки должна быть одинаковой для обеих статей.  
 
## <a name=""></a><a name="interactive-conflict-resolution">Интерактивное разрешение конфликтов</a>
[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Репликация предоставляет интерактивный сопоставитель, который позволяет разрешать конфликты вручную во время синхронизации по требованию в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Диспетчер синхронизации Windows. После того как интерактивное разрешение конфликтов включено, конфликты разрешаются во время синхронизации в интерактивном режиме с помощью интерактивного сопоставителя. Интерактивный сопоставитель доступен через диспетчер синхронизации [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows. Дополнительные сведения см. в статье [Синхронизация подписки с помощью диспетчера синхронизации Windows (диспетчер синхронизации Windows)](../synchronize-a-subscription-using-windows-synchronization-manager.md).  
  
    
###  <a name="recommendations"></a><a name="Recommendations"></a> Рекомендации  
  
-   Если синхронизация выполнена вне диспетчера синхронизации Windows (по расписанию или по требованию в среде SQL Server Management Studio или мониторе репликации), конфликты разрешаются автоматически без вмешательства пользователя с помощью метода разрешения конфликтов по умолчанию, указанному для статьи. Дополнительные сведения см. в разделе [Interactive Conflict Resolution](../merge/advanced-merge-replication-conflict-interactive-resolution.md).  
  
###  <a name="using-sql-server-management-studio"></a>Использование среды SQL Server Management Studio  
  
#### <a name="enable-interactive-conflict-resolution-for-an-article"></a>Включение интерактивного разрешения конфликтов для статьи  
  
1.  На странице **Статьи** мастера создания публикаций или в диалоговом окне **Свойства публикации — \<Publication>** выберите таблицу. Дополнительные сведения об использовании мастера и доступе к этому диалоговому окну см. в статьях [Создание публикации](create-a-publication.md) и [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).    
2.  Щелкните **Свойства статьи**, затем щелкните **Указать свойства выделенной статьи таблицы** или **Указать свойства всех статей таблиц**.    
3.  На странице **Свойства статьи — \<Article>** или **Свойства статьи — \<ArticleType>** щелкните вкладку **Сопоставитель**.    
4.  Выберите **Позволить подписчикам разрешать конфликты в интерактивном режиме во время синхронизации по требованию**.    
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]    
6.  Если вы находитесь в диалоговом окне **Свойства публикации — \<Publication>** , нажмите кнопку **ОК**, чтобы сохранить результаты и закрыть диалоговое окно.  
  
#### <a name="to-specify-that-a-subscription-should-use-interactive-conflict-resolution"></a>Указание, что подписка должна использовать интерактивное разрешение конфликтов  
  
1.  В диалоговом окне **Свойства подписки — \<Subscriber>: \<SubscriptionDatabase>** для параметра **Интерактивное разрешение конфликтов** задайте значение **True**. Дополнительные сведения о доступе к этому диалоговому окну см. в разделах [Просмотр и изменение свойств принудительной подписки](../view-and-modify-push-subscription-properties.md) и [Просмотр и изменение свойств подписки по запросу](../view-and-modify-pull-subscription-properties.md). 
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="using-transact-sql"></a>Использование Transact-SQL  
 Можно программно указать, чтобы подписчик использовал этот графический интерфейс для разрешения конфликтов статей, если создается подписка по запросу на публикацию слиянием. В интерактивном сопоставителе отображаются только конфликты статей, поддерживающих этот параметр.  
  
#### <a name="create-a-merge-pull-subscription-that-uses-the-interactive-resolver"></a>Создание подписки по запросу на публикации слиянием, использующую интерактивный сопоставитель  
  
1.  На издателе в базе данных публикации выполните [sp_helpmergearticle](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), указав ** \@ publication**. Запомните значение **allow_interactive_resolver** для каждой статьи в результирующем наборе, для которого будет использоваться интерактивный сопоставитель.    
    -   Если это значение равно **1**, будет использоваться интерактивный сопоставитель.    
    -   Если значение равно **0**, необходимо вначале включить интерактивный сопоставитель для каждой статьи. Для этого выполните [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), указав ** \@ публикацию**, ** \@ статью**, значение **allow_interactive_resolver** для ** \@ Свойства**и значение **true** в качестве ** \@ значения**.    
2.  В базе данных подписки на издателе выполните процедуру [sp_addmergepushsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-transact-sql). Дополнительные сведения см. в статье [Создание подписки по запросу](../create-a-pull-subscription.md).    
3.  На подписчике в базе данных подписки выполните хранимую процедуру [sp_addmergepullsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql), указав следующие параметры.  
  
    -   ** \@ Издатель**, ** \@ publisher_db** (опубликованная база данных) и ** \@ Публикация**.    
    -   Значение **true** для ** \@ enabled_for_syncmgr**.    
    -   Значение **true** для ** \@ use_interactive_resolver**.    
    -   Сведения учетной записи безопасности, необходимой для агента слияния. Дополнительные сведения см. в статье [Создание подписки по запросу](../create-a-pull-subscription.md).    
4.  В базе данных публикации на издателе выполните процедуру [sp_addmergepushsubscription_agent](/sql/relational-databases/system-stored-procedures/sp-addmergesubscription-transact-sql).  
  
#### <a name="define-an-article-that-supports-the-interactive-resolver"></a>Определение статьи, поддерживающей интерактивный сопоставитель  
  
В базе данных публикации на издателе выполните процедуру [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql). Укажите имя публикации, которой принадлежит статья для ** \@ публикации**, ** \@ имя статьи для статьи,** публикуемый объект базы данных для ** \@ source_object**и значение **true** для ** \@ allow_interactive_resolver**. Дополнительные сведения см. в статье [определить статью](define-an-article.md).  

## <a name="specify-the-conflict-tracking-and-resolution-level"></a>Укажите уровень отслеживания и разрешения конфликтов 
При синхронизации подписки на публикацию слиянием репликация проверяет наличие конфликтов, вызванных изменениями в одних и тех же данных, внесенных на издателе и подписчике. Можно указать, чтобы конфликты определялись на уровне строки, где любое изменение строки будет считаться конфликтом, либо на уровне столбца, где конфликтом будет считаться только изменение в одних и тех же строке и столбце. Разрешение конфликтов статей выполняется на уровне строки. Дополнительные сведения по определению и разрешению конфликтов при использовании логических записей см. в разделе [Detecting and Resolving Conflicts in Logical Records](../merge/advanced-merge-replication-conflict-resolving-in-logical-record.md).  
  

  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> Ограничения  
  
-   Если изменить уровень отслеживания после инициализации подписок, то эти подписки потребуется инициализировать повторно. Дополнительные сведения о последствиях изменения свойств см. в статье [Изменение свойств публикации и статьи](../publish/change-publication-and-article-properties.md).    
-   При отслеживании на уровне строк и столбцов устранение конфликтов всегда выполняется на уровне строк: победившая строка перезаписывает проигравшую строку. Репликация слиянием также позволяет указывать, что конфликты должны отслеживаться и разрешаться на уровне логических записей, но эти параметры недоступны из среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]. Сведения об установке данных параметров с помощью хранимых процедур репликации см. в разделе [Определение связи логических записей между статьями таблиц слияния](../publish/define-a-logical-record-relationship-between-merge-table-articles.md).  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Использование среды SQL Server Management Studio  
 Выберите отслеживание на уровне строк или столбцов для статей публикации слиянием на вкладке **Свойства** диалогового окна **Свойства статьи**, которое доступно в мастере создания публикаций и диалоговом окне **Свойства публикации — \<Publication>** . Дополнительные сведения об использовании мастера и доступе к этому диалоговому окну см. в статьях [Создание публикации](create-a-publication.md) и [Просмотр и изменение свойств публикации](../publish/view-and-modify-publication-properties.md).  
  
#### <a name="specify-row--or-column-level-tracking"></a>Указание отслеживания на уровне строк или столбцов  
  
1.  На странице **Статьи** мастера создания публикаций или в диалоговом окне **Свойства публикации — \<Publication>** выберите таблицу.    
2.  Щелкните **Свойства статьи**, затем щелкните **Указать свойства выделенной статьи таблицы** или **Указать свойства всех статей таблиц**.   
3.  На вкладке **Свойства** диалогового окна **Свойства статьи — \<Article>** выберите одно из следующих значений для свойства **Уровень отслеживания**: **Отслеживание на уровне строк** или **Отслеживание на уровне столбцов**.    
4.  Если вы находитесь в диалоговом окне **Свойства публикации — \<Publication>** , нажмите кнопку **ОК**, чтобы сохранить результаты и закрыть диалоговое окно.  
  
###  <a name="using-transact-sql"></a>Использование Transact-SQL  
  
#### <a name="specify-conflict-tracking-options-for-a-new-merge-article"></a>Указание параметров отслеживания конфликтов для новой статьи публикации слиянием  
  
1.  На издателе в базе данных публикации выполните [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) и укажите одно из следующих значений для ** \@ column_tracking**.  
  
    -   **true** — использовать для статьи отслеживание на уровне столбцов;    
    -   **false** — использовать отслеживание на уровне строк (значение по умолчанию).  
  
#### <a name="change-conflict-tracking-options-for-a-merge-article"></a>Изменение параметров отслеживания конфликтов для статьи публикации слиянием  
  
1.  Чтобы определить текущие параметры отслеживания конфликтов для статьи публикации слиянием, выполните хранимую процедуру [sp_helpmergearticle](/sql/relational-databases/system-stored-procedures/sp-helpmergearticle-transact-sql). Проверьте значение параметра **column_tracking** в результирующем наборе для статьи. Значение **1** показывает, что используется отслеживание конфликтов уровня столбца, а значение **0** — отслеживание конфликтов уровня строки.    
2.  В базе данных публикации на издателе выполните процедуру [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql). Укажите значение **column_tracking** для ** \@ Свойства** и одно из следующих значений в поле ** \@ значение**:
    -   **true** — использовать для статьи отслеживание на уровне столбцов;
    -   **false** — использовать отслеживание на уровне строк (значение по умолчанию).  
  
     Укажите значение **1** как для ** \@ force_invalidate_snapshot** , так и для ** \@ force_reinit_subscription**.  

## <a name="tracking-deletes"></a>Отслеживание удалений

> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 По умолчанию репликация слиянием производит синхронизацию команд DELETE между издателем и подписчиком. Репликация слиянием позволяет извлекать строки из базы данных подписки даже в том случае, если они были удалены из публикации (и наоборот). При создании новой статьи можно отключить выполнение команд DELETE программным путем, либо сделать это позже с помощью хранимых процедур репликации.  
  
> [!IMPORTANT]  
>  Включение этой функции приведет к потере конвергенции, то есть возникнет несоответствие данных, содержащихся на подписчике и на издателе. Потребуется реализация собственного механизма очистки удаленных строк.  
  
### <a name="specify-that-deletes-be-ignored-for-a-new-merge-article"></a>Отключение обработки команд удаления для новой статьи слияния  
  
1.  В базе данных публикации на издателе выполните процедуру [sp_addmergearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql). Укажите значение `false` для ** \@ delete_tracking**. Дополнительные сведения см. в статье [определить статью](../publish/define-an-article.md).  
  
    > [!NOTE]  
    >  Если исходная таблица для статьи уже опубликована в другой публикации, значение **delete_tracking** должно быть одинаковым для обеих статей.  
  
### <a name="specify-that-deletes-be-ignored-for-an-existing-merge-article"></a>Отключение обработки команд удаления для существующей статьи слияния  
  
1.  Чтобы определить, включена ли компенсация ошибок для статьи, выполните хранимую процедуру [sp_helpmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergearticle-transact-sql) и в полученных результатах проверьте значение параметра **delete_tracking**. Если это значение равно **0**, то команды удаления уже не обрабатываются.    
2.  Если на шаге 1 получено значение **1**, в базе данных публикации на издателе выполните процедуру [sp_changemergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql). Укажите значение **delete_tracking** для ** \@ Свойства**и значение `false` для параметра ** \@ значение**.  
  
    > [!NOTE]  
    >  Если исходная таблица для статьи уже опубликована в другой публикации, значение **delete_tracking** должно быть одинаковым для обеих статей.  
  
## <a name="processing-order"></a>Порядок обработки
  Репликация слиянием позволяет указать порядок, в котором статьи обрабатываются агентом слияния во время процесса синхронизации. Можно с помощью хранимых процедур репликации программно назначить порядок каждой статье при ее создании. Статьи обрабатываются по номерам, от меньших к большим. Если значения двух статей совпадают, то эти статьи обрабатываются одновременно. Дополнительные сведения см. в разделе [Указание свойств репликации слиянием](../publish/specify-merge-replication-properties.md).  

  Начиная с версии [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , можно переопределить порядок обработки статей по умолчанию для публикаций слиянием. Это полезно, например, при определении ссылочной целостности с помощью триггеров и при этом триггеры должны запускаться в конкретном порядке. 

### <a name="how-processing-order-is-determined"></a>Как определяется порядок обработки  
 Во время синхронизации слияния статьи по умолчанию обрабатываются в том порядке, который требуют зависимости между объектами, в том числе ограничения декларативной ссылочной целостности (DRI), определенные для базовых таблиц. Обработка включает нумерацию изменений в таблице и применение этих изменений. Если DRI отсутствуют, но для статей таблиц имеются фильтры соединения или логические записи, то статьи обрабатываются в том порядке, который требуют эти фильтры и логические записи. Статьи, не связанные с какой-либо другой статьей через DRI, фильтры соединения, логические записи и другие зависимости обрабатываются в соответствии с псевдонимами в системной таблице [sysmergearticles (Transact-SQL)](/sql/relational-databases/system-tables/sysmergearticles-transact-sql).  
  
 Рассмотрим публикацию, включающую таблицы **SalesOrderHeader** и **SalesOrderDetail** с первичным ключевым столбцом **SalesOrderID** в таблице **SalesOrderHeader** и соответствующим внешним ключевым столбцом **SalesOrderID** в таблице **SalesOrderDetail** . Во время синхронизации репликация слиянием препятствует нарушениям внешнего ключа путем вставки новых строк в столбец **SalesOrderHeader** перед тем, как вставить соответствующие строки в столбец **SalesOrderDetail**. Точно так же строки удаляются из столбца **SalesOrderDetail** перед удалением соответствующих строк из столбца **SalesOrderHeader**.  
  
 Однако в некоторых приложениях ссылочная целостность принудительно навязывается через триггеры базы данных или на уровне приложения, а не через DRI. В приведенной выше публикации таблица **SalesOrderDetail** вместо DRI могла бы иметь триггер Insert, который перед вставкой проверял бы, что в таблице **SalesOrderHeader** существует связанная строка. Таблица**SalesOrderHeader** могла бы иметь триггер Delete, который перед удалением проверял бы, что в таблице **SalesOrderDetail** отсутствует связанная строка. Репликация слиянием перед указанием порядка обработки не учитывает триггеры, потому что она перед запуском триггера не может определить, каков будет его результат. Точно так же репликация не может учитывать ограничения, определенные на уровне приложения.  
  
 Если ссылочная целостность сохраняется с помощью триггеров или на уровне приложения, необходимо задать порядок, в котором будут обрабатываться статьи. В примере с триггерами следовало бы указать, что таблица **SalesOrderHeader** должна обрабатываться раньше **SalesOrderDetail**, потому что упорядочивание статей основано на порядке вставки. Репликация слиянием автоматически меняет этот порядок на обратный для удалений. Репликация слиянием не завершится неудачей, если статьи не упорядочены, потому что, если происходит нарушение ограничения, агент слияния продолжает обрабатывать статьи. Затем, после обработки остальных статей, он пытается выполнить сбойные операции. При указании порядка статей просто исключаются повторные попытки и связанная с ними дополнительная обработка. Если указать неверный порядок (например, если он задает обработку записей с подробными данными до обработки записей заголовков), репликация слиянием будет продолжать обработку до ее успешного завершения.  

### <a name="new-article"></a>Новая статья
  
1.  В базе данных публикации на издателе выполните процедуру [sp_addmergearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql). Укажите целочисленное значение, представляющее порядок обработки статьи для ** \@ processing_order**. Дополнительные сведения см. в статье [определить статью](define-an-article.md).  
  
    > [!NOTE]  
    >  При создании упорядоченных статей необходимо оставлять промежутки между значениями порядковых номеров статей. Это облегчит задание новых значений в будущем. Например, если у вас есть три статьи, для которых необходимо указать фиксированный порядок обработки, установите значение ** \@ processing_order** равным 10, 20 и 30, а не 1, 2 и 3 соответственно.  
  
### <a name="existing-article"></a>Существующая статья
  
1.  Чтобы определить порядок обработки статьи, выполните процедуру [sp_helpmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergearticle-transact-sql) и проверьте значение **processing_order** в результирующем наборе.  
  
2.  В базе данных публикации на издателе выполните процедуру [sp_changemergearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql). Укажите значение **processing_order** для ** \@ Свойства** и целочисленное значение, представляющее порядок обработки ** \@ значения**.  



## <a name="see-also"></a>См. также:  
 [Оптимизация производительности репликации слиянием с помощью отслеживания условного удаления](../merge/optimize-merge-replication-performance-with-conditional-delete-tracking.md)  
 [Обнаружение и разрешение конфликтов в логических записях](../merge/advanced-merge-replication-conflict-resolving-in-logical-record.md)   
 [Определение связи логических записей между статьями таблиц слияния](define-a-logical-record-relationship-between-merge-table-articles.md)   
 [Обнаружение и разрешение конфликтов репликации слиянием](../merge/advanced-merge-replication-conflict-detection-and-resolution.md)   
 [Оптимизация производительности репликации слиянием при работе со статьями, доступными только для загрузки](../merge/optimize-merge-replication-performance-with-download-only-articles.md)   
 [Define an Article](define-an-article.md)   
 [View and Modify Article Properties (Просмотр и изменение свойств статьи)](view-and-modify-article-properties.md)  