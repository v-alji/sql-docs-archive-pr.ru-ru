---
title: Предупреждения (конструктор баз данных) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657905"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a>Предупреждения (конструктор баз данных) (службы Analysis Services — многомерные данные)
  Чтобы просмотреть и отклонить правила глобально, а также просмотреть и повторно включить конкретные экземпляры отклоненных предупреждений, используется вкладка **Предупреждения** . На вкладке **Предупреждения** отображаются две сетки: **Правила предупреждений конструктора** и **Отключенные предупреждения**.  
  
 **Отображение вкладки «Предупреждения»**  
  
1.  В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
2.  В **обозревателе решений**щелкните правой кнопкой мыши проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , выберите команду **Изменить базу данных**, а затем перейдите на вкладку **Предупреждения** .  
  
## <a name="design-warning-rules-grid"></a>Сетка «Правила предупреждений конструктора»  
 В сетке **Правила предупреждений конструктора** отображаются все правила предупреждений конструктора. Эта сетка также управляет правилами, которые включены в базу данных. Чтобы включить или выключить правило предупреждения, установите или снимите флажок.  
  
 В сетке **Правила предупреждений конструктора** имеются следующие столбцы.  
  
 **Описание**  
 Отображает имя правила. Правила группируются по категориям.  
  
 **Важность**  
 Отображает уровень важности, назначенный правилу.  
  
 **Комментарии**  
 Позволяет пользователю ввести комментарий, который объясняет, почему отключено предупреждение (необязательно).  
  
## <a name="dismissed-warnings-grid"></a>Сетка «Отключенные предупреждения»  
 В сетке **Отключенные предупреждения** отображаются все определенные предупреждения, которые были отключены в окне **Список ошибок**. Чтобы возобновить выдачу предупреждения, выделите его в сетке и нажмите кнопку **Включить заново**.  
  
 Сетка **Отключенные предупреждения** содержит следующие элементы.  
  
 **Объект**  
 Отображает значок, представляющий тип и имя объекта.  
  
 **Тип**  
 Отображает тип объекта.  
  
 **Описание**  
 Отображает имя правила.  
  
 **Важность**  
 Отображает уровень важности, назначенный правилу.  
  
 **Комментарии**  
 Отображает комментарий, введенный, когда предупреждение было отклонено. Здесь можно добавить или изменить комментарий.  
  
 **Включить заново**  
 Заново включает выбранные предупреждения.  
  
> [!NOTE]  
>  Если объект имеет предупреждение, но находится в недопустимом состоянии или был вручную удален из проекта, то рядом с предупреждением в списке появляется значок ошибки. Чтобы отклонить предупреждение, выделите его и нажмите кнопку **Включить заново**.  
  
## <a name="see-also"></a>См. также:  
 [Диалоговое окно "Отклонить предупреждение" &#40;Analysis Services многомерных данных&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md)   
 [Общие &#40;конструктор баз данных&#41; &#40;Analysis Services многомерных данных&#41;](general-database-designer-analysis-services-multidimensional-data.md)  
  
  