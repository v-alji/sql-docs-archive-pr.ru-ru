---
title: Согласование диаграммы базы данных с измененной базой данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729977"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a>Согласование диаграммы базы данных с измененной базой данных (визуальные инструменты для баз данных)
  Сохраняйте диаграмму базы данных, когда вы готовы обновить базу данных для согласования с текущей диаграммой. Однако если с момента открытия базы данных другие пользователи внесли изменения в базу данных, то внесенные ими изменения могут повлиять на вашу диаграмму, и наоборот.  
  
 Сохранение диаграммы приводит к согласованию базы данных с диаграммой путем перезаписи изменений, внесенных другими пользователями.  
  
### <a name="to-update-a-database-to-match-your-diagram"></a>Обновление базы данных для согласования с диаграммой  
  
1.  Сохраните диаграмму базы данных.  
  
     Если диаграмма до этого не сохранялась, введите ее имя в диалоговом окне **Сохранение новой диаграммы базы данных** и нажмите кнопку **ОК**.  
  
2.  В диалоговом окне **Сохранение** перечислены таблицы, которые затронет сохранение диаграммы. Чтобы продолжить, нажмите кнопку **Да** .  
  
3.  В диалоговом окне **Обнаружены изменения базы данных** перечислены объекты, в которые были внесены изменения и которые будут исправлены для согласования с диаграммой. Нажмите кнопку **Да** для сохранения диаграммы и подтверждения всех изменений в списке.  
  
    > [!NOTE]  
    >  Если в диаграмме содержатся удаленные из базы данных таблицы и столбцы, то при сохранении диаграммы в базе данных будут повторно созданы только их определения. При этом процессе не восстанавливаются данные, которые существовали в этих объектах до их удаления.  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a>Обновление диаграммы для согласования с измененной базой данных  
  
1.  Закройте диаграмму без сохранения изменений.  
  
2.  Щелкните диаграмму правой кнопкой мыши в обозревателе объектов.  
  
3.  В контекстном меню выберите пункт **Обновить**.  
  
4.  Снова откройте диаграмму.  
  
## <a name="see-also"></a>См. также:  
 [Работа с диаграммами баз данных (визуальные инструменты для баз данных)](visual-database-tools.md)  
  
  