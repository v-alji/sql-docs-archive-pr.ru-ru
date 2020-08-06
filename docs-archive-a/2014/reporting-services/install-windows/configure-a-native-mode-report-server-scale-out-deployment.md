---
title: Настройка масштабного развертывания сервера отчетов в собственном режиме (службы SSRS Configuration Manager) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], deployments
- deploying [Reporting Services], scale-out deployment model
- scale-out deployments [Reporting Services]
ms.assetid: b30d0308-4d9b-4f85-9f83-dece4dcb2775
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6855769d36632ce60b7cf299291d58d5f136d120
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666967"
---
# <a name="configure-a-native-mode-report-server-scale-out-deployment-ssrs-configuration-manager"></a>Настройка масштабного развертывания сервера отчетов в собственном режиме (диспетчер конфигурации служб SSRS)

  Службы Reporting Services в собственном режиме поддерживают модель масштабного развертывания, которая позволяет запускать несколько экземпляров сервера отчетов, совместно использующих одну базу данных сервера отчетов. Масштабное развертывание позволяет увеличить масштабируемость сервера отчетов, чтобы обслуживать одновременно больше пользователей и повысить нагрузочную способность сервера отчетов. Масштабное развертывание также может быть использовано для выделения отдельных серверов для обработки интерактивных или запланированных отчетов.

 Серверы отчетов в режиме интеграции с SharePoint используют инфраструктуру продуктов SharePoint для горизонтального масштабирования. Горизонтальное масштабирование в режиме SharePoint выполняется путем добавления в ферму SharePoint дополнительных серверов отчетов в режиме интеграции с SharePoint. Сведения о масштабном развертывании в режиме интеграции с SharePoint см. в статье [Добавление дополнительного сервера отчетов в ферму (горизонтально масштабируемые службы SSRS)](../../reporting-services/install-windows/add-an-additional-report-server-to-a-farm-ssrs-scale-out.md).

 **Масштабное развертывание включает в себя следующие компоненты.**

-   Два или более экземпляра сервера отчетов, совместно использующие общую базу данных сервера отчетов.

-   Кроме того, может присутствовать кластер с распределенной сетевой нагрузкой (NLB), который распределяет интерактивных пользователей по экземплярам сервера отчетов.

 Во время развертывания служб Reporting Services на кластере с распределенной сетевой нагрузкой (NLB) следует убедиться, что имя виртуального сервера NLB используется в настройке URL-адресов сервера отчетов, а серверы настроены для совместного использования общего состояния представления.

 Службы Reporting Services не присутствуют в кластерах службы кластеров (Майкрософт). Однако можно создать базу данных сервера отчетов на экземпляре компонента Database Engine, который является частью отказоустойчивого кластера.

 **Чтобы произвести планирование, установку и настройку масштабного развертывания, выполните следующие шаги.**

-   Дополнительные сведения об установке экземпляров сервера отчетов см. в разделе [install SQL Server 2014 мастера установки &#40;установки&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации.

-   Если планируется выполнить масштабное развертывание на NLB-кластере, следует настроить NLB-кластер перед настройкой масштабного развертывания. Дополнительные сведения см. в статье [настроить сервер отчетов в кластере с балансированием сетевой нагрузки](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).

-   Просмотрите процедуры этого раздела с инструкциями по организации общего доступа к базе данных сервера отчетов и присоединению серверов отчетов к масштабному развертыванию.

     Эти процедуры иллюстрируют порядок настройки масштабного развертывания для сервера отчетов, состоящего из двух узлов. Чтобы добавить к развертыванию дополнительные узлы сервера отчетов, нужно будет повторить описанные в данном разделе действия.

    -   Программа установки позволяет установить все экземпляры сервера отчетов, которые будут объединены в масштабное развертывание.

         Чтобы избежать проблем совместимости баз данных при подключении экземпляров сервера к совместно используемой базе данных, следует убедиться, что все экземпляры имеют одну и ту же версию. Например, если база данных сервера отчетов создается с помощью экземпляра сервера отчетов [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , все остальные экземпляры, входящие в это развертывание, также должны иметь версию [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].

    -   Диспетчер конфигурации служб Reporting Services позволяет подключить каждый сервер отчетов к общей базе данных. Подключаться к серверам и выполнять настройку можно только единожды за один раз.

    -   Программа настройки служб Reporting Services используется для завершения масштабного развертывания посредством объединения новых экземпляров сервера отчетов с первым экземпляром сервера отчетов, уже подключенным к базе данных сервера отчетов.

### <a name="to-install-a-sql-server-instance-to-host-the-report-server-databases"></a>Установка экземпляра SQL Server для размещения баз данных сервера отчетов

1.  Установите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на компьютер, на котором будут расположены базы данных сервера отчетов. Как минимум, следует установить компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].

2.  При необходимости активируйте сервер отчетов для удаленных соединений. В некоторых версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] удаленные соединения TCP/IP и именованные каналы по умолчанию не разрешены. Чтобы проверить, разрешены ли удаленные соединения, запустите средство диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и выясните значение параметров конфигурации сети для целевого экземпляра. Если удаленный экземпляр является именованным, убедитесь в том, что на целевом сервере включена и запущена служба браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сообщает номер порта, используемый для подключения к именованному экземпляру.

### <a name="to-install-the-first-report-server-instance"></a>Установка первого экземпляра сервера отчетов

1.  Установите первый экземпляр сервера отчетов, входящий в развертывание. При установке служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]на странице параметров установки сервера отчетов выберите **Установить, но не настраивать сервер** .

2.  Запустите программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .

3.  Настройте URL-адрес веб-службы сервера отчетов, URL-адрес диспетчера отчетов и базу данных сервера отчетов. Дополнительные сведения см. в статье [Настройка сервера отчетов (службы Reporting Services в собственном режиме)](../report-server/configure-a-report-server-reporting-services-native-mode.md) в электронной документации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].

4.  Убедитесь, что сервер отчетов находится в рабочем состоянии. Дополнительные сведения см. в статье [Проверка установки служб Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md) в электронной документации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .

### <a name="to-install-and-configure-the-second-report-server-instance"></a>Установка и настройка второго экземпляра сервера отчетов

1.  Запустите программу установки, чтобы установить второй экземпляр служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] на другом компьютере или в качестве именованного экземпляра на том же компьютере. При установке служб Reporting Services на странице параметров установки сервера отчетов выберите **Установить, но не настраивать сервер** .

2.  Запустите программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и подключитесь к только что установленному экземпляру серверу отчетов.

3.  Подключите сервер отчетов к той же базе данных, что была использована для первого экземпляра сервера отчетов.

    1.  Нажмите кнопку **База данных** , чтобы открыть страницу базы данных.

    2.  Нажмите кнопку **Изменить базу данных**.

    3.  Щелкните **Выбрать существующую базу данных сервера отчетов**.

    4.  Введите имя сервера для экземпляра компонента SQL Server Database Engine, на котором расположена необходимая база данных сервера отчетов. Это должен быть тот же сервер, к которому производилось подключение в предыдущем наборе инструкций.

    5.  Нажмите кнопку **Проверить соединение**, а затем кнопку **Далее**.

    6.  В **Базе данных сервера отчетов**выберите базу данных, созданную для первого сервера отчетов, и нажмите кнопку **Далее**. По умолчанию это база данных с именем ReportServer. Не выбирайте ReportServerTempDB. Эта база данных используется только для хранения временных данных при обработке отчетов. Если список баз данных пуст, повторите предыдущие четыре шага, чтобы установить соединение с сервером.

    7.  На странице учетных данных выберите тип учетной записи и укажите учетные данные, которые сервер отчетов будет использовать для подключения к базе данных сервера отчетов. Можно использовать те же учетные данные, что и для первого экземпляра сервера отчета, или задать новые. Щелкните **Далее**.

    8.  Нажмите кнопку **Сводка** , а затем кнопку **Готово**.

4.  Настройте URL-адрес веб-службы сервера отчетов. На данном этапе не выполняйте проверку URL-адреса. URL-адрес не сработает, пока сервер отчетов не будет объединен в масштабное развертывание.

5.  Настройте URL-адрес диспетчера отчетов. На данном этапе не выполняйте проверку URL-адреса и не пытайтесь проверить развертывание. До присоединения к масштабному развертыванию сервер отчетов будет оставаться недоступным.

### <a name="to-join-the-second-report-server-instance-to-the-scale-out-deployment"></a>Включение в масштабное развертывание второго экземпляра сервера отчетов

1.  Запустите программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и повторно подключитесь к первому экземпляру сервера отчетов. Поскольку этот экземпляр уже инициализирован для операций обратимого шифрования, с его помощью к масштабному развертыванию будут присоединяться дополнительные экземпляры сервера отчетов.

2.  Выберите пункт **Масштабное развертывание** , чтобы открыть страницу "Масштабное развертывание". Здесь должны отображаться две записи: по одной для каждого экземпляра сервера отчетов, подключенного к базе данных сервера отчетов. Первый экземпляр сервера отчетов должен быть присоединен. Второй экземпляр сервера отчетов должен быть в состоянии «Ожидание соединения». Если в развертывании подобные записи не отображаются, проверьте соединение с первым сервером отчетов, который должен быть настроен и инициализирован для использования базы данных сервера отчетов.

     ![Частичный снимок экрана страницы "Масштабное развертывание"](../../../2014/sql-server/install/media/scaloutscreen.gif "Частичный снимок экрана страницы "Масштабное развертывание"")

3.  На странице Масштабное развертывание выберите экземпляр сервера отчетов, который ожидает присоединение к развертыванию, и нажмите кнопку **Добавить сервер**.

    > [!NOTE]
    >  **Вопрос.** При попытке присоединить Reporting Services экземпляр сервера отчетов к масштабному развертыванию могут возникать сообщения об ошибках, аналогичные "доступ запрещен".
    > 
    >  **Обходное решение.** Создайте резервную копию ключа шифрования [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] из первого экземпляра [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и восстановите его на второй сервер отчетов [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Затем попытайтесь включить в масштабное развертывание [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] второй экземпляр сервера отчетов.

4.  Теперь оба экземпляра сервера отчетов можно проверить, чтобы убедиться в их рабочем состоянии. Чтобы проверить второй экземпляр, можно при помощи программы настройки служб Reporting Services подключиться к серверу отчетов и щелкнуть URL-адрес веб-службы или URL-адрес диспетчера отчетов.

 Если серверы отчетов планируется запускать в кластере со сбалансированной нагрузкой, необходима дополнительная настройка. Дополнительные сведения см. в статье [настроить сервер отчетов в кластере с балансированием сетевой нагрузки](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).

## <a name="see-also"></a>См. также:
 [Настройка учетной записи службы &#40;ssrs Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) [Настройка URL-адреса &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) [Создание базы данных сервера отчетов в собственном режиме &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Настройка url-адресов сервера отчетов &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md) [Настройка подключения к базе данных сервера отчетов &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) [Добавление и удаление ключей шифрования &#40;служб SSRS](../../reporting-services/install-windows/add-and-remove-encryption-keys-for-scale-out-deployment.md) [Manage a Reporting Services Native Mode Report Server](../report-server/manage-a-reporting-services-native-mode-report-server.md) Configuration Manager

