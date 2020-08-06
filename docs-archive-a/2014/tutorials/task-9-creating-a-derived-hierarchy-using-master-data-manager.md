---
title: Задача 9. создание производной иерархии с помощью диспетчер основных данных | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751576"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a>Задача 9. Создание производной иерархии с помощью диспетчера основных данных
  В этой задаче вы создадите производную иерархию с помощью диспетчера основных данных. Эта производная иерархия является производной от отношений атрибутов на основе домена между сущностями **поставщика** и **состояния** .  
  
1.  Перейдите на главную страницу **Диспетчер основных данных** , щелкнув **SQL Server 2012 Master Data Services** в верхней части страницы.  
  
2.  В разделе **задачи администрирования** щелкните **Администрирование системы** .  
  
3.  Наведите указатель мыши на **Управление** в строке меню и выберите пункт **производные иерархии**.  
  
     ![Меню управления — выбрана производная иерархия](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Меню управления — выбрана производная иерархия")  
  
4.  Нажмите кнопку **Добавить производную иерархию (+)** на панели инструментов.  
  
     ![Кнопка «Добавить производную иерархию»](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Кнопка «Добавить производную иерархию»")  
  
5.  Введите **SuppliersInState** в качестве **имени производной иерархии**.  
  
6.  Нажмите кнопку **сохранить** на панели инструментов.  
  
     ![Кнопка «Сохранить производную иерархию»](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Кнопка «Сохранить производную иерархию»")  
  
7.  Перетащите **поставщик** из **доступных уровней: SuppliersInState** на **текущие уровни: SuppliersInState**.  
  
     ![Доступные сущности и иерархии для текущего уровня](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Доступные сущности и иерархии для текущего уровня")  
  
8.  Перетащите **состояние** из **доступных уровней: SuppliersInState** на **текущие уровни: SuppliersInState**. На экране должны быть **текущие уровни** , как показано на следующем рисунке.  
  
     ![Текущие уровни и предварительный просмотр производной иерархии](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Текущие уровни и предварительный просмотр производной иерархии")  
  
9. В окне **предварительного просмотра** разверните узел **Нью {Нью Йорк}** , и в этом состоянии вы должны увидеть одного поставщика, как показано на предыдущем рисунке.  
  
10. Перейдите на главную страницу **Диспетчер основных данных** , щелкнув **SQL Server 2012 Master Data Services** в верхней части страницы.  
  
11. Нажмите кнопку **Браузер**.  
  
12. Наведите указатель мыши на **иерархии** и выберите **производный: SuppliersInState**.  
  
     ![Иерархии — меню Derived:SuppliersInState](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Иерархии — меню Derived:SuppliersInState")  
  
13. Щелкните любой узел **состояния** в представлении в **виде дерева** , и вы увидите поставщиков в этом состоянии на правой панели.  
  
     ![Производная иерархия в обозревателе](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Производная иерархия в обозревателе")  
  
## <a name="next-step"></a>Следующий шаг  
 [Занятие 5.: Автоматизация очистки и сопоставления с помощью SSIS](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  