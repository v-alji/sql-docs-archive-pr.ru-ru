---
title: Определение логики операций со счетами (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728961"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a>Определение логики операций со счетами (мастер бизнес-аналитики)
  Используйте страницу **Определение логики операций со счетами** для сопоставления типов записей, определенных в экземпляре служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , с типами записей, заданных таблицей-источником в источнике данных, поставляющем данные для измерения счетов.  
  
> [!NOTE]  
>   Эта страница появится, если атрибут измерения будет сопоставлен **типу счета** на странице **Настройка атрибутов измерения** .  
  
## <a name="options"></a>Варианты  
 **Типы счетов исходной таблицы**  
 Отображает значения, которые содержатся в атрибуте измерения, назначенном типу атрибута **Тип счета** на странице **Настройка атрибутов измерения** .  
  
 **Встроенные типы счетов**  
 Выберите тип счета, определенный в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , который соответствует типам счетов записей таблицы-источника.  
  
 Следующая таблица содержит список типов счетов, определенных в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
|Значение|Описание|  
|-----------|-----------------|  
|**Ресурс**|Ценность вещей, находящихся в собственности в заданное время.|  
|**Balance**|Итоговое количество чего-либо в заданное время.|  
|**Расход**|Ценность потраченного.|  
|**Поток**|Подсчет приращений элементов.|  
|**Доходы**|Ценность полученного.|  
|**Обязательство**|Ценность подлежащего возврату в заданное время.|  
|**Статистические**|Вычисленное соотношение или количество некоторой величины, не подлежащей статистической обработке.|  
  
## <a name="see-also"></a>См. также:  
 [Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md)   
 [Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md)   
 [Конструктор измерений &#40;Analysis Services многомерных данных&#41;](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
