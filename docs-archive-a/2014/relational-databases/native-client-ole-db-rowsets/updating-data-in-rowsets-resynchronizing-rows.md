---
title: Повторная синхронизация строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657086"
---
# <a name="resynchronizing-rows"></a>Повторная синхронизация строк
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает **интерфейс irowsetresynch** только для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] наборов строк, поддерживаемых курсорами. Интерфейс **IRowsetResynch** не предоставляется по требованию. Пользователь должен запросить этот интерфейс перед открытием набора строк.  
  
## <a name="see-also"></a>См. также:  
 [Обновление данных в наборах строк](updating-data-in-rowsets.md)  
  
  
