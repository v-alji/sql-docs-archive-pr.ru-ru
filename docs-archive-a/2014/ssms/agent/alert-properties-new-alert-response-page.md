---
title: Свойства предупреждения — Создание предупреждения (страница "ответ") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.response.f1
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 34e7f11ff3210ec4fc1835751bc35b140d3fa0ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737490"
---
# <a name="alert-properties-new-alert-response-page"></a>Свойства предупреждения — Создание предупреждения (страница «ответ»)
  Используйте эту страницу, чтобы указать задание, которое требуется запустить, и получить список операторов, которые должны получать уведомления в ответ на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждение агента.  
  
## <a name="options"></a>Варианты  
 **Выполнить задание**  
 Включает параметры **Список заданий**, **Создать задание** и **Просмотреть задание** .  
  
 **Создать задание**  
 Откройте диалоговое окно **Создать задание** . Эта кнопка недоступна, если не установлен флажок **Выполнить задание** .  
  
 **Просмотр задания**  
 Просмотреть или изменить выбранное задание. Этот параметр недоступен, если не установлен флажок **Выполнить задание** .  
  
 **Уведомить операторов**  
 Включает элементы управления, которые используются для добавления, удаления и изменения операторов.  
  
 **Список операторов**  
 Перечисляет операторов, которые должны получать уведомления при появлении предупреждения. Чтобы указать метод уведомления, установите флажок **Электронная почта**, **Пейджер**или **Net send** , отображаемый после имени оператора. Этот параметр недоступен, если флажок **Уведомить операторов** не установлен.  
  
 **Электронных**  
 Использовать электронную почту, чтобы уведомить оператора.  
  
 **Пейджер**  
 Использовать адрес электронной почты пейджера, чтобы уведомить оператора.  
  
 **NET SEND**  
 Использовать команду **net send** , чтобы уведомить оператора.  
  
 **Оператор New**  
 Отображает диалоговое окно **Создать оператора** , которое используется для создания новых операторов.  
  
 **Просмотр оператора**  
 Отображается диалоговое окно **Свойства** для текущего выбранного оператора. Свойства операторов можно просматривать и изменять в диалоговом окне **Свойства оператора**.  
  
## <a name="see-also"></a>См. также:  
 [Alerts](alerts.md)   
 [Создание предупреждения с использованием уровня серьезности](create-an-alert-using-severity-level.md)   
 [Alerts](alerts.md)   
 [Изменение оповещения](edit-an-alert.md)   
 [Удаление предупреждения](delete-an-alert.md)  
  
  