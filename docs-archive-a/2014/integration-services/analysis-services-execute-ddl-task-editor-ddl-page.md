---
title: Редактор задачи «Выполнение инструкции DDL Analysis Services» (страница «DDL») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657236"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a>Редактор задачи «Выполнение инструкции DDL служб Analysis Services» (страница DDL)
  Используйте страницу **DDL** диалогового окна **Редактор задачи "Выполнение инструкции DDL служб аналитики"** , чтобы настроить соединение с проектом [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базой данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а также предоставить сведения об источнике инструкций языка определения данных (DDL).  
  
 Дополнительные сведения об этой задаче см. в разделе [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).  
  
## <a name="static-options"></a>Статические параметры  
 **Соединение**  
 Выберите проект [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или диспетчер подключений [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в списке или щелкните \<**New connection...**> и создайте подключение с помощью диалогового окна **Добавление диспетчера соединений со службами Analysis Services**.  
  
 **См. также:** [Диалоговое окно "Добавление диспетчера соединений со службами Analysis Services" в справочнике по пользовательскому интерфейсу](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Диспетчер соединений служб Analysis Services](connection-manager/analysis-services-connection-manager.md)  
  
 **Тип источника**  
 Указать тип источника инструкции DDL. Параметры этого свойства приведены в следующей таблице.  
  
|Значение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Установите в качестве источника инструкцию DDL, содержащуюся в текстовом поле **SourceDirect** . При выборе этого значения в следующем подразделе отображаются динамические параметры.|  
|**Соединение с файлом**|В качестве источника указывается файл, содержащий инструкцию DDL. При выборе этого значения в следующем подразделе отображаются динамические параметры.|  
|**Переменная**|Установите в качестве источника переменную. При выборе этого значения в следующем подразделе отображаются динамические параметры.|  
  
## <a name="dynamic-options"></a>Динамические параметры  
  
### <a name="sourcetype--direct-input"></a>SourceType = Прямой ввод  
 **Source**  
 Введите инструкции DDL или нажмите кнопку с многоточием **(…)** и после этого введите инструкции в диалоговом окне **Инструкции DDL**.  
  
### <a name="sourcetype--file-connection"></a>SourceType = Подключение файла  
 **Source**  
 Выберите "Соединение с файлом" в списке или щелкните \<**New connection...**> и создайте подключение с помощью диалогового окна **Диспетчер соединения файлов**.  
  
 **См. также:** [Диспетчер соединения файлов](connection-manager/file-connection-manager.md)  
  
### <a name="sourcetype--variable"></a>SourceType = Переменная  
 **Source**  
 Выберите переменную в списке или щелкните \<**New variable...**> и создайте переменную с помощью диалогового окна **Добавление переменной**.  
  
 **См. также:** [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md)  
  
## <a name="see-also"></a>См. также:  
 [Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Редактор задачи "Analysis Services выполнение инструкции DDL" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md)   
 [Страница «Выражения»](expressions/expressions-page.md)   
 [Поток управления](control-flow/control-flow.md)   
 [Справочник по языку сценариев Analysis Services &#40;языка ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla)   
 [Справочник по XML для аналитики (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
