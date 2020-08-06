---
title: Редактор задачи «веб-служба» (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667787"
---
# <a name="web-service-task-editor-general-page"></a>Редактор задачи «Веб-служба» (страница «Общие»)
  Страница **Общие** в диалоговом окне **Редактор задачи "Веб-служба"** применяется для указания диспетчера HTTP-соединений, расположения файла WSDL, используемого задачей веб-службы, описания задачи веб-службы и загрузки файла WSDL.  
  
 Дополнительные сведения об этой задаче см. в разделе [Задача "Веб-служба"](control-flow/web-service-task.md).  
  
## <a name="options"></a>Параметры  
 **HTTPConnection**  
 Выберите из списка диспетчер подключений или нажмите кнопку \<**New connection...**> для создания нового диспетчера подключений.  
  
> [!IMPORTANT]  
>  Диспетчер HTTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности. Проверка подлинности Windows не поддерживается.  
  
 **См. также:**  подробные сведения о [диспетчере HTTP-подключений](connection-manager/http-connection-manager.md) и о [редакторе диспетчера HTTP-подключений &#40;страница "Сервер"&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md).  
  
 **WSDLFile**  
 Введите полный путь к локальному WSDL-файлу на компьютере или нажмите кнопку обзора **(...)** и выберите файл.  
  
 Если WSDL-файл был загружен на компьютер вручную, выберите этот файл. Однако, если WSDL-файл еще не был загружен, выполните следующие действия.  
  
-   Создайте пустой файл с расширением WSDL.  
  
-   Выберите этот пустой файл для параметра **WSDLFile** .  
  
-   Присвойте параметру **свойство overwritewsdlfile** значение, `True` чтобы разрешить перезапись пустого файла с фактическим WSDL-файлом.  
  
-   Нажмите кнопку **Загрузить язык WSDL** , чтобы загрузить фактический WSDL-файл и перезаписать пустой файл.  
  
    > [!NOTE]  
    >  Кнопка **Загрузить язык WSDL** недоступна, пока не указано имя существующего локального файла в поле **WSDLFile** .  
  
 **OverwriteWSDLFile**  
 Укажите, можно ли перезаписать WSDL-файл для задачи веб-службы.  
  
 Если вы собираетесь загрузить WSDL-файл с помощью кнопки **скачать WSDL** , задайте для этого параметра значение `True` .  
  
 **имя**;  
 Введите уникальное имя задачи веб-службы. Это имя используется в качестве метки для значка задачи.  
  
> [!NOTE]  
>  Имена задач в пределах пакета должны быть уникальными.  
  
 **Описание**  
 Введите описание задачи веб-службы.  
  
 **Загрузить язык WSDL**  
 Загрузите файл WSDL.  
  
 Эта кнопка недоступна, пока не указано имя существующего локального файла в поле **WSDLFile** .  
  
## <a name="see-also"></a>См. также:  
 [Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Редактор задачи "веб-служба" &#40;"входная страница"&#41;](../../2014/integration-services/web-service-task-editor-input-page.md)   
 [Редактор задачи "веб-служба" &#40;страница "выходные данные"&#41;](../../2014/integration-services/web-service-task-editor-output-page.md)   
 [Страница «Выражения»](expressions/expressions-page.md)  
  
  
