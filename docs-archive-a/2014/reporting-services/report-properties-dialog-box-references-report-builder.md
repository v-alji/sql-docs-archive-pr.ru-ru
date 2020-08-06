---
title: Диалоговое окно «Свойства отчета», ссылки (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733570"
---
# <a name="report-properties-dialog-box-references-report-builder"></a>Диалоговое окно «Свойства отчета» — «Ссылки» (построитель отчетов)
  На вкладке **Ссылки** диалогового окна **Свойства отчета** можно удалить или добавить ссылки на пользовательские или другие внешние сборки и экземпляры пользовательских классов, используемые выражениями в определении отчета. Пользовательские сборки не поддерживаются в локальном режиме построителя отчетов. Для создания отчетов, использующих пользовательские сборки, используйте конструктор отчетов в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .  
  
## <a name="options"></a>Варианты  
 **Добавить или удалить сборки**  
 Отображает список сборок, на которые имеются ссылки в отчете. Сборка должна быть доступна на компьютере, на котором установлено средство для создания отчетов, и на сервере отчетов. Имя ссылки должно точно совпадать с содержимым **\<CodeModule>** тегов в файле языка определения отчетов (RDL).  
  
 **Добавление**  
 Нажмите, чтобы добавить сборку. Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите сборки, необходимые для завершения обработки отчета и оценки выражений.  
  
 **Удалить**  
 Чтобы удалить ссылку на сборку из списка, выделите имя сборки, а затем нажмите кнопку **Удалить** .  
  
 **Добавить или удалить классы**  
 Отображает список экземпляров классов, которые используются в отчете. Список классов используется только элементами на основе экземпляров, но не статическими элементами.  
  
 **Добавление**  
 Нажмите, чтобы добавить ссылку на класс. Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите классы, необходимые для завершения обработки отчета и оценки выражений.  
  
 **Удалить**  
 Чтобы удалить экземпляр класса, выберите его и нажмите кнопку **Удалить** .  
  
 **Крывающемся**  
 Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более высокую позицию списка.  
  
 **Down**  
 Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более низкую позицию списка.  
  
## <a name="see-also"></a>См. также:  
 [Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md)  
  
  