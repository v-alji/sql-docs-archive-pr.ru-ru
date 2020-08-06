---
title: rsInternalError — ошибка служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664678"
---
# <a name="rsinternalerror---reporting-services-error"></a>rsInternalError - Ошибка службы Reporting Services
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Идентификатор события|rsInternalError|  
|Источник события|Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings|  
|Компонент|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|Текст сообщения|Произошла внутренняя ошибка на сервере отчетов. Дополнительные подробности см. в журнале ошибок.|  
  
## <a name="explanation"></a>Объяснение  
 Это общее сообщение об ошибке, за которым часто следует более описательное сообщение об ошибке, предоставляющее больше сведений.  
  
 Внутренние ошибки случаются редко. При возникновении такой ошибки дополнительные сведения можно получить в журналах трассировки сервера отчетов. Помимо этого, если вы работаете на компьютере, где произошла ошибка, под учетной записью локального администратора, можно также просмотреть стек вызовов.  
  
## <a name="user-action"></a>Действие пользователя  
 Чтобы определить конкретную причину этого сообщения, просмотрите файлы журнала сервера отчетов, расположенные по адресу \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles. Дополнительные сведения см. в разделе [Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md).  
  
 Для просмотра стека вызова щелкните правой кнопкой мыши на странице, где произошла ошибка, и выберите команду **Исходный код**. Для просмотра стека вызовов необходимы разрешения администратора на том компьютере, где возникла ошибка.  
  
 Если дополнительные сведения недоступны, можно повторить попытку запроса.  
  
## <a name="internal-only"></a>Только для внутреннего использования  
  
## <a name="see-also"></a>См. также:  
 [Запуск и остановка службы сервера отчетов](../report-server/start-and-stop-the-report-server-service.md)  
  
  
