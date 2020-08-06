---
title: Развертывание базы данных с помощью приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbdeployment.settings.f1
- sql12.swb.dbdeployment.progress.f1
- sql12.swb.dbdeployment.summary.f1
- sql12.swb.dbdeployment.results.f1
- sql12.swb.dbdeployment.welcome.f1
helpviewer_keywords:
- deploy database wizard
- database deploy [SQL Server]
ms.assetid: 08c506e8-4ba0-4a19-a066-6e6a5c420539
author: stevestein
ms.author: sstein
ms.openlocfilehash: f753cfaf44e51b5bd3ffb939e38e2a300acb9703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740031"
---
# <a name="deploy-a-database-by-using-a-dac"></a>Развертывание базы данных с помощью приложения уровня данных
  С помощью мастера **развертывания базы данных в SQL Azure** разверните базу данных между экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и сервером [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] либо между двумя серверами [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].  
  
##  <a name="before-you-begin"></a><a name="BeforeBegin"></a> Перед началом  
 Мастер использует архивный файл приложения уровня данных (DAC) BACPAC для развертывания как данных, так и определений объектов базы данных. Он выполняет операцию экспорта приложения уровня данных из базы данных-источника и импорт приложения уровня данных в место назначения.  
  
###  <a name="database-options-and-settings"></a><a name="DBOptSettings"></a> Настройка параметров баз данных  
 По умолчанию база данных, созданная при развертывании, получит все параметры по умолчанию из инструкции CREATE DATABASE. Исключением являются параметры сортировки и уровень совместимости базы данных, которые устанавливаются в значения из базы данных-источника.  
  
 Некоторые параметры баз данных, например TRUSTWORTHY, DB_CHAINING и HONOR_BROKER_PRIORITY, нельзя изменить в рамках процедуры развертывания. Физические свойства, например количество файловых групп или количество и размер файлов, нельзя изменять в рамках процедуры развертывания. После завершения развертывания можно настроить базу данных с помощью инструкции ALTER DATABASE, среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]или программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> Ограничения  
 Мастер **Развертывание базы данных** поддерживает развертывание базы данных:  
  
-   C экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].  
  
-   С [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] в экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
-   Между двумя серверами [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] .  
  
 Мастер не поддерживает развертывание баз данных между двумя экземплярами компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
 Для работы с мастером на экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] должен быть запущен [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 4 (SP4) или более поздней версии. Если база данных на экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] содержит объекты, неподдерживаемые в [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], то использовать мастер развертывания базы данных на [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]нельзя. Если база данных на [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] содержит объекты, неподдерживаемые в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то использовать мастер для развертывания базы данных на экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]нельзя.  
  
###  <a name="security"></a><a name="Security"></a> безопасность  
 В целях повышения безопасности имена входа в SQL Server хранятся в файле экспорта приложения уровня данных BACPAC без пароля. При импорте файла BACPAC имя входа создается как отключенное имя входа с созданным паролем. Чтобы включить имена входа, войдите в систему под учетной записью, имеющей разрешение ALTER ANY LOGIN и с помощью команды ALTER LOGIN включите имя входа и присвойте ему новый пароль, который можно передать пользователю. Это не требуется для имен входа, использующих проверку подлинности Windows, поскольку SQL Server не управляет их паролями.  
  
#### <a name="permissions"></a>Разрешения  
 Мастеру необходимы разрешения на экспорт приложения уровня данных в базе данных-источнике. Для имени входа необходимы как минимум разрешения ALTER ANY LOGIN и VIEW DEFINITION на уровне базы данных, а также разрешение SELECT для представления каталога **sys.sql_expression_dependencies**. Экспорт приложения уровня данных может выполняться членами предопределенной роли сервера securityadmin, которые также входят в предопределенную роль базы данных database_owner для базы данных, из которой экспортируется приложение уровня данных. Экспортировать приложение уровня данных могут также члены предопределенной роли сервера sysadmin или встроенной роли системного администратора SQL Server с названием **sa** .  
  
 Мастеру необходимы разрешения на импорт приложения уровня данных на экземпляре или сервере назначения. Имя входа должно быть членом предопределенных ролей сервера **sysadmin** или **serveradmin** либо членом предопределенной роли сервера **dbcreator** с разрешениями ALTER ANY LOGIN. Импорт приложения уровня данных также может быть запущен от имени учетной записи системного администратора [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с именем **sa** . Для импорта приложения уровня данных с именами входа в [!INCLUDE[ssSDS](../../includes/sssds-md.md)] необходимо быть участником группы с ролью loginmanager или serveradmin. Для импорта приложения уровня данных без имен входа в [!INCLUDE[ssSDS](../../includes/sssds-md.md)] необходимо быть участником группы с ролью dbmanager или serveradmin.  
  
##  <a name="using-the-deploy-database-wizard"></a><a name="UsingDeployDACWizard"></a> Использование мастера развертывания баз данных  
 **Перенос базы данных с помощью мастера развертывания баз данных**  
  
1.  Подключитесь к расположению базы данных, которую необходимо развернуть. Вы можете указать либо экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , либо сервер [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] .  
  
2.  В **обозревателе объектов**разверните узел экземпляра, содержащего базу данных.  
  
3.  Разверните узел **Базы данных** .  
  
4.  Щелкните правой кнопкой мыши базу данных, которую необходимо развернуть, выберите **Задачи**, а затем **Развертывание базы данных в SQL Azure…** .  
  
5.  Выполните шаги в диалоговых окнах мастера.  
  
    -   [Вводная страница](#Introduction)  
  
    -   [Параметры развертывания](#Deployment_settings)  
  
    -   [Страница «Сводка»](#Summary)  
  
    -   [Результаты](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> Вводная страница  
 На этой странице описываются шаги мастера **развертывания баз данных** .  
  
 **Параметры**  
  
-   **Больше не показывать эту страницу.** — установите этот флажок, чтобы предотвратить отображение страницы «Введение» в будущем.  
  
-   **Далее** — осуществляет переход на страницу **Параметры развертывания** .  
  
-   **Отмена** — отмена операции и закрытие мастера.  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a>Страница "Параметры развертывания"  
 На этой странице указываются целевой сервер и подробные сведения о новой базе данных.  
  
 **Локальный узел:**  
  
-   **Подключение к серверу** — укажите сведения о подключении к серверу, а затем нажмите кнопку **Подключиться** , чтобы проверить подключение.  
  
-   **Имя новой базы данных** — укажите имя новой базы данных.  
  
 **[!INCLUDE[ssSDS](../../includes/sssds-md.md)]Параметры базы данных:**  
  
-   ** [!INCLUDE[ssSDS](../../includes/sssds-md.md)] выпуск** — выберите выпуск из раскрывающегося [!INCLUDE[ssSDS](../../includes/sssds-md.md)] меню.  
  
-   **Максимальный размер базы данных** — выберите максимальный размер базы данных в раскрывающемся меню.  
  
 **Другие параметры:**  
  
-   Укажите локальный каталог для временного файла (архивного файла BACPAC). Не забывайте, что файл будет создан в указанном месте и останется там после завершения операции.  
  
##  <a name="summary-page"></a><a name="Summary"></a> Страница «Сводка»  
 Воспользуйтесь этой страницей для просмотра указанного источника и целевых параметров операции. Чтобы выполнить развертывание с заданными параметрами, нажмите кнопку **Готово**. Чтобы отменить операцию развертывания и выйти из мастера, нажмите кнопку **Отмена**.  
  
##  <a name="progress-page"></a><a name="Progress"></a> Страница «Ход выполнения»  
 На этой странице отображается индикатор выполнения, который определяет состояние операции. Чтобы просмотреть подробности состояния, выберите параметр **Просмотр сведений** .  
  
##  <a name="results-page"></a><a name="Results"></a>Страница «результаты»  
 На этой странице отображаются сведения об успешности операции развертывания по результатам каждого действия. Для каждого действия, в котором обнаружена ошибка, предусмотрена ссылка в столбце **Результат** . Щелкните эту ссылку, чтобы просмотреть отчет об ошибках, относящихся к данному действию.  
  
 Нажмите кнопку **Готово** , чтобы закрыть мастер.  
  
## <a name="using-a-net-framework-application"></a>Использование приложения .NET Framework  
 **Развертывание базы данных с помощью методов DacStore Export() и Import() в приложении .NET Framework.**  
  
 Чтобы просмотреть пример кода, загрузите пример приложения DAC на сайте [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)  
  
1.  Создайте объект SMO и настройте его на работу с экземпляром или сервером, содержащим базу данных, подлежащую развертыванию.  
  
2.  Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.  
  
3.  Используйте метод `Export` типа `Microsoft.SqlServer.Management.Dac.DacStore` для экспорта базы данных в файл BACPAC. Укажите имя экспортируемой базы данных и путь к папке, в которой будет размещен файл BACPAC.  
  
4.  Создайте объект SMO Server и задайте для него целевой экземпляр или сервер.  
  
5.  Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.  
  
6.  Вызовите метод `Import` типа `Microsoft.SqlServer.Management.Dac.DacStore` для импорта BACPAC. Укажите файл BACPAC, созданный при экспорте.  
  
## <a name="see-also"></a>См. также:  
 [Приложения уровня данных](data-tier-applications.md)   
 [Экспорт приложения уровня данных](export-a-data-tier-application.md)   
 [Импорт файла BACPAC для создания новой пользовательской базы данных](import-a-bacpac-file-to-create-a-new-user-database.md)  
  
  