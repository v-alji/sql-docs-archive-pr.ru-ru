---
title: Определение и просмотр перспектив | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734549"
---
# <a name="defining-and-browsing-perspectives"></a>Определение и поиск перспектив
  Перспектива может упростить вид куба для определенных целей. По умолчанию пользователям доступны для просмотра все элементы куба, на которые они имеют разрешения. Все элементы, которые видит пользователь при просмотре всего куба служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , называются перспективой по умолчанию для куба. Представление полного куба может оказаться слишком сложным для перемещений, особенно для тех пользователей, которым для решения задач, связанных с бизнес-аналитикой и отчетностью, достаточно доступа лишь к малой его части.  
  
 Чтобы упростить излишне сложный куб, можно создать его отображаемые подмножества, называемые *перспективами*, которые отражают лишь небольшую часть групп мер, мер, измерений, атрибутов, иерархий, ключевых показателей эффективности, операций и вычисляемых элементов этого куба. Это может оказаться полезным для работы с клиентскими приложениями, написанных для предыдущей версии служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Эти клиенты не имеют концепции, например папок отображения или перспектив, но перспектива рассматривается клиентами прошлых версий как куб. Дополнительные сведения см. в разделах [Перспективы](multidimensional-models-olap-logical-cube-objects/perspectives.md)и [Перспективы в многомерных моделях](multidimensional-models/perspectives-in-multidimensional-models.md).  
  
> [!NOTE]  
>  Перспектива не является механизмом безопасности, она призвана повысить удобство работы пользователя. Все параметры безопасности перспективы наследуются из базового куба.  
  
 В задачах этого раздела будет определено несколько разных перспектив, в которых затем будет просмотрен куб.  
  
## <a name="defining-an-internet-sales-perspective"></a>Определение перспективы Internet Sales  
  
1.  Откройте конструктор кубов для куба "Учебник по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] " и перейдите на вкладку **Перспективы** .  
  
     Все объекты и их типы отображаются на панели **Перспективы** , как показано на рисунке ниже.  
  
     ![Панель «Перспективы» конструктора кубов](../../2014/tutorials/media/l9-perspectives-1.gif "Панель «Перспективы» конструктора кубов")  
  
2.  На панели инструментов вкладки **Перспективы** нажмите кнопку **Создать перспективу** .  
  
     Новая перспектива появится в столбце **Имя перспективы** с заданным по умолчанию именем **Перспектива**, как показано на рисунке ниже. Обратите внимание, что для каждого из объектов установлен флажок. Пока не снят флажок для одного из объектов, перспектива будет идентична заданной по умолчанию перспективе данного куба.  
  
     ![Новая перспектива в столбце «Имя перспективы»](../../2014/tutorials/media/l9-perspectives-2.gif "Новая перспектива в столбце «Имя перспективы»")  
  
3.  Измените имя перспективы на `Internet Sales` .  
  
4.  В следующей строке задайте для свойства DefaultMeasure значение **Продажи через Интернет — объем продаж**.  
  
     При просмотре куба с помощью этой перспективы будет видна именно эта мера, если не будет выбрана другая.  
  
    > [!NOTE]  
    >  В окне свойств на вкладке [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Структура куба **можно также указать меру по умолчанию для всего куба учебника по службам** .  
  
5.  Снимите флажки для следующих объектов:  
  
    -   `Reseller Sales`Группа мер  
  
    -   группа мер**Квоты продаж** ;  
  
    -   группа мер**Квоты продаж 1** ;  
  
    -   измерение куба**Торговый посредник** ;  
  
    -   измерение куба**География торгового посредника** ;  
  
    -   измерение куба**Территория продаж** ;  
  
    -   измерение куба**Сотрудник** ;  
  
    -   измерение куба**Продвижение** ;  
  
    -   ключевой показатель эффективности**Доход от продаж через торгового посредника** ;  
  
    -   именованный набор**Крупные торговые посредники** ;  
  
    -   вычисляемый элемент**Итоговая сумма продаж** ;  
  
    -   вычисляемый элемент**Общая стоимость товара** ;  
  
    -   вычисляемый элемент**Коэффициент валовой прибыли торгового посредника** ;  
  
    -   вычисляемый элемент**Итоговый коэффициент валовой прибыли** ;  
  
    -   вычисляемый элемент**Доля продаж через торгового посредника по всей номенклатуре продукции** ;  
  
    -   вычисляемый элемент**Общая доля продаж по всей номенклатуре продукции** .  
  
     Эти объекты не связаны с продажами через Интернет.  
  
    > [!NOTE]  
    >  В каждом из измерений отдельно можно выбрать пользовательские иерархии и атрибуты, которые должны отображаться в данной перспективе.  
  
## <a name="defining-a-reseller-sales-perspective"></a>Определение перспективы Reseller Sales  
  
1.  На панели инструментов вкладки **Перспективы** нажмите кнопку **Создать перспективу** .  
  
2.  Измените имя новой перспективы на `Reseller Sales` .  
  
3.  Установите меру **Товарооборот посредников — объем продаж** в качестве меры по умолчанию.  
  
     Если пользователи выполняют просмотр куба при помощи этой перспективы, они будут видеть именно эту меру, если не выберут другую.  
  
4.  Снимите флажки для следующих объектов:  
  
    -   `Internet Sales`Группа мер  
  
    -   группа мер**Причина покупки через Интернет** ;  
  
    -   измерение куба**Заказчик** ;  
  
    -   измерение куба**Подробности заказа через Интернет** ;  
  
    -   измерение куба**Причина покупки** ;  
  
    -   действие детализации**Действие детализации продаж через Интернет** ;  
  
    -   вычисляемый элемент**Итоговая сумма продаж** ;  
  
    -   вычисляемый элемент**Общая стоимость товара** ;  
  
    -   вычисляемый элемент**Коэффициент валовой прибыли от продаж через Интернет** ;  
  
    -   вычисляемый элемент**Итоговый коэффициент валовой прибыли** ;  
  
    -   вычисляемый элемент**Доля продаж через Интернет по всей номенклатуре продукции** ;  
  
    -   вычисляемый элемент**Общая доля продаж по всей номенклатуре продукции** .  
  
     Эти объекты не связаны с продажами через торгового посредника.  
  
## <a name="defining-a-sales-summary-perspective"></a>Определение перспективы сводки о продажах  
  
1.  На панели инструментов вкладки **Перспективы** нажмите кнопку **Создать перспективу** .  
  
2.  Измените имя новой перспективы на `Sales Summary` .  
  
    > [!NOTE]  
    >  Нельзя указывать вычисляемую меру как меру по умолчанию.  
  
3.  Снимите флажки для следующих объектов:  
  
    -   `Internet Sales`Группа мер  
  
    -   `Reseller Sales`Группа мер  
  
    -   группа мер**Причина покупки через Интернет** ;  
  
    -   группа мер**Квоты продаж** ;  
  
    -   группа мер**Квоты продаж 1** ;  
  
    -   измерение куба**Подробности заказа через Интернет** ;  
  
    -   измерение куба**Причина покупки** ;  
  
    -   действие детализации**Действие детализации продаж через Интернет** ;  
  
4.  Установите флажки для следующих объектов:  
  
    -   мера**Число продаж через Интернет** ;  
  
    -   мера**Число продаж через торговых посредников** .  
  
## <a name="browsing-the-cube-through-each-perspective"></a>Просмотр куба в каждой из перспектив  
  
1.  В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.  
  
2.  После успешного завершения развертывания перейдите на вкладку **Браузер** и нажмите кнопку **Повторное соединение** .  
  
3.  Запустите Excel.  
  
4.  При выполнении команды «Анализ в Excel» выводится запрос выбора перспективы, которая будет использоваться при просмотре модели в Excel, как показано на следующем рисунке.  
  
     ![Объекты перспективы «Продажи через Интернет»](../../2014/tutorials/media/l9-perspectives-3.gif "Объекты перспективы «Продажи через Интернет»")  
  
5.  Кроме того, можно запустить Excel из меню «Пуск» Windows, определить подключение к базе данных учебника по службам Analysis Services на узле localhost и выбрать перспективу в мастере подключения к данным, как показано на следующем рисунке.  
  
     ![Мастер подключения к данным в Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Мастер подключения к данным в Excel")  
  
6.  Выберите `Internet Sales` в списке **Перспектива** , а затем просмотрите меры и измерения на панели Метаданные.  
  
     Обратите внимание, что отображаются только те объекты, которые определены для перспективы «Internet Sales».  
  
7.  На панели "Метаданные" разверните узел **Меры**.  
  
     Обратите внимание, что `Internet Sales` отображается только группа мер, а также отношение **товарооборота через Интернет** и **продажи через Интернет ко всем** вычисляемым элементам продукты.  
  
8.  В модели снова выберите Excel. Выберите `Sales Summary`.  
  
     Обратите внимание, что в каждой из этих групп мер отображается лишь одна мера, как показано на следующем рисунке.  
  
     ![Меры «Продажи через Интернет» и «Продажи через посредников»](../../2014/tutorials/media/l9-perspectives-4.gif "Меры «Продажи через Интернет» и «Продажи через посредников»")  
  
## <a name="next-task-in-lesson"></a>Следующая задача занятия  
 [Определение и просмотр переводов](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a>См. также:  
 [Перспективы](multidimensional-models-olap-logical-cube-objects/perspectives.md)   
 [Перспективы в многомерных моделях](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  