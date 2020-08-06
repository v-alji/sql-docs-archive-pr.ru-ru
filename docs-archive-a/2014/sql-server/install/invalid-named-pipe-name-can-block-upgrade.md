---
title: Недопустимое имя именованного канала может препятствовать обновлению | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- invalid named pipes [SQL Server]
- named pipes
ms.assetid: 58c2199c-4fdf-4d43-ac1c-842703344b75
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bacfd3d097d7cccb0a5780328c4db95dc5afc733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749608"
---
# <a name="invalid-named-pipe-name-can-block-upgrade"></a>Неверное имя именованного канала может помешать обновлению
  Обновление завершается ошибкой, если протокол именованных каналов настроен неправильно.  
  
## <a name="component"></a>Компонент  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Описание  
 Во время обновления программа установки запускает [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] экземпляр с поддержкой общей памяти, именованным каналом, который принимает только локальные соединения. Если имя канала, указанное на сервере, не является пустым, оно должно начинаться с строки " \\ \\ .\pipe \\ ", которая должна быть допустимой. Если задано недопустимое имя канала, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] не запустится и установка завершится ошибкой.  
  
## <a name="corrective-action"></a>Действие по исправлению  
 Используйте ** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] служебную программу Network** для указания допустимого имени канала, а затем запустите программу установки.  
  
## <a name="see-also"></a>См. также:  
 [Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [Советник по переходу SQL Server 2014 &#91;New&#93;](sql-server-2014-upgrade-advisor.md)  
  
  
