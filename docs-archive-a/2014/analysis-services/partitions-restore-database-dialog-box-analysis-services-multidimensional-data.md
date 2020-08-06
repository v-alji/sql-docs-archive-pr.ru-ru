---
title: Секции (диалоговое окно «Восстановление базы данных») (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.partitions.f1
ms.assetid: 1ad4dde5-4651-4069-875c-7ab73cd8b4f4
author: minewiskan
ms.author: owend
ms.openlocfilehash: b54ac204cd09651a933f1c53c7780fc96ae1bfb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667443"
---
# <a name="partitions-restore-database-dialog-box-analysis-services---multidimensional-data"></a>Секции (диалоговое окно «Восстановление базы данных») (службы Analysis Services - многомерные данные)
  Страница **Секции** диалогового окна **Восстановление базы данных** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] позволяет указать расположение для восстановления локальных секций, а также указать, восстанавливать ли удаленные секции и удаленные файлы резервных копий для восстановления удаленных секций.  
  
> [!IMPORTANT]  
>  Пользователь, выполняющий команду восстановления, должен иметь разрешение на чтение из папки резервного копирования, указанной для каждого восстанавливаемого файла. Чтобы восстановить базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которая не установлена на сервере, пользователь также должен быть членом роли сервера для этого экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] . Чтобы перезаписать базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , пользователь должен быть членом одной из следующих ролей: роль сервера для экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или роль базы данных с разрешениями "Полный доступ (администратор)" в восстанавливаемой базе данных.  
  
> [!NOTE]  
>  После восстановления существующей базы данных пользователь, выполнявший восстановление, может утратить доступ к этой базе данных. Потеря доступа может произойти в случае, если на время создания резервной копии этот пользователь не был членом роли сервера и роли базы данных с разрешением «Полный доступ (Администратор)».  
  
 **Отображение страницы «Секции» в диалоговом окне «Восстановление базы данных»**  
  
-   В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши папку **Базы данных** экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базу данных в окне **Обозреватель объектов**, выберите пункт **Восстановить**, а затем на панели **Выбор страницы**выберите **Секции**.  
  
## <a name="options"></a>Варианты  
 **Сценарий**  
 Создает скрипт восстановления, основанный на параметрах, выбранных в диалоговом окне. Скрипт восстановления написан на языке скриптов служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ASSL).  
  
 Щелкнув значок **Скрипт** , можно отправить скрипт восстановления в новое окно запроса по умолчанию.  
  
 Щелкнув стрелку **Скрипт** , можно открыть меню, в котором можно выбрать, куда отправить скрипт восстановления:  
  
-   в новое окно запроса (по умолчанию);  
  
-   в файл;  
  
-   в буфер обмена;  
  
-   в задание.  
  
 **Восстановить в исходном месте**  
 Выберите этот режим для восстановления локальных секций из файла резервной копии в места их исходного расположения.  
  
 **Укажите разные размещения**  
 Выберите этот режим для указания других мест для восстановления локальных секций.  
  
> [!NOTE]  
>  Изменять папку восстановления локальной секции можно, только если в кубе для этой секции было указано расположение, отличное от стандартного.  
  
 При выборе данного параметра активируется следующая сетка, которая используется для указания папки восстановления каждой локальной секции:  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Cube**|Отображает имя куба, содержащего данную локальную секцию.|  
|**MeasureGroup**|Отображает имя группы мер, содержащей данную локальную секцию.|  
|**Секция**|Отображает имя локальной секции.|  
|**Размер (МБ)**|Показывает размер локальной секции в мегабайтах.|  
|**Исходный каталог**|Выводит имя исходной папки, в которую была сохранена данная локальная секция.|  
|**Каталог восстановления**|Введите имя папки восстановления локальной секции или нажмите кнопку с многоточием (**...**), чтобы выбрать путь к нужной папке в диалоговом окне **Выбор удаленной папки**. Дополнительные сведения о диалоговом окне **Выбор удаленной папки** см. в разделе [Диалоговое окно "Выбор удаленной папки" (службы Analysis Services — многомерные данные)](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md).|  
  
 **Восстановить удаленные секции**  
 Выберите, чтобы восстановить удаленные секции, сохраненные в удаленных файлах резервных копий.  
  
> [!NOTE]  
>  Этот параметр доступен, только если файл резервной копии содержит ссылки на удаленные секции.  
  
 При выборе данного параметра активируется следующая сетка, которая используется для указания папки восстановления каждой локальной секции:  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Server**|Выводит имя экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , управляющего удаленной секцией.|  
|**Источник данных**|Выводит имя источника данных в файле резервной копии, представляющего базу данных, содержащую данную удаленную секцию.|  
|**Файл резервной копии**|Введите полный путь и имя нужного файла резервной копии или нажмите кнопку с многоточием (**...**) для вывода диалогового окна **Расположение файлов базы данных** и выбора пути и имени нужного удаленного файла резервной копии. Дополнительные сведения о диалоговом окне **Расположение файлов базы данных** см. в разделе [Диалоговое окно "Расположение файлов базы данных" (службы Analysis Services — многомерные данные)](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).|  
|**...**|Нажмите, чтобы отобразить диалоговое окно **Удаленные секции — дополнительные параметры** и изменить дополнительные параметры, например строку подключения для источника данных, для восстановления удаленной секции. Дополнительные сведения о диалоговом окне **Удаленные секции — дополнительные параметры** см. в разделе [Диалоговое окно "Удаленные секции — дополнительные параметры" (службы Analysis Services — многомерные данные)](remote-partitions-advanced-settings-dialog-analysis-services-multidimensional-data.md).|  
  
## <a name="see-also"></a>См. также:  
 [Диалоговое окно «Восстановление базы данных» &#40;Analysis Services многомерных данных&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md)   
 [Диалоговое окно «Общие &#40;восстановление базы данных»&#41; &#40;Analysis Services многомерных данных&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md)   
 [Создание и восстановление резервных копий баз данных служб Analysis Services](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  