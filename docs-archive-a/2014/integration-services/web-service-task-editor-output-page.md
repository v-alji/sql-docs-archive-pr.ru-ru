---
title: Редактор задачи «веб-служба» (страница «выходные данные») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667782"
---
# <a name="web-service-task-editor-output-page"></a>Редактор задачи «Веб-служба» (страница «Вывод»)
  Используйте страницу **Вывод** диалогового окна **Редактор задачи «Веб-служба»** , чтобы указать, где следует хранить результаты, возвращенные веб-методом.  
  
 Дополнительные сведения об этой задаче см. в разделе [Задача "Веб-служба"](control-flow/web-service-task.md).  
  
## <a name="static-options"></a>Статические параметры  
 **OutputType**  
 Выберите тип хранения, используемый для хранения результатов. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Значение|Описание|  
|-----------|-----------------|  
|**Соединение с файлом**|Хранить результаты в файле. При выборе этого значения отображается динамический параметр **Файл**.|  
|**Переменная**|Хранить результаты в переменной. При выборе этого значения отображается динамический параметр **Переменная**.|  
  
## <a name="outputtype-dynamic-options"></a>Динамические параметры OutputType  
  
### <a name="outputtype--file-connection"></a>OutputType = Соединение с файлом  
 **Файл**  
 Выберите в списке диспетчер подключений файлов или щелкните \<**New Connection...**>, чтобы создать диспетчер подключений.  
  
 **См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).  
  
### <a name="outputtype--variable"></a>OutputType = Переменная  
 **Переменная**  
 Выберите переменную в списке или щелкните \<**New Variable...**> для создания переменной.  
  
 **См. также:**  подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Редактор задачи "веб-служба" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md)   
 [Редактор задачи "веб-служба" &#40;"входная страница"&#41;](../../2014/integration-services/web-service-task-editor-input-page.md)   
 [Страница «Выражения»](expressions/expressions-page.md)  
  
  
