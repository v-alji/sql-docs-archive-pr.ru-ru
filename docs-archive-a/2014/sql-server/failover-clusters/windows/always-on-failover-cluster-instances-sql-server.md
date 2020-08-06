---
title: Экземпляры отказоустойчивого кластера AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clustering [SQL Server]
- high availability [SQL Server], failover clustering
- virtual servers [SQL Server], about virtual servers
- clusters [SQL Server]
- servers [SQL Server], failover clustering
- resource groups [SQL Server]
- availability [SQL Server]
- failover clustering [SQL Server]
- AlwaysOn [SQL Server], see failover clustering [SQL Server]
ms.assetid: 86a15b33-4d03-4549-8ea2-b45e4f1baad7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6adc173560fd83d00616eb00c63651ef667c2a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659289"
---
# <a name="always-on-failover-cluster-instances-sql-server"></a>Экземпляры отказоустойчивого кластера AlwaysOn (SQL Server)
  В рамках [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предложения Always On Always on экземпляры отказоустойчивого кластера используют функции отказоустойчивой кластеризации Windows Server (WSFC), чтобы обеспечить локальную высокую доступность с помощью избыточности на уровне экземпляра сервера — *экземпляра отказоустойчивого кластера* (FCI). Экземпляр отказоустойчивого кластера (FCI) является единственным экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , установленным на всех узлах отказоустойчивой кластеризации Windows Server (WSFC) и, возможно, в нескольких подсетях. Экземпляр отказоустойчивого кластера выглядит в сети как экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , запущенный на одном компьютере, но экземпляр отказоустойчивого кластера обеспечивает отработку отказа с переходом одного узла WSFC на другой узел, если текущий узел становится недоступным.  
  
 Экземпляр отказоустойчивого кластера (FCI) может эффективно использовать [Группы доступности AlwaysOn](../../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md) для выполнения удаленного аварийного восстановления на уровне базы данных. Дополнительные сведения см. в разделе [Отказоустойчивая кластеризация и группы доступности AlwaysOn (SQL Server)](../../../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md).  
  
> [!NOTE]  
>  Начиная с версии [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)], экземпляры отказоустойчивого кластера AlwaysOn поддерживают кластерные общие тома (CSV) как в [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)], так и в [!INCLUDE[win8srv](../../../includes/win8srv-md.md)]. Дополнительные сведения о CSV-файле см. в разделе [Основные сведения о кластерных общих томах в отказоустойчивом кластере](https://technet.microsoft.com/library/dd759255.aspx).  
  
 **В этом разделе.**  
  
-   [Преимущества](#Benefits)  
  
-   [Рекомендации](#Recommendations)  
  
-   [Общие сведения об экземпляре отказоустойчивого кластера](#Overview)  
  
-   [Элементы экземпляра отказоустойчивого кластера](#FCIelements)  
  
-   [SQL Server концепции и задачи отработки отказа](#ConceptsAndTasks)  
  
-   [Связанные разделы](#RelatedTopics)  
  
##  <a name="benefits-of-a-failover-cluster-instance"></a><a name="Benefits"></a> Преимущества экземпляра отказоустойчивого кластера  
 При сбое оборудования или программного обеспечения сервера приложения или клиенты, связывающиеся с сервером, будут простаивать. Если экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] настроен как отказоустойчивый кластер (а не как независимый экземпляр), высокий уровень доступности такого экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] защищен наличием избыточных узлов в отказоустойчивом кластере. Только один из узлов в FCI принадлежит группе ресурсов WSFC одновременно. В случае сбоя (отказа оборудования, сбоя операционной системы, приложений или служб) либо при выполнении запланированного обновления группа передается во владение другому узлу отказоустойчивого кластера. Данный процесс не заметен для клиента или приложения, соединяющегося с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , и сводит к минимуму время ожидания приложения или клиента во время сбоя. Ниже перечислены некоторые ключевые преимущества, которые обеспечивают экземпляры отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :  
  
-   Защита на уровне экземпляра через избыточность  
  
-   Автоматический переход на другой ресурс в случае сбоя (отказа оборудования, сбоя операционной системы, приложений или служб)  
  
    > [!IMPORTANT]  
    >  В группе доступности AlwaysOn не поддерживается автоматический переход на другие узлы в пределах доступности группы от FCI. Это означает, что отказоустойчивые кластеры и независимые узлы не следует объединять внутри одной группы доступности, если автоматический переход на другой ресурс является важным компонентом решения высокого уровня доступности. Однако такое объединение можно сделать для решения *аварийного восстановления* .  
  
-   Поддержка широкого массива решения хранения, включая диски кластеров WSFC (iSCSI, Fiber Channel и т. д.) и общие папки протокола SMB.  
  
-   Решение для аварийного восстановления с помощью FCI с несколькими подсетями или запуска базы данных, размещенной в FCI, внутри группы доступности AlwaysOn. Благодаря новой поддержке большого числа подсетей в среде [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]кластеру FCI с большим количеством подсетей больше не нужна виртуальная локальная сеть, что повышает управляемость и безопасность кластера FCI с большим числом подсетей.  
  
-   Нулевая реконфигурация приложений и клиентов при сбое  
  
-   Гибкая политика отработки отказа для гранулированных событий триггера для автоматической отработки отказа  
  
-   Надежная отработка отказа посредством периодического подробного отслеживания исправности системы с помощью выделенных и постоянных соединений  
  
-   Возможность настройки и предсказуемость во время отработки отказа посредством косвенных контрольных точек  
  
-   Использование регулируемых ресурсов при отработке отказа  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> Рекомендации  
 В рабочей среде рекомендуется использовать статические IP-адреса в сочетании с виртуальным IP-адресом экземпляра отказоустойчивого кластера.  Не рекомендуется использовать протокол DHCP в рабочей среде. В случае простоя, если время действия IP-адреса протокола DHCP истекло, на регистрацию нового сетевого IP-адреса протокола DHCP, связанного с DNS-именем, уйдет дополнительное время.  
  
##  <a name="failover-cluster-instance-overview"></a><a name="Overview"></a>Общие сведения об экземпляре отказоустойчивого кластера  
 FCI работает в группе ресурсов WSFC вместе с одним или несколькими узлами WSFC. Когда экземпляр FCI запускается, один из узлов принимает владение группой ресурсов и выводит свой экземпляр служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в сеть. Ресурсы, принадлежащие данному узлу включают в себя:  
  
-   Сетевое имя  
  
-   IP-адрес  
  
-   Общие диски  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Служба компонента Database Engine  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Служба агента  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Analysis Services, если эти служб установлены  
  
-   Один файловый ресурс общего доступа, если установлен компонент FILESTREAM  
  
 В любое время только владелец группы ресурсов (и никакой другой узел в FCI) запускает соответствующие службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в группе ресурсов. Когда происходит переход на другой ресурс, будь то автоматический или запланированный переход на другой ресурс, происходит следующая последовательность событий.  
  
1.  Если событие не является сбоем оборудования или системы, все «грязные» страницы в буферном кэше записываются на диск.  
  
2.  Все соответствующие службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в группе ресурсов останавливаются на активном узле.  
  
3.  Права владения группой ресурсов переносятся на другой узел в FCI.  
  
4.  Новый владелец группы ресурсов запускает свои службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
5.  Клиентские запросы на подключение приложения автоматически перенаправляются на новый активный узел, используя то же имя виртуальной сети (VNN).  
  
 FCI находится в сети, если его базовый кластер WSFC находится в исправном состоянии (большая часть узлов кворума WSFC доступны в качестве целей автоматического перехода на другой ресурс). Когда кластер WSFC теряет кворум из-за сбоя аппаратной части, программного обеспечения, сети или неверной настройки кворума, весь кластер WSFC вместе с FCI выводится из сети. Для этого незапланированного сценария отработки отказа требуется вмешательство пользователя, который должен переустановить кворум для оставшихся доступных узлов, чтобы вернуть кластер WSFC и FCI обратно в сеть. Дополнительные сведения см. в разделе [режимы кворума WSFC и конфигурация голосования (; SQL Server);](wsfc-quorum-modes-and-voting-configuration-sql-server.md).  
  
### <a name="predictable-failover-time"></a>Прогнозируемое время отработки отказа  
 В зависимости от того, когда экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в последний раз выполнил операцию контрольной точки, в кэше буфера может быть достаточное число «грязных» страниц. Последующая отработка отказа длится столько, сколько потребуется времени для записи оставшихся «грязных» страниц на диск, что может увеличить время отработки отказа непредсказуемым образом. Начиная с [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]FCI может использовать косвенные контрольные точки для регулирования числа "грязных" страниц, хранимых в кэше буфера. Несмотря на то что это занимает дополнительные ресурсы при нормальной рабочей нагрузке, время отработки отказа становится более прогнозируемым и регулируемым. Это очень полезно, когда в соглашении об уровне обслуживания в организации указана цель времени восстановления (RTO) для решения высокого уровня доступности. Дополнительные сведения о косвенных контрольных точках см. в разделе [Indirect Checkpoints](../../../relational-databases/logs/database-checkpoints-sql-server.md#IndirectChkpt).  
  
### <a name="reliable-health-monitoring-and-flexible-failover-policy"></a>Надежный мониторинг исправности и гибкая политика отработки отказа  
 После успешного запуска FCI служба WSFC мониторит состояние базового кластера WSFC, а также состояние экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Начиная с [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]служба WSFC использует выделенную линию для обращения к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и получения подробной диагностики компонентов посредством системной хранимой процедуры. Это имеет три последствия.  
  
-   Выделенное соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] позволяет получать надежную диагностику компонентов в любое время, даже когда FCI испытывает перегрузку. В результате можно выделить систему, испытывающую большую нагрузку, и систему, которая находится на грани отработки отказа, позволяя избежать проблем, связанных с ложной отработкой отказа.  
  
-   Подробная диагностика компонентов позволяет настроить более гибкую политику отработки отказа, с помощью которой вы можете выбрать, какие условия отказа запускают отработку отказа, а какие нет.  
  
-   Подробная диагностика компонентов также позволяет лучше устранять ошибки автоматической отработки отказа. Сведения диагностики сохраняются в файлы журналов, связанные с журналами ошибок [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Файлы можно загрузить в средство просмотра файлов журнала для изучения состояний компонентов, которые привели к отработке отказа, чтобы определить причину сбоя.  
  
 Дополнительные сведения см. в разделе [политика отработки отказа для экземпляров отказоустойчивого кластера](failover-policy-for-failover-cluster-instances.md) .  
  
##  <a name="elements-of-a-failover-cluster-instance"></a><a name="FCIelements"></a>Элементы экземпляра отказоустойчивого кластера  
 FCI включает набор физических серверов (узлов), которые имеют схожую аппаратную и программную конфигурацию, в том числе версию операционной системы и уровень обновления, версию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , ее уровень обновления, компоненты и имя экземпляра. Идентичная программная конфигурация необходима для того, чтобы FCI смог работать после отработки отказа между двумя узлами.  
  
 Группа ресурсов WSFC  
 FCI [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] работает в группе ресурсов WSFC. Каждый узел в группе ресурсов поддерживает синхронизированную копию параметров конфигурации и разделов реестра для того, чтобы сохранить полную функциональность FCI после отработки отказа, при этом только один узел в кластере владеет группой ресурсов одновременно (активный узел). Служба WSFC управляет кластером сервера, конфигурацией кворума, политикой и операциями отработки отказа, а также именем виртуальной сети и виртуальными IP-адресами для FCI. В случае сбоя (аппаратной части, операционной системы, приложения или службы) или запланированного обновления права владения группой ресурсов перемещаются на другой узел в FCI. Число узлов, поддерживаемых в группе ресурсов WSFC, зависит от выпуска [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Также один кластер WSFC может запускать несколько FCI (множественные группы ресурсов), в зависимости от возможностей оборудования, например ЦП, памяти и числа дисков.  
  
 Двоичные файлы SQL Server  
 Двоичные файлы устанавливаются локально на каждом узле FCI, так же как и в случае изолированной установки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Однако во время запуска службы не запускаются автоматически, а управляются службой WSFC.  
  
 Память  
 В отличие от группы доступности AlwaysOn, FCI должен использовать общее хранилище для всех узлов FCI для базы данных и хранения журналов. Общее хранилище может быть в форме кластерных дисков WSFC, дисков на SAN или общих папок SMB. Таким образом, все узлы в FCI имеют одинаковое представление данных экземпляра всегда, когда происходит отработка отказа. Однако в этом случае общее хранилище может стать единственной точкой сбоя, в то время как FCI зависит от базового решения хранилища для обеспечения защиты данных.  
  
 Сетевое имя  
 VNN для FCI предоставляет единую точку соединения для FCI. Это позволяет приложениям подключаться к VNN без необходимости знать текущий активный узел. Когда происходит отработка отказа, VNN регистрируется на новом активном узле после его запуска. Данный процесс не заметен для клиента или приложения, соединяющегося с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , и сводит к минимуму время ожидания приложения или клиента во время сбоя.  
  
 Виртуальные IP-адреса  
 В случае многоподсетевого кластера FCI виртуальный IP-адрес присваивается каждой подсети FCI. В ходе отработки отказа VNN-имя DNS-сервера обновляется и указывает на виртуальный IP-адрес соответствующей подсети. Приложения и клиенты могут подключиться к FCI, используя то же самое имя VNN после многоподсетевой отработки отказа.  
  
##  <a name="sql-server-failover-concepts-and-tasks"></a><a name="ConceptsAndTasks"></a> Основные понятия и задачи отработки отказа SQL Server  
  
|Основные понятия и задачи|Раздел|  
|------------------------|-----------|  
|Описывает механизм обнаружения сбоя и гибкую политику отработки отказа.|[Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md)|  
|Описание основных понятий в управлении и обслуживании экземпляров отказоустойчивых кластеров.|[Администрирование и обслуживание экземпляров отказоустойчивого кластера](failover-cluster-instance-administration-and-maintenance.md)|  
|Описание и понятия конфигурации с несколькими подсетями|[SQL Server кластеризации с несколькими подсетями (; SQL Server);](sql-server-multi-subnet-clustering-sql-server.md)|  
  
##  <a name="related-topics"></a><a name="RelatedTopics"></a>См. также  
  
|**Описание раздела**|**Раздел**|  
|----------------------------|---------------|  
|Описывает, как установить новый FCI [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .|[Создание нового SQL Server отказоустойчивого кластера (; Настройка);](../install/create-a-new-sql-server-failover-cluster-setup.md)|  
|Описывает, как выполнить обновление до отказоустойчивого кластера [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] .|[Обновление отказоустойчивого кластера SQL Server](upgrade-a-sql-server-failover-cluster-instance.md)|  
|Описание основных понятий отказоустойчивых кластеров Windows, а также ссылки на связанные с ними задачи.|[!INCLUDE[nextref_longhorn](../../../includes/nextref-longhorn-md.md)]: [обзор отказоустойчивых кластеров](https://go.microsoft.com/fwlink/?LinkId=177878)<br /><br /> [!INCLUDE[nextref_longhorn](../../../includes/nextref-longhorn-md.md)] R2: [обзор отказоустойчивых кластеров](https://go.microsoft.com/fwlink/?LinkId=177879)|  
|Описывает различия в основных понятиях между узлами в экземпляре отказоустойчивого кластера и репликами внутри группы доступности, а также содержит рекомендации по использованию экземпляра отказоустойчивого кластера для размещения реплики для группы доступности.|[Отказоустойчивая кластеризация и группы доступности AlwaysOn (SQL Server)](../../../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md)|  
  
  