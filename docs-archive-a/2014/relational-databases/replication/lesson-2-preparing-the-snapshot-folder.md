---
title: Занятие 2. Подготовка папки моментальных снимков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739710"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a>Занятие 2. Подготовка папки моментальных снимков
  На этом занятии можно научиться настраивать папку моментальных снимков для создания и хранения моментального снимка публикации.  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a>Создание ресурса для папки моментальных снимков и настройка разрешений  
  
1.  В проводнике Windows перейдите к папке данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Путь по умолчанию — «C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data».  
  
2.  Создайте папку с именем **repldata**.  
  
3.  Правой кнопкой мыши щелкните эту папку и выберите пункт **Свойства**.  
  
4.  В диалоговом окне **Свойства repldata** на вкладке **Общий доступ** щелкните **Открыть общий доступ**.  
  
5.  В диалоговом окне **Общий доступ к файлу** щелкните **Открыть общий доступ**, а затем — **Готово**.  
  
6.  На вкладке **Безопасность** нажмите **Изменить**.  
  
7.  В диалоговом окне **Разрешения** нажмите кнопку **Добавить**. В текстовом поле **выберите пользователя, компьютеры, учетная запись службы или группы** введите имя учетной записи агент моментальных снимков, созданной на занятии 1, как \<_Machine_Name> _**\ repl_snapshot**, где \<*Machine_Name> * — имя издателя. Щелкните **Проверить имена**и нажмите кнопку **ОК**.  
  
8.  Повторите предыдущий шаг, чтобы добавить разрешения для агент распространения, как \<_Machine_Name> _ **\ repl_distribution**, а также для агент слияния как \<_Machine_Name> _ **\ repl_merge**.  
  
9. Убедитесь в том, что следующие разрешения допустимы:  
  
    -   repl_snapshot — «Полный контроль»;  
  
    -   repl_distribution — «Чтение»;  
  
    -   repl_merge — «Чтение».  
  
10. Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Свойства repldata** , и создайте ресурс repldata.  
  
## <a name="next-steps"></a>Next Steps  
 Настройка ресурса папки моментальных снимков выполнена успешно. Далее предстоит настроить распространение. См. [Занятие 3. Настройка распространения](lesson-3-configuring-distribution.md).  
  
## <a name="see-also"></a>См. также:  
 [Защита папки моментальных снимков](security/secure-the-snapshot-folder.md)  
  
  
