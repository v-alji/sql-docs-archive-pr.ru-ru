---
title: Добавление, изменение или удаление допустимых значений параметра отчета (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportparameters.availablevalues.f1
- "10455"
- "10071"
ms.assetid: 0e03264c-523f-4c59-b71b-ceef600f75f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 985ab3e8dc1d74f94e7242ff57f46ffe4fba9586
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663974"
---
# <a name="add-change-or-delete-available-values-for-a-report-parameter-report-builder-and-ssrs"></a>Добавление, изменение и удаление допустимых значений параметра отчета (построитель отчетов и службы SSRS)
  После создания параметра отчета можно указать список допустимых значений, которые будут выведены для пользователя. Список допустимых значений ограничивает значения, которые может выбрать пользователь, набором допустимых значений.  
  
 Допустимые значения выводятся в раскрывающемся списке рядом с параметром отчета на панели инструментов при выполнении отчета. Параметры отчета могут представлять одно или несколько значений. В случае нескольких значений в верхней позиции списка будет расположено значение **Выделить все** , предоставляя пользователю возможность выбрать или очистить все значения одним щелчком.  
  
 Можно предоставить статический список значений или список из набора данных отчета. Дополнительно значениям можно присвоить понятные имена, указав значение в поле метки. Например, для параметра на основе поля `ProductID` можно вывести в метке параметра поле `ProductName` . При работе отчета пользователь сможет выбирать названия продуктов, но на самом деле выбранное значение будет соответствовать полю `ProductID`.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 После публикации отчета можно изменить доступные значения, определяемые в отчете с помощью средства разработки отчетов, задавая значения свойств параметров на сервере отчетов. Дополнительные сведения см. в разделе [Параметры отчета (построитель отчетов и конструктор отчетов)](report-parameters-report-builder-and-report-designer.md).  
  
### <a name="to-add-or-change-the-available-values-for-a-report-parameter"></a>Добавление или изменение допустимых значений параметра отчета  
  
1.  В области данных отчета разверните узел «Параметры». Щелкните правой кнопкой мыши параметр и выберите пункт **Свойства параметра**. Откроется диалоговое окно **Свойства параметра отчета** .  
  
    > [!NOTE]  
    >  Если область данных отчета не появилась, в меню **Вид** выберите команду **Данные отчета**.  
  
2.  Нажмите кнопку **Допустимые значения**. Выберите параметр допустимых значений.  
  
    -   Нажмите кнопку **Указать значения** , чтобы вручную ввести список значений, и, по желанию, понятные имена (метки) для значений.  
  
         Нажмите кнопку **Добавить** и введите значение в текстовое поле **Значение** и, по желанию, метку в текстовое поле **Метка** . Если не указать метку, будет использовано значение. Для значения можно записать выражение. Тип данных должен соответствовать типу данных параметра. Нельзя задавать параметры в выражении с помощью имен полей. Примеры см. в разделе [Часто используемые фильтры (построитель отчетов и службы SSRS)](commonly-used-filters-report-builder-and-ssrs.md).  
  
         Повторите этот шаг для всех значений, которые нужно указать. Порядок, в котором значения отображаются в данном списке, определяет порядок, в котором пользователь увидит их в раскрывающемся списке. Чтобы изменить порядок элементов списка, щелкните текстовое поле **Значение** или **Метка** , чтобы выбрать элемент, а потом с помощью кнопок со стрелками вверх и вниз переместите выбранный элемент вверх или вниз по списку.  
  
    -   Чтобы ввести имя существующего набора данных, который получает значения и, по желанию, понятные имена для данного параметра, щелкните **Получать значения из запроса** .  
  
        > [!IMPORTANT]  
        >  Если один и тот же набор данных содержит параметр запроса, соответствующий параметру отчета, то отчет отобразит сообщение об ошибке при попытке запустить его. Эту ошибку можно устранить, использовав другой набор данных для получения значений.  
  
         В поле **Набор данных**введите имя набора данных.  
  
         В поле **Поле значения**выберите имя поля, которое предоставляет значения параметра.  
  
         В поле **Поле метки**выберите имя поля, предоставляющего понятные имена для параметра. Если для понятных имен нет отдельного поля, выберите поле, которое было выбрано для поля **Значение** .  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     При предварительном просмотре отчета можно увидеть раскрывающийся список допустимых значений параметра.  
  
### <a name="to-remove-the-available-values-for-a-report-parameter"></a>Удаление допустимых значений параметра отчета  
  
1.  В области данных отчета разверните узел «Параметры». Щелкните правой кнопкой мыши параметр и выберите пункт **Свойства параметра**. Откроется диалоговое окно **Параметры отчета** .  
  
2.  Нажмите кнопку **Допустимые значения**.  
  
3.  В поле **Выберите один из следующих параметров**укажите значение **Нет**.  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     При предварительном просмотре отчета можно увидеть, что для данного параметра раскрывающийся список допустимых значений больше не появляется.  
  
## <a name="see-also"></a>См. также:  
 [Изменение порядка параметров отчета (построитель отчетов и службы SSRS)](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)   
 [Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)   
 [Добавление каскадных параметров в отчет (построитель отчетов и службы SSRS)](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Добавление, изменение или удаление значения по умолчанию для параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-default-values-for-a-report-parameter.md)   
 [Ссылки на коллекцию параметров (построитель отчетов и службы SSRS)](built-in-collections-parameters-collection-references-report-builder.md)   
 [Учебник. Добавление параметра к отчету (построитель отчетов)](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md)  
  
  