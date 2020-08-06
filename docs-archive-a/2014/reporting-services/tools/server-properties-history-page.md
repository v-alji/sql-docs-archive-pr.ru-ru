---
title: Свойства сервера (страница "Журнал") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665229"
---
# <a name="server-properties-history-page"></a>Свойства сервера (страница «Журнал»)
  Используйте эту страницу для задания значения по умолчанию для количества сохраняемых копий журнала отчета. Значение по умолчанию предоставляет начальный параметр, который задает пределы объема журнала отчета для всех отчетов. Эти настройки можно изменить для отдельных отчетов.  
  
 Журнал отчета представляет собой коллекцию моментальных снимков отчета, включающих данные отчета и макет на момент создания моментального снимка. Журнал отчета можно использовать для сохранения копии отчета в том виде, какой он имел на конкретную дату и время. Можно создавать и управлять журналом отчета для отдельных отчетов, выполняемых на сервере отчетов, работающем в собственном режиме, или на сервере отчетов, работающем в режиме интеграции с SharePoint.  
  
 Моментальные снимки журнала отчета хранятся в базе данных сервера отчетов. Если количество хранимых моментальных снимков не ограничено, то следует периодически проверять размер базы данных, чтобы убедиться в том, что она не увеличивается слишком быстро и не занимает чрезмерно большой объем дискового пространства.  
  
 Чтобы открыть эту страницу, в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру сервера отчетов, щелкните его правой кнопкой мыши и выберите пункт **Свойства**. Нажмите кнопку **Журнал** , чтобы открыть эту страницу.  
  
## <a name="options"></a>Варианты  
 **Хранить в журнале отчета неограниченное количество моментальных снимков**  
 Сохранение всех моментальных снимков журнала отчета. Для уменьшения размера журнала отчетов моментальные снимки нужно удалять вручную.  
  
 **Ограничить количество копий журнала отчета**  
 Сохранение заданного количества моментальных снимков журнала отчета. По достижении предела старые копии будут удаляться из журнала отчетов, чтобы освободить место для новых.  
  
 Если объем журнала отчета будет ограничен позже, при превышении указанного предела объема существующего журнала отчета сервер отчетов сокращает объем журнала до нового предела. Первыми удаляются наиболее старые моментальные снимки отчетов. Если журнал отчетов отсутствует или его объем меньше заданного предела, добавляются новые моментальные снимки отчетов. По достижении предела при добавлении новых моментальных снимков отчетов удаляются наиболее старые моментальные снимки.  
  
## <a name="see-also"></a>См. также:  
 [Установка свойств сервера отчетов &#40;Management Studio&#41;](set-report-server-properties-management-studio.md)   
 [Соединение с сервером отчетов в Management Studio](connect-to-a-report-server-in-management-studio.md)   
 [Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md)  
  
  