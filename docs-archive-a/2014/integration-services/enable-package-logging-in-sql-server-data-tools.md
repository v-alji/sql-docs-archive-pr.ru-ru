---
title: Включение ведения журнала пакетов в SQL Server Data Tools | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665032"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a>Включение средств ведения журналов в SQL Server Data Tools
  В этой процедуре описывается, как добавлять журналы в пакет, настраивать ведение журналов на уровне пакетов и сохранять настройку ведения журналов в XML-файле. Журнал можно добавить только на уровне пакета, однако пакеты не обязаны осуществлять ведение журналов, чтобы включить ведение журналов в контейнерах, которые содержатся в этих пакетах.  
  
> [!IMPORTANT]  
>  При развертывании проекта [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] уровень ведения журнала, заданный для выполнения пакета, переопределяет уровень, настраиваемый с помощью среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
 По умолчанию к контейнерам в пакете применяются те же самые настройки ведения журналов, что и к их родительскому контейнеру. Дополнительные сведения об установке параметров ведения журналов для отдельных контейнеров см. в разделе [Настройка ведения журналов с помощью сохраненного файла конфигурации](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).  
  
### <a name="to-enable-logging-in-a-package"></a>Включение ведения журналов в пакете  
  
1.  В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.  
  
2.  В меню **Службы SSIS** нажмите **Ведение журнала**.  
  
3.  Выберите регистратор из списка **Тип поставщика** и щелкните **Добавить**.  
  
4.  В столбце **Конфигурация** выберите диспетчер подключений или щелкните **\<New connection>** , чтобы создать диспетчер подключений, соответствующий регистратору. В зависимости от выбранного регистратора может использоваться один из следующих диспетчеров соединений.  
  
    -   Для текстовых файлов используется диспетчер подключения файлов. Дополнительные сведения см. в разделе [диспетчер подключения файлов](connection-manager/file-connection-manager.md).  
  
    -   Для [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]используется диспетчер подключения файлов.  
  
    -   Для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]используется диспетчер соединений OLE DB. Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](connection-manager/ole-db-connection-manager.md).  
  
    -   В журнале событий Windows выполнение действий не требуется. [!INCLUDE[ssIS](../includes/ssis-md.md)] автоматически создадут журнал.  
  
    -   Для XML-файлов используется диспетчер подключения файлов.  
  
5.  Для каждого журнала, используемого в пакете, повторите шаги 3 и 4.  
  
    > [!NOTE]  
    >  Пакет может задействовать более одного журнала каждого типа.  
  
6.  При необходимости установите флажок уровня пакетов, выберите журналы для ведения на уровне пакетов и перейдите на вкладку **Подробности** .  
  
7.  На вкладке **Подробности** установите флажок **События** для сохранения всех записей журнала или снимите флажок **События** , чтобы выбрать отдельные события.  
  
8.  При необходимости перейдите на вкладку **Дополнительно** , чтобы указать, какие именно данные следует вносить в журнал.  
  
    > [!NOTE]  
    >  По умолчанию в журнал вносятся все данные.  
  
9. На вкладке **Подробности** нажмите кнопку **Сохранить**. Отображается диалоговое окно **Сохранить как** . Выберите папку для хранения настроек ведения журнала, введите имя файла для конфигурации нового журнала и щелкните **Сохранить**.  
  
10. Нажмите кнопку **ОК**.  
  
11. Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .  
  
## <a name="see-also"></a>См. также:  
 [Ведение журнала&#41; Integration Services &#40;SSIS](performance/integration-services-ssis-logging.md)   
 [Ведение журналов в службах Integration Services (SSIS)](performance/integration-services-ssis-logging.md)  
  
  