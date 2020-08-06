---
title: Учебник. Добавление круговой диаграммы к отчету (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735950"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a>Учебник. Добавление круговой диаграммы к отчету (построитель отчетов)
  Круговые и кольцевые диаграммы отображают данные в виде пропорциональных долей целого. Круговые диаграммы обычно используются для сравнения групп. Круговые и кольцевые диаграммы, наряду с пирамидальными и воронкообразными диаграммами, относятся к группе диаграмм, называемых фигурными. Фигурные диаграммы не имеют осей. После перетаскивания числового поля на фигурную диаграмму в этой диаграмме вычисляется процентная доля каждого значения в общей сумме.  
  
 Если на круговой диаграмме расположено слишком много точек данных, метки точек данных могут располагаться близко друг к другу, и их будет трудно читать. В этом случае лучше использовать график. Круговую диаграмму рекомендуется использовать только в случае, если данные статистически обработаны в небольшое количество точек данных.  
  
 На приведенной ниже иллюстрации показана круговая диаграмма, которую предстоит создать.  
  
 ![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a>Что вы узнаете  
 В этом учебнике рассматривается следующее.  
  
1.  [Создание круговой диаграммы с помощью мастера диаграмм](#Chart)  
  
2.  [Выбор типа диаграммы](#ChartType)  
  
3.  [Отображение процентов в каждом срезе](#Percentages)  
  
4.  [Объединение небольших срезов круговой диаграммы в один срез](#CombineSlices)  
  
5.  [Настройка эффекта рисования](#DrawingEffect)  
  
6.  [Добавление заголовка отчета](#Title)  
  
7.  [Сохранение отчета](#Save)  
  
> [!NOTE]  
>  В этом учебнике шаги для мастера объединены в две процедуры. Пошаговые инструкции по переходу к серверу отчетов, добавлению источника данных и набора данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета (построитель отчетов)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).  
  
 Предполагаемое время для выполнения заданий этого учебника: 10 минут  
  
## <a name="requirements"></a>Требования  
 Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a>1. Создание круговой диаграммы с помощью мастера диаграмм  
 В диалоговом окне «Приступая к работе» создайте внедренный набор данных с помощью мастера диаграмм, выберите общий источник данных и создайте круговую диаграмму.  
  
> [!NOTE]  
>  В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется. В связи с этим запрос получается весьма длинным. В рабочей среде запрос не будет содержать данные. Этот запрос содержит данные только в учебных целях.  
  
#### <a name="to-create-a-new-chart-report"></a>Создание нового отчета с диаграммой  
  
1.  Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.  
  
     Откроется диалоговое окно Приступая к работе.  
  
    > [!NOTE]  
    >   Если диалоговое окно «Приступая к работе» не откроется, выберите команду **Создать**в меню кнопки «Построитель отчетов».  
  
2.  Убедитесь, что на левой панели выбран **Новый отчет** .  
  
3.  На правой панели выберите **Мастер диаграмм**.  
  
4.  На странице **Выбор набора данных** нажмите кнопку **Создать набор данных**, а затем кнопку **Далее**.  
  
5.  На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных, а затем нажмите кнопку **Далее**. Может потребоваться указать имя пользователя и пароль.  
  
    > [!NOTE]  
    >  При наличии необходимых разрешений выбор источника данных не имеет существенного значения. Этот источник данных не будет использоваться для получения данных. Дополнительные сведения см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).  
  
6.  На странице **Конструирование запроса** нажмите кнопку **изменить как текст**.  
  
7.  На панель запроса вставьте следующий запрос:  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  Нажмите кнопку Выполнить (**!**), чтобы просмотреть данные, на основе которых будет создана диаграмма (необязательно).  
  
9. Щелкните **Далее**.  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a>2. Выбор типа диаграммы  
 Можно выбрать один из различных стандартных типов диаграмм.  
  
#### <a name="to-add-a-pie-chart"></a>Добавление круговой диаграммы  
  
1.  На странице **Выбор типа диаграммы** выберите **круговая диаграмма**, а затем нажмите кнопку **Далее**. Откроется страница **Расположение полей диаграммы** .  
  
     На странице **Расположение полей диаграммы** перетащите поле Product на панель **Категории** . Категории определяют номера срезов в круговой диаграмме. В этом примере восемь срезов — по одному для каждого продукта.  
  
2.  Перетащите поле Sales на панель **Значения** . Поле Sales представляет объем продаж по подкатегории. На панели **Значения** отображается выражение `[Sum(Sales)]` , так как на диаграмме отображается агрегат для каждого из продуктов.  
  
3.  Щелкните **Далее**.  
  
4.  На панели Стили на странице **Выбор стиля** выберите стиль.  
  
     Стиль задает стиль шрифта, набор цветов и стиль границы. При выборе стиля на панели просмотра отобразится образец диаграммы с этим стилем.  
  
5.  Нажмите кнопку **Готово**.  
  
     Диаграмма добавляется в область конструктора.  
  
6.  Щелкните диаграмму, чтобы отобразить ее маркеры. Перетащите правый нижний угол диаграммы вниз, чтобы увеличить ее размер. Обратите внимание, что область конструктора отчета увеличивается для соответствия размеру диаграммы.  
  
7.  Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
 В отчете отображается круговая диаграмма с восемью срезами, по одному для каждого продукта. Размер каждого среза представляет продажи для этого продукта. Три среза диаграммы достаточно тонкие.  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a>3. Отображение процентных значений в каждом срезе  
 На каждом срезе круговой диаграммы можно отобразить процент для этого среза относительно полной круговой диаграммы.  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a>Отображение процентов в каждом срезе круговой диаграммы  
  
1.  Переключитесь в режим конструктора отчета.  
  
2.  Щелкните правой кнопкой мыши круговую диаграмму и выберите пункт **Отобразить метки данных**. На диаграмме появятся метки данных.  
  
3.  Щелкните правой кнопкой мыши метку и выберите пункт **Свойства метки ряда**.  
  
4.  В поле данные метки в раскрывающемся списке выберите **#PERCENT**.  
  
     Чтобы значения отображались в виде процентов, свойство UseValueAsLabel должно иметь значение false. Если в диалоговом окне **Подтверждение действия** будет предложено задать это значение, нажмите кнопку **Да**.  
  
5.  Используемых Чтобы указать, сколько десятичных разрядов отображается в метке, введите, `#PERCENT{Pn}` где *n* — число десятичных разрядов для отображения. Например, чтобы не отображать десятичные разряды, введите `#PERCENT{P0}` .  
  
    > [!NOTE]  
    >  Поле**Формат чисел** в диалоговом окне **Свойства метки ряда** не имеет значения, если выбрано форматирование в процентах. Это форматирует метки в виде процентов, но не вычисляет процент, который представляет каждый срез круговой диаграммы.  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
 В отчете отображается процент от целого для каждого среза круговой диаграммы.  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a>4. Объединение маленьких срезов в один срез  
 Три среза диаграммы достаточно маленькие. Можно объединить несколько небольших срезов в один большой срез, представляющий все эти срезы.  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a>Объединение срезов круговой диаграммы, имеющих размер менее 5 процентов, в один срез  
  
1.  Переключитесь в режим конструктора отчета.  
  
2.  На вкладке **вид** в группе **Показать/скрыть** выберите **Свойства**.  
  
3.  В области конструктора щелкните любой сегмент круговой диаграммы. На панели «Свойства» отображаются свойства ряда.  
  
4.  В разделе **Общие** разверните узел **CustomAttributes** .  
  
5.  Присвойте свойству **CollectedStyle** значение **SingleSlice**.  
  
6.  Убедитесь в том, что свойство **CollectedThreshold** имеет значение 5.  
  
7.  Убедитесь в том, что свойство **CollectedThresholdUsePercent** имеет значение **True**.  
  
8.  На ленте на вкладке **Главная** нажмите кнопку **выполнить** , чтобы просмотреть отчет.  
  
 В условных обозначениях теперь существует категория «Прочее». Новый срез круговой диаграммы объединяет все срезы, имеющие размер менее 5%, в один срез, имеющий размер 6% от всей круговой диаграммы.  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a>5. Настройка эффектов рисования  
 В мастере диаграмм для круговой диаграммы по умолчанию установлен стиль «Аквамарин» с вогнутым эффектом рисования. Эти параметры можно изменить после запуска мастера.  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a>Добавление эффекта рисования к круговой диаграмме  
  
1.  Переключитесь в режим конструктора отчета.  
  
2.  Если панель свойств еще не открыта, на вкладке **вид** выберите **свойства**.  
  
3.  Дважды щелкните саму круговую диаграмму. На панели свойств отобразятся свойства рядов для круговой диаграммы.  
  
4.  На панели «Свойства» разверните узел **CustomAttributes** .  
  
5.  Задайте для **параметр PieDrawingStyle** значение **софтедже**.  
  
    > [!NOTE]  
    >  Эффекты рисования и трехмерные эффекты являются взаимоисключающими. Если к диаграмме применены трехмерные эффекты, **параметр PieDrawingStyle** недоступен на панели «Свойства».  
  
6.  Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
 На следующей иллюстрации показана круговая диаграмма с эффектом размытых краев.  
  
 ![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a>6. Добавление заголовка отчета  
  
#### <a name="to-add-a-report-title"></a>Добавление заголовка отчета  
  
1.  В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.  
  
2.  Введите **Продажи фотоаппаратов и видеокамер**, нажмите клавишу ВВОД, а затем введите **В процентах от общего объема продаж**, после чего он будет выглядеть следующим образом:  
  
     **Продажи фотоаппаратов и видеокамер**  
  
     **В процентах от общего объема продаж**  
  
3.  Выберите **продажи камеры и**видеокамеры и нажмите кнопку **полужирный** в разделе **Шрифт** на вкладке ленты **Главная** .  
  
4.  Выберите в **процентах от общего объема продаж**, а в разделе **Шрифт** на вкладке **Главная** установите размер шрифта равным **10**.  
  
5.  Может потребоваться увеличить высоту текстового поля «Заголовок» для соответствия размерам двух строк текста (необязательно).  
  
     Данный заголовок появится в верхней части отчета. При отсутствии верхнего колонтитула страницы элементы в верхней части текста отчета выполняют роль заголовка отчета.  
  
6.  Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
##  <a name="7-save-the-report"></a><a name="Save"></a>7. Сохранение отчета  
  
#### <a name="to-save-the-report"></a>Сохранение отчета  
  
1.  Переключитесь в режим конструктора отчета.  
  
2.  Нажмите кнопку «Построитель отчетов» и выберите **Сохранить как**.  
  
3.  В поле **Имя**введите **Круговая диаграмма продаж**.  
  
4.  Выберите команду **Сохранить**.  
  
 Отчет будет сохранен на сервере отчетов.  
  
## <a name="next-steps"></a>Next Steps  
 Учебник «Добавление круговой диаграммы в отчет» успешно завершен. Дополнительные сведения о диаграммах см. в разделах [Диаграммы (построитель отчетов и службы SSRS)](report-design/charts-report-builder-and-ssrs.md) и [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).  
  
## <a name="see-also"></a>См. также:  
 [Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md)   
 [Построитель отчетов в SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)  
  
  