---
title: Свойства SQL Server (вкладка «Параметры запуска») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 16942624-5374-446c-8de4-ee6ed34d6e94
author: stevestein
ms.author: sstein
ms.openlocfilehash: 66c4b71433face008ba78af93579cf175fb4bed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659047"
---
# <a name="sql-server-properties-startup-parameters-tab"></a>Свойства SQL Server (вкладка «Параметры запуска»)
  Используйте это диалоговое окно для добавления и удаления параметров запуска для компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Параметры запуска могут сильно влиять на производительность компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Прежде чем добавлять или изменять параметры запуска, ознакомьтесь с разделом «Использование параметров запуска службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] » в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="options"></a>Параметры  
 **Укажите параметр запуска**  
 Чтобы добавить параметр, введите его и нажмите кнопку **Добавить**.  
  
 Чтобы изменить один из обязательных параметров, выберите этот параметр в поле **Существующие параметры** , измените значения в поле **Укажите параметр запуска** и нажмите кнопку **Обновить**.  
  
 **Существующие параметры**  
 Чтобы удалить параметр, выберите его и нажмите кнопку **Удалить**.  
  
## <a name="parameter-format"></a>Формат параметров  
 Не вводите разделитель между параметрами. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] добавит разделитель автоматически. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] существуют следующие требования к параметрам.  
  
-   Начальные и конечные пробелы любого параметра запуска отсекаются.  
  
-   Каждый параметр запуска начинается с символа "—" (тире), вторым символом является буква.  
  
## <a name="required-parameters"></a>Необходимые параметры  
 Следующие параметры обязательны: Их можно изменять, но не удалять.  
  
-   -d представляет путь к файлу **master.mdf** (файл данных базы данных master).  
  
-   -l представляет путь к файлу **master.ldf** (файл журнала базы данных master).  
  
-   -e представляет путь к файлам журнала ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
> [!CAUTION]  
>  Если параметры пути неверны, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может не запуститься.  
  
 Подробнее о перемещении базы данных master см. в разделе «Перемещение системных баз данных» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="optional-parameters"></a>Необязательные параметры  
 Все поддерживаемые параметры запуска описаны в разделе «Использование параметров запуска службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] » электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Параметр запуска -T*trace#* показывает, что экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен запускаться с указанным флагом трассировки (*trace#* ). Флаги трассировки используются для запуска сервера в нестандартном режиме. Подробнее о флагах трассировки см. в разделе "Флаги трассировки ([!INCLUDE[tsql](../../includes/tsql-md.md)])" электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
> [!CAUTION]  
>  Описание некоторых дополнительных недокументированных параметров запуска и флагов трассировки можно найти в Интернете. Недокументированные параметры запуска и флаги трассировки создаются для решения нетиповых задач и создания определенных условий, необходимых для тестирования. Использование недокументированных параметров запуска может привести к непредвиденным результатам. Используйте недокументированные параметры только по указанию службы поддержки пользователей Майкрософт.  
  
 В следующем списке описаны самые распространенные необязательные параметры.  
  
|Параметр|Краткое описание|  
|---------------|-----------------------|  
|-M|Запускает экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в однопользовательском режиме.|  
|-T1204|Возвращает ресурсы и типы блокировки, участвующие во взаимоблокировке и текущую команду, на которую влияет взаимоблокировка.|  
|-T1224|Отключает укрупнение блокировок на основе количества блокировок.|  
|-T3608|Запрещает автоматический запуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и восстановление любых баз данных, кроме базы данных master.|  
|-T7806|Включает применение выделенных административных соединений (DAC) в [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].|  
  
> [!CAUTION]  
>  Некоторые необязательные параметры могут изменить поведение сервера и повлиять на его производительность.  
  
## <a name="permissions"></a>Разрешения  
 Доступ к этой странице имеют только пользователи, уполномоченные изменять соответствующие записи в реестре. Это следующие пользователи.  
  
-   Члены локальной группы администраторов.  
  
-   Учетная запись домена, используемая [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], если компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] настроен для работы под определенной учетной записью домена.  
  
## <a name="books-online-references"></a>Электронная документация  
 Дополнительные сведения о параметрах запуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в статье "Инструкции. Настройка параметров запуска сервера (диспетчер конфигурации[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] )" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
  