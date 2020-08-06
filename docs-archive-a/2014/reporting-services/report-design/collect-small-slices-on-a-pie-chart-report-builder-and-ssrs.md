---
title: Сбор мелких срезов на круговой диаграмме (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2302217843864115847aeb544d1c64727b8ad3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664719"
---
# <a name="collect-small-slices-on-a-pie-chart-report-builder-and-ssrs"></a>Сбор мелких срезов на круговой диаграмме (построитель отчетов и службы SSRS)
  Если круговая диаграмма содержит слишком много данных, она выглядит загроможденной. Чтобы исправить это, можно отобразить на круговой диаграмме все данные, находящиеся в пределах определенного значения, одним срезом.  
  
 Чтобы собрать мелкие срезы в один, сначала следует решить, как будет измеряться порог для сбора мелких срезов — в процентном отношении от круговой диаграммы или как фиксированное значение. Затем задайте свойства CollectedThreshold и CollectedThresholdUsePercent. Присвойте свойству CollectedThreshold либо значение в процентах для диаграммы (собираемые данные не будут превышать это значение), либо фактическое пороговое значение собираемых данных. Присвойте свойству CollectedThresholdUsePercent значение, чтобы `True` использовать процентное значение, или `False` для использования фактического значения.  
  
 Можно также собрать мелкие срезы во вторую круговую диаграмму, вызываемую из собранного среза первой диаграммы. Вторая круговая диаграмма отображается справа от исходной круговой диаграммы.  
  
 Нельзя объединить в один срез срезы воронкообразных и пирамидальных диаграмм.  
  
 Пример этой диаграммы доступен в виде образца отчета. Дополнительные сведения о скачивании этого и других примеров отчетов см. в статье [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).  
  
### <a name="to-collect-small-slices-into-a-single-slice-on-a-pie-chart"></a>Сбор мелких срезов в один срез круговой диаграммы  
  
1.  Откройте панель «Свойства».  
  
2.  В области конструктора щелкните любой сегмент круговой диаграммы. На панели «Свойства» отображаются свойства ряда.  
  
3.  В разделе **Общие** разверните узел **CustomAttributes** .  
  
4.  Присвойте свойству CollectedStyle значение **SingleSlice**.  
  
5.  Задайте значение порога сбора и его тип. Следующие примеры демонстрируют общие способы задания порогов сбора.  
  
    -   **В процентах.** Например, можно собрать в один срез все срезы круговой диаграммы, не превышающие 10%.  
  
         Задайте для свойства CollectedThresholdUsePercent значение `True` .  
  
         Присвойте свойству CollectedThreshold значение **10**.  
  
        > [!NOTE]  
        >  Если для присвойте свойству collectedstyle задано значение **значение singleslice**, CollectedThreshold равно значению больше **100**, а CollectedThresholdUsePercent — `True` , то диаграмма выдаст исключение, поскольку не может вычислить процент. Чтобы избежать этого, присвойте свойству CollectedThreshold значение меньше **100**.  
  
    -   **По значению данных.** Например, можно собрать в один срез все срезы круговой диаграммы, не превышающие 5000%.  
  
         Задайте для свойства CollectedThresholdUsePercent значение `False` .  
  
         Присвойте свойству CollectedThreshold значение **5000**.  
  
6.  Задайте в качестве свойства CollectedLabel строку, представляющую текстовую метку, которая будет отображена на собранном срезе.  
  
7.  (Необязательно) Присвойте значения свойствам CollectedSliceExploded, CollectedColor, CollectedLegendText и CollectedToolTip. Эти свойства определяют внешний вид, цвет, текстовую метку, текст условных обозначений и подсказку отдельного среза.  
  
### <a name="to-collect-small-slices-into-a-secondary-callout-pie-chart"></a>Сбор мелких срезов во вторичную, вызываемую круговую диаграмму  
  
1.  Выполните приведенные выше шаги 1—3.  
  
2.  Присвойте свойству CollectedStyle значение **CollectedPie**.  
  
3.  Определите для свойства CollectedThresholdproperty значение порога, мелкие срезы со значениями ниже которого будут собираться в один срез. Если свойство присвойте свойству collectedstyle имеет значение **коллектедпие**, коллектедсрешолдусеперцентпроперти всегда имеет значение `True` , а собранное пороговое значение всегда измеряется в процентах.  
  
4.  (Необязательно) Присвойте значения свойствам CollectedColor, CollectedLabel, CollectedLegendText и CollectedToolTip. Все остальные свойства, в имя которых входит «Collected», не относятся к собранной диаграмме.  
  
> [!NOTE]  
>  Поскольку вторичная круговая диаграмма вычисляется на основе мелких срезов данных, она появится только в режиме предварительного просмотра. Она не появляется в области конструктора.  
  
> [!NOTE]  
>  Форматировать вторичную круговую диаграмму нельзя. По этой причине настоятельно рекомендуется пользоваться для сбора мелких срезов круговых диаграмм первым методом.  
  
## <a name="see-also"></a>См. также:  
 [Круговые диаграммы &#40;построитель отчетов и службы SSRS&#41;](charts-report-builder-and-ssrs.md)   
 [Форматирование точек данных на диаграмме &#40;построитель отчетов и SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)   
 [Отображение меток точек данных за пределами круговой диаграммы &#40;построитель отчетов и SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md)   
 [Отображение процентных значений на круговой диаграмме &#40;построитель отчетов и SSRS&#41;](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)   
 [Добавление в диаграмму объемных эффектов (построитель отчетов и службы SSRS)](chart-effects-add-3d-effects-report-builder.md)  
  
  