---
title: Вы выполняете обновление с версии SQL Server 2005? | Документы Майкрософт
ms.custom: ''
ms.date: 12/15/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d50a66a-1845-4116-8b3a-7b5a2eeb78e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6d1e7ab42e2e4fc41694d34a335cea3045adcb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659244"
---
# <a name="are-you-upgrading-from-sql-server-2005"></a>Вы выполняете обновление с версии SQL Server 2005?
  Окончание расширенной поддержки для SQL Server 2005 — еще одна причина выполнить обновление до более новой версии SQL Server и базы данных SQL Azure. Обновление позволяет обеспечить безопасность и соответствие требованиям, достичь высокой производительности и оптимизировать инфраструктуру платформы данных.  
  
 Дополнительные сведения, руководство и средства для планирования и автоматизации обновления или миграции см. в разделе [Прекращение поддержки SQL Server 2005](https://www.microsoft.com/sql-server/sql-server-2005).  
  
## <a name="why-upgrade"></a>Зачем выполнять обновление  
  
> [!IMPORTANT]  
>  Расширенная поддержка SQL Server 2005 заканчивается 12 апреля 2016 г. Если SQL Server 2005 будет использоваться после 12 апреля 2016 г., вы больше не будете получать обновления для системы безопасности.  
  
 Чтобы получить таблицу данных в формате PDF об обновлении с SQL Server 2005, [щелкните здесь](https://info.microsoft.com/rs/157-GQE-382/images/EN-CNTNT-Infographic-UpgradeSQL2005Datasheet.pdf) (не на эскизе ниже).  
  
 ![Лист данных об обновлении SQL Server 2005](../../../2014/sql-server/install/media/sqlserver2005eos.png "Лист данных об обновлении SQL Server 2005")  
  
## <a name="choose-your-upgrade-option"></a>Выберите вариант обновления  
 Если вы обновляете реляционные базы данных с SQL Server 2005, вы можете получить сведения о вариантах реляционного хранилища на платформе Майкрософт.  
  
 Чтобы просмотреть более подробный анализ этих вариантов, [щелкните здесь](https://sql05upgrade.azurewebsites.net/).  
  
|Вариант реляционного хранилища|Преимущества|Другие факторы, которые следует учитывать|  
|-------------------------------|--------------|-------------------------------|  
|**SQL Server на локальном компьютере**<br /><br /> Этот вариант рекомендуется для приложений баз данных любого типа: от транзакционных систем до хранилищ данных.<br /><br /> Дополнительные сведения см. в разделе [SQL Server 2014](https://www.microsoft.com/EN-US/server-cloud/products/sql-server/).|У вас есть полный контроль над возможностями и масштабируемостью, так как вы управляете и оборудованием, и программным обеспечением.<br /><br /> При обновлении с SQL Server 2005 это наиболее похожая среда.|Необходимо сделать максимальные первоначальные инвестиции и обеспечить наиболее тщательное управление, поскольку необходимо приобрести собственное оборудование и программное обеспечение, поддерживать его и управлять им.|  
|**SQL Server, размещенный на виртуальных машинах Azure**<br /><br /> Рекомендуется использовать этот вариант, если требуется следующее.<br />— Преимущества перехода на размещенную среду.<br />— Управление операционной средой.<br />-Знакомый набор функций SQL Server.<br /><br /> Дополнительные сведения см. [в статье обзор SQL Server на виртуальных машинах Azure](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-infrastructure-services/).<br /><br /> Сведения о миграции см. в разделе [Перенос базы данных в SQL Server на виртуальной машине Azure](https://azure.microsoft.com/documentation/articles/virtual-machines-migrate-onpremises-database/).|Можно быстро выполнить развертывание из библиотеки образов виртуальных машин.<br /><br /> Вы получаете полный набор функций SQL Server.<br /><br /> Можно сэкономить на стоимости оборудования и серверного программного обеспечения. Вы платите только за почасовое использование.|Необходимо настроить программное обеспечение SQL Server и операционной системы и управлять им.|  
|**Размещенная служба базы данных SQL Azure**<br /><br /> Рекомендуется использовать этот вариант, если требуется экономичное решение с меньшим объемом обслуживания.<br /><br /> Этот вариант особенно хорошо подходит для приложений, которым не требуется постоянное выделение одинаковых мощностей или для которых необходим внешний доступ.<br /><br /> Дополнительные сведения см. в разделе [база данных SQL](https://azure.microsoft.com/services/sql-database/).<br /><br /> Сведения о миграции см. в статье [Миграция базы данных SQL Server в базу данных SQL Azure](https://azure.microsoft.com/documentation/articles/sql-database-cloud-migrate/).|Можно быстро выполнить развертывание и масштабирование.<br /><br /> Вы платите только за почасовое использование.<br /><br /> Стоимость обслуживания включает не только хранилище, но и высокую доступность и автоматическое резервное копирование.|В базе данных SQL Azure отсутствуют некоторые функции SQL Server, которые не применяются в размещенной облачной среде. Дополнительные сведения см. в разделе [Сведения о Transact-SQL Базы данных SQL Azure](https://azure.microsoft.com/documentation/articles/sql-database-transact-sql-information/).<br /><br /> Кроме того, база данных SQL Azure имеет максимальный размер 500 ГБ, а SQL Server — 524 ПБ.|  
  
 Возможно, для некоторых данных и приложений следует использовать нереляционное решение или решение, отличное от SQL.  
  
|Нереляционное решение|Преимущества|  
|------------------------------|--------------|  
|**Azure DocumentDB**<br /><br /> Рекомендуется использовать этот вариант для современных, масштабируемых, мобильных и веб-приложений, использующих данные JSON и требующих сочетания надежного выполнения запросов и обработки транзакционных данных.<br /><br /> Дополнительные сведения см. в разделе [DocumentDB](https://azure.microsoft.com/services/documentdb/).|Документы индексируются, и для запросов к ним можно использовать знакомый синтаксис SQL.<br /><br /> База данных является бессхемной.<br /><br /> Можно добавлять свойства в документы без необходимости перестроения индексов.<br /><br /> Поддержка JSON и JavaScript осуществляется прямо внутри ядра СУБД.<br /><br /> Вы получаете встроенную поддержку геопространственных данных и интеграции с другими службами Azure, включая поиск Azure, HDInsight и фабрику данных.<br /><br /> Вы получаете высокопроизводительное хранилище с низкими задержками, имеющее зарезервированные уровни пропускной способности.|  
|**Хранилище таблиц Azure**<br /><br /> Рекомендуется использовать этот вариант для хранения петабайт частично структурированных данных в экономичном решении.<br /><br /> Дополнительные сведения см. в разделе [Табличное хранилище](https://azure.microsoft.com/services/storage/tables/).|Можно развивать приложения и табличную схему без перевода данных в автономный режим.<br /><br /> Можно увеличивать масштаб без сегментирования набора данных.<br /><br /> Вы получаете географически избыточное хранилище, которое реплицирует данные по нескольким регионам.|  
  
 Чтобы скачать отчет "Миграция из SQL Server 2005" от Directions on Microsoft, содержащий дополнительные сведения о вариантах обновления, [щелкните здесь](https://info.microsoft.com/CO-SQL-CNTNT-FY16-09Sep-14-ModernizationDirOnMFST-Register.html) (не эскиз ниже).  
  
 ![Отчет о миграции с SQL Server 2005](../../../2014/sql-server/install/media/sqlserver2005migratingdoc.png "Отчет о миграции с SQL Server 2005")  
  
## <a name="plan-your-upgrade"></a>Планирование обновления  
  
-   Ознакомьтесь с рядом сообщений о планировании обновления в блоге группы разработчиков SQL Server.  
  
    -   [Планирование эффективного обновления SQL Server 2005: шаг 1 из 3](https://cloudblogs.microsoft.com/sqlserver/2015/12/10/planning-an-efficient-upgrade-from-sql-server-2005-step-1-of-3/)  
  
    -   [Планирование эффективного обновления SQL Server 2005: шаг 2 из 3](https://cloudblogs.microsoft.com/sqlserver/2015/12/15/planning-an-efficient-upgrade-from-sql-server-2005-step-2-of-3/)  
  
    -   [Планирование эффективного обновления SQL Server 2005: шаг 3 из 3](https://cloudblogs.microsoft.com/sqlserver/2015/12/17/planning-an-efficient-upgrade-from-sql-server-2005-step-3-of-3/)  
  
-   Ознакомьтесь с требованиями и замечаниями в разделе [Планирование установки SQL Server](../../../2014/sql-server/install/planning-a-sql-server-installation.md), включая [требования к оборудованию и программному обеспечению для установки SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).  
  
-   Ознакомьтесь со способами обновления.  
  
    -   Просмотрите доступные методы обновления и узнайте о способах планирования и тестирования в разделе [Обновление [компонент ядра СУБД]](../../database-engine/install-windows/upgrade-database-engine.md).  
  
        > [!IMPORTANT]  
        >  Невозможно обновить SQL Server 2005 до SQL Server 2014 на месте. Необходимо установить SQL Server 2014, а затем перенести базы данных SQL Server 2005 в новую установку.  
  
    -   Чтобы получить подробное "Техническое руководство по обновлению" в формате PDF, [щелкните здесь](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf).  
  
-   Дополнительные сведения, руководство и средства для планирования и автоматизации обновления или миграции см. в разделе [Прекращение поддержки SQL Server 2005](https://www.microsoft.com/sql-server/sql-server-2005).  
  
## <a name="get-sql-server-2014"></a>Получить SQL Server 2014  
 Чтобы скачать ознакомительную копию SQL Server 2014, [щелкните здесь](https://www.microsoft.com/evalcenter/evaluate-sql-server-2014).  
  
## <a name="see-also"></a>См. также:  
 [SQL Server 2014](https://docs.microsoft.com/sql/getting-started/getting-started-sql-server-2014)   
 [SQL Server 2005. Окончание поддержки](https://www.microsoft.com/sql-server/sql-server-2005)   
 [Обновление с SQL Server 2005 до SQL Server 2016](https://msdn.microsoft.com/library/mt168847.aspx)  
  
  