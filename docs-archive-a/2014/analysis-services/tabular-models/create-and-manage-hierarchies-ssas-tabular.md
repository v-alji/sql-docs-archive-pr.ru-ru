---
title: Создание иерархий и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657926"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a>Создание иерархий и управление ими (табличные службы SSAS)
  Создавать иерархии и управлять ими можно в конструкторе моделей, в представлении диаграммы. Чтобы просмотреть представление диаграммы в конструкторе моделей в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], укажите в меню **Модель** пункт **Представление модели**, а затем выберите пункт **Представление диаграммы**.  
  
 В этот раздел включены следующее задачи:  
  
-   [Создание иерархии](#bkmk_create)  
  
-   [Изменение иерархии](#bkmk_edit)  
  
-   [Удаление иерархии](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> Создание иерархии  
 Иерархию можно создать, используя контекстное меню таблицы и столбцов. При создании иерархии новый родительский уровень отображает выбранные столбцы как дочерние уровни.  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a>Создание иерархии из контекстного меню  
  
1.  В конструкторе моделей (представление диаграммы) в окне таблицы щелкните правой кнопкой мыши столбец и выберите пункт **Создать иерархию**.  
  
     Для выбора нескольких столбцов щелкните каждый столбец, а затем щелкните правой кнопкой мыши для открытия контекстного меню и выберите пункт **Создать иерархию**.  
  
     В нижней части окна таблицы будет создан родительский уровень иерархии, а выбранные столбцы будут скопированы в иерархию в качестве дочерних уровней.  
  
2.  Введите имя иерархии.  
  
 Можно перетаскивать дополнительные столбцы в родительский уровень иерархии, который копирует столбцы. Перетащите дочерний уровень в то место, где он должен появиться в иерархии.  
  
> [!NOTE]  
>  Если вместе с одним или более столбцами выбрано несколько мер или выбраны столбцы из нескольких таблиц, команда «Создать иерархию» в контекстном меню будет недоступна.  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a>Изменение иерархии  
 Иерархию можно переименовать, переименовать ее дочерний узел, изменить порядок следования дочерних узлов, добавить дополнительные столбцы в качестве дочерних узлов, удалить дочерний узел из иерархии, отобразить имя источника дочернего узла (т. е. имя столбца), а также скрыть дочерний узел, если его имя совпадает с именем родительского узла иерархии.  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a>Изменение имени иерархии или дочернего уровня  
  
1.  Щелкните правой кнопкой мыши родительский или дочерний уровень иерархии и выберите пункт **Переименовать**.  
  
2.  Введите новое имя или измените существующее.  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a>Изменение порядка следования дочернего уровня в иерархии  
  
-   Перетащите дочерний уровень в новое положение в иерархии.  
  
-   Можно также щелкнуть правой кнопкой мыши дочерний уровень иерархии и выбрать пункт Переместить вверх для перемещения уровня вверх по списку или Переместить вниз для перемещения уровня вниз по списку.  
  
-   Можно также щелкнуть дочерний уровень иерархии, чтобы выделить его, затем нажать комбинацию клавиш Alt + «Стрелка вверх» для перемещения уровня вверх или комбинацию клавиш Alt + «Стрелка вниз» для перемещения уровня вниз по списку.  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a>Добавление в иерархию нового дочернего уровня  
  
-   Перетащите столбец на родительский уровень или в определенное место в иерархии. Столбец копируется в качестве дочернего уровня иерархии.  
  
-   Также можно щелкнуть правой кнопкой мыши столбец, выбрать пункт **Добавить в иерархию**, а затем выбрать иерархию.  
  
> [!NOTE]  
>  В качестве дочернего уровня иерархии можно добавить скрытый столбец (невидимый в отчетах). Дочерний уровень при этом скрыт не будет.  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a>Удаление дочернего уровня из иерархии  
  
-   Щелкните правой кнопкой мыши дочерний уровень и выберите пункт **Удалить из иерархии**.  
  
-   Можно также щелкнуть дочерний уровень иерархии и нажать клавишу **Delete**.  
  
> [!NOTE]  
>  Если дочерний уровень иерархии был переименован, его имя уже не будет совпадать с именем столбца, из которого уровень был скопирован. Для просмотра столбца, из которого был скопирован уровень, используйте команду **Отобразить имя источника** .  
  
#### <a name="to-show-a-source-name"></a>Отображение имени источника  
  
-   Щелкните правой кнопкой мыши дочерний уровень иерархии и выберите пункт **Отобразить имя источника**. Появится имя столбца, из которого он был скопирован.  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a>Удаление иерархии  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a>Удаление иерархии и ее дочерних уровней  
  
-   Щелкните правой кнопкой мыши родительский уровень иерархии и выберите пункт «Удалить иерархию».  
  
-   Можно также щелкнуть родительский уровень иерархии и нажать клавишу «Delete». При этом также удаляются все дочерние уровни.  
  
## <a name="see-also"></a>См. также:  
 [Конструктор табличных моделей &#40;табличные&#41;SSAS](../tabular-model-designer-ssas-tabular.md)   
 [Иерархии &#40;табличные&#41;SSAS](hierarchies-ssas-tabular.md)   
 [Меры (табличные службы SSAS)](measures-ssas-tabular.md)  
  
  