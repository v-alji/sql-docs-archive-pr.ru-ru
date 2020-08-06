---
title: Удаление модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f5dfd3a6a7615fa3fd91c917bba6dbf0808f0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750483"
---
# <a name="removing-a-data-processing-extension"></a>Удаление модуля обработки данных
  Чтобы удалить модуль обработки данных, просто удалите элемент **Extension** для модуля обработки данных в файле конфигурации. Если выполнены записи для сервера отчетов, а также для конструктора отчетов, удалите элемент **Extension** из файла RSReportServer.config и из файла RSReportDesigner.config. После удаления сведений о конфигурации модуль обработки данных становится недоступным компоненту.  
  
## <a name="see-also"></a>См. также:  
 [Расширения Reporting Services](../reporting-services-extensions.md)   
 [Реализация модуля обработки данных](implementing-a-data-processing-extension.md)   
 [Библиотека модулей служб Reporting Services](../reporting-services-extension-library.md)  
  
  
