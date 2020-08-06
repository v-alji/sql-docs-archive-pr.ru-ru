---
title: Свойство ExitCode (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657593"
---
# <a name="exitcode-property-sqlservice-class"></a>Свойство ExitCode (класс SqlService)
  Возвращает или задает код ошибки [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32, которая определяет проблемы, происходящие при запуске и остановке службы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a>Компоненты  
 *object*  
 Объект [класса SqlService](sqlservice-class.md) , представляющий службу.  
  
## <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение  
 Значение `uint32`, определяющее код завершения.  
  
## <a name="remarks"></a>Remarks  
 Это свойство имеет значение ERROR_SERVICE_SPECIFIC_ERROR (1066), если ошибка уникальна для службы, представленной этим классом. Во время выполнения и после нормального завершения работы служба присваивает этому параметру значение NO_ERROR.  
  
## <a name="see-also"></a>См. также:  
 [Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
