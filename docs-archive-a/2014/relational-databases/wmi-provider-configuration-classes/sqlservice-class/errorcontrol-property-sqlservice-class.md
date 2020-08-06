---
title: Свойство ErrorControl (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738105"
---
# <a name="errorcontrol-property-sqlservice-class"></a>Свойство ErrorControl (класс SqlService)
  Возвращает или задает серьезность ошибки, если служба не запускается во время запуска системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a>Компоненты  
 *object*  
 Объект [класса SqlService](sqlservice-class.md) , представляющий службу.  
  
## <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение  
 Строковое значение, определяющее серьезность ошибки, если служба не запускается во время запуска системы. В следующей таблице приводятся возможные значения.  
  
 Игнорировать  
 Пользователь не получает уведомление.  
  
 Норм.  
 Пользователь получает уведомление.  
  
 Severe  
 Система перезапускается в последней известной рабочей конфигурации.  
  
 Критически важно  
 Попытка перезапустить систему в рабочей конфигурации.  
  
 Неизвестно  
 Серьезность ошибки неизвестна.  
  
## <a name="remarks"></a>Remarks  
 Значение задает действие, предпринимаемое программой запуска при возникновении ошибки. Все ошибки записываются в журнал системой компьютера.  
  
## <a name="see-also"></a>См. также:  
 [Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
