---
title: Экспорт приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667206"
---
# <a name="export-a-data-tier-application"></a>Экспорт приложения уровня данных
  При экспорте развернутого приложения уровня данных (DAC) или базы данных создается файл экспорта, содержащий определения объектов в базе данных и все данные, содержащиеся в таблицах. Файл экспорта затем можно импортировать в другой экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]или в [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]. Операции экспорта-импорта могут быть совмещены для переноса приложения уровня данных с одного экземпляра на другой, а также для создания логической резервной копии или создания находящейся на предприятии копии базы данных, развернутой в службах [!INCLUDE[ssSDS](../../includes/sssds-md.md)].  
  
## <a name="before-you-begin"></a>Перед началом  
 Процедура экспорта создает файл приложения уровня данных в два этапа.  
  
1.  При экспорте создается определение приложения уровня данных в файле экспорта (BACPAC) аналогично тому, как извлечение приложения уровня данных создает определение приложения уровня данных в файле пакета приложения уровня данных. Экспортируемое определение приложения уровня данных включает все объекты в текущей базе данных. Если процесс экспорта выполняется в базе данных, которая была первоначально развернута из приложения уровня данных, а все изменения были внесены непосредственно в базу данных после развертывания, то экспортируемое определение соответствует заданному в базе данных объекту, а не объекту, определенному в исходном приложении уровня данных.  
  
2.  При экспорте выполняется массовое копирование данных из всех таблиц в базе данных; эти данные включаются в файл экспорта.  
  
 В процессе экспорта устанавливается версия приложения уровня данных 1.0.0.0, а описание приложения уровня данных в файле экспорта устанавливается в пустую строку. Если база данных была развернута из приложения уровня данных, то определение приложения уровня данных в файле экспорта содержит имя, заданное для исходного приложения уровня данных; в противном случае имя приложения уровня данных устанавливается равным имени базы данных.  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> Ограничения  
 Приложение уровня данных или база данных могут экспортироваться только из базы данных в [!INCLUDE[ssSDS](../../includes/sssds-md.md)]или [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 4 (SP4) и выше.  
  
 Если база данных содержит объекты, не поддерживаемые в приложениях уровня данных, или автономных пользователей, то экспортировать такую базу данных будет невозможно. Дополнительные сведения о типах объектов, поддерживаемых в DAC, см. в разделе [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).  
  
###  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 Для экспорта приложения уровня данных необходимы по крайней мере разрешения ALTER ANY LOGIN и VIEW DEFINITION на уровне базы данных, а также разрешение SELECT на представление каталога **sys.sql_expression_dependencies**. Экспорт приложения уровня данных может выполняться членами предопределенной роли сервера securityadmin, которые также входят в предопределенную роль базы данных database_owner для базы данных, из которой экспортируется приложение уровня данных. Экспортировать приложение уровня данных могут также члены предопределенной роли сервера sysadmin или встроенной роли системного администратора SQL Server с названием **sa** .  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a>Использование мастера экспорта приложения уровня данных  
 **Экспорт приложения уровня данных с помощью мастера**  
  
1.  Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]на предприятии или в службах [!INCLUDE[ssSDS](../../includes/sssds-md.md)].  
  
2.  В **обозревателе объектов**раскройте узел экземпляра, из которого будет производиться экспорт приложения уровня данных.  
  
3.  Щелкните правой кнопкой мыши имя базы данных.  
  
4.  Щелкните **задачи** и выберите **Экспорт приложения уровня данных...**  
  
5.  Выполните шаги в диалоговых окнах мастера.  
  
    -   [Вводная страница](#Introduction)  
  
    -   [Страница «Параметры экспорта»](#Export_settings)  
  
    -   [Страница «Проверка»](#Validation)  
  
    -   [Страница «Сводка»](#Summary)  
  
    -   [Страница "выполнение"](#Progress)  
  
    -   [Страница «Результаты»](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> Вводная страница  
 На этой странице описаны шаги мастера экспорта приложения уровня данных.  
  
 **Параметры**  
  
 **Больше не показывать эту страницу.** — установите этот флажок, чтобы предотвратить отображение страницы «Введение» в будущем.  
  
 **Далее &gt;** — переход на страницу **Выбор пакета приложения уровня данных** .  
  
 **Отмена** — отмена операции и закрытие мастера.  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a>Страница параметров экспорта  
 Используйте эту страницу, чтобы указать место, где нужно создать BACPAC-файл.  
  
-   **Сохранить на локальный диск** — создает BACPAC-файл в каталоге на локальном компьютере. Нажмите кнопку **Обзор…** для навигации по локальному компьютеру или укажите путь в соответствующем поле. Имя пути должно включать имя файла и расширение BACPAC.  
  
-   **Сохранить в Azure** — создает BACPAC-файл в контейнере Azure. Чтобы проверить этот параметр, необходимо подключиться к контейнеру Azure. Обратите внимание, что для этого параметра также необходимо указать локальный каталог для временного файла. Примите к сведению, что временный файл будет создан в указанном месте и останется там после завершения операции.  
  
 Чтобы задать подмножество таблиц для экспорта, используйте параметр **Дополнительно** .  
  
##  <a name="validation-page"></a><a name="Validation"></a>Страница проверки  
 Используйте страницу «Проверка» для поиска любых проблем, блокирующих операцию. Для продолжения устраните критические препятствия, приводящие к блокированию, и нажмите кнопку **Повторная проверка** для обеспечения успешного завершения проверки.  
  
 Чтобы продолжить, нажмите кнопку **Далее**.  
  
##  <a name="summary-page"></a><a name="Summary"></a> Страница «Сводка»  
 Воспользуйтесь этой страницей для просмотра указанного источника и целевых параметров операции. Для завершения экспорта с использованием заданных параметров нажмите кнопку **Готово**. Чтобы отменить операцию экспорта и выйти из мастера, нажмите кнопку **Отмена**.  
  
##  <a name="progress-page"></a><a name="Progress"></a> Страница «Ход выполнения»  
 На этой странице отображается индикатор выполнения, который определяет состояние операции. Чтобы просмотреть подробности состояния, выберите параметр **Просмотр сведений** .  
  
##  <a name="results-page"></a><a name="Results"></a>Страница «результаты»  
 На этой странице отображаются сведения об успешности завершения экспорта по результатам каждого действия. Для каждого действия, в котором обнаружена ошибка, предусмотрена ссылка в столбце **Результат** . Щелкните эту ссылку, чтобы просмотреть отчет об ошибках, относящихся к данному действию.  
  
 Нажмите кнопку **Готово** , чтобы закрыть мастер.  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a>Использование приложения .NET Framework  
 **Экспорт приложения уровня данных с использованием метода Export () в приложении .NET Framework.**  
  
 Чтобы просмотреть пример кода, загрузите пример приложения DAC на сайте [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)  
  
1.  Создайте объект SMO Server и установите его в экземпляр, содержащий экспортируемое приложение уровня данных.  
  
2.  Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.  
  
3.  Используйте метод `Export` типа `Microsoft.SqlServer.Management.Dac.DacStore` для экспорта приложения уровня данных. Укажите имя экспортируемого приложения уровня данных и путь к папке, в которой будет размещен файл экспорта.  
  
## <a name="see-also"></a>См. также:  
 [Приложения уровня данных](data-tier-applications.md)   
 [Извлечение DAC из базы данных](extract-a-dac-from-a-database.md)  
  
  