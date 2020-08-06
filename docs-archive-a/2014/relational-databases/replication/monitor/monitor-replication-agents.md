---
title: Наблюдение за агентами репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657651"
---
# <a name="monitor-replication-agents"></a>Наблюдение за агентами репликации
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Монитор репликации [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предоставляет систематический обзор действий репликации, а также облегчает поиск сведений о конкретном агенте. В приведенном ниже списке перечислены все агенты, для которых существуют вкладки в мониторе репликации, а также дается ссылка на раздел, где описывается порядок доступа к этим вкладкам.  
  
-   С публикациями в мониторе репликации связаны следующие агенты.  
  
    -   агент моментальных снимков  
  
    -   Агент чтения журнала.  
  
    -   Агент чтения очереди.  
  
     Получить доступ к сведениям и задачам, связанным с этими агентами, можно на следующих вкладках: **Агенты** (доступна для всех издателей и публикаций) и **Предупреждения** (доступна для всех публикаций). Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).  
  
-   С подписками в мониторе репликации связаны следующие агенты:  
  
    -   Агент распространителя  
  
    -   Агент слияния.  
  
     Получить доступ к сведениям и задачам, связанным с этими агентами, можно на следующих вкладках: **Список наблюдения за подписками** (доступна для каждого издателя) или вкладка **Все подписки** (доступна для каждой публикации). Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a>Использование среды Management Studio для наблюдения за агентами репликации  
 Среда [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] предоставляет возможность наблюдения за агентами репликации с помощью следующих диалоговых окон.  
  
-   **Просмотр состояния агента моментальных снимков** (для всех публикаций).  
  
-   **Просмотр состояния агента чтения журнала** (для всех публикаций транзакций).  
  
-   **Просмотр состояния синхронизации** (для всех подписок; это диалоговое окно предоставляет доступ к агенту распространителя и агенту слияния).  
  
 Монитор репликации предоставляет дополнительные сведения о каждом агенте и предоставляет возможность наблюдения за агентом чтения очереди в случае его использования. Дополнительные сведения см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](view-information-and-perform-tasks-replication-monitor.md).  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a>Наблюдение за агентом моментальных снимков и агентом чтения журналов  
  
1.  Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.  
  
2.  Раскройте папку **Репликация** , а затем папку **Локальные публикации** .  
  
3.  Щелкните публикацию правой кнопкой мыши, затем щелкните **Просмотреть состояние агента чтения журнала** или **Просмотреть состояние агента моментальных снимков**.  
  
4.  В диалоговом окне **Просмотр состояния агента чтения журнала** или **Просмотр состояния агента моментальных снимков** выполните следующие действия.  
  
    -   Просмотрите состояние агента.  
  
    -   Запустите или остановите агент при необходимости.  
  
    -   Щелкните **Отслеживать** , чтобы запустить **Монитор репликации**.  
  
5.  Щелкните **Закрыть**.  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a>Наблюдение за агентом распространителя и агентом слияния (с издателя)  
  
1.  Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.  
  
2.  Раскройте папку **Репликация** , а затем папку **Локальные публикации** .  
  
3.  Раскройте публикацию, связанную с подпиской, которую требуется проконтролировать.  
  
4.  Щелкните правой кнопкой мыши подписку, затем выберите **Просмотреть состояние синхронизации**.  
  
5.  В диалоговом окне **Просмотр состояния синхронизации** выполните следующие действия:  
  
    -   Просмотрите состояние агента.  
  
    -   Запустите или остановите агент при необходимости.  
  
    -   Для принудительных подписок щелкните **Отслеживать** , чтобы запустить **Монитор репликации**.  
  
    -   Для подписок по запросу щелкните **Просмотреть журнал заданий** , чтобы запустить **Средство просмотра файла журнала**, отображающего записи журнала агента.  
  
6.  Щелкните **Закрыть**.  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a>Наблюдение за агентом распространителя и агентом слияния (с подписчика)  
  
1.  Подключитесь к подписчику в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и раскройте узел сервера.  
  
2.  Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .  
  
3.  Щелкните подписку правой кнопкой мыши, и щелкните **Просмотреть состояние синхронизации**.  
  
4.  В диалоговом окне **Просмотр состояния синхронизации** выполните следующие действия:  
  
    -   Просмотрите состояние агента.  
  
    -   Запустите или остановите агент при необходимости.  
  
    -   Щелкните **Просмотреть журнал заданий** , чтобы запустить **Средство просмотра файла журнала**, отображающего записи журнала агента.  
  
5.  Щелкните **Закрыть**.  
  
## <a name="see-also"></a>См. также:  
 [Наблюдение за репликацией](../monitoring-replication.md)   
 [Replication Agents Overview](../agents/replication-agents-overview.md)  
  
  