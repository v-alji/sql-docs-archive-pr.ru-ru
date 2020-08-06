---
title: Сборка мусора XTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 64ae91e5-b420-44b4-af1a-f8bca83d7f41
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 341a45c1c103f154672bb01a0648339562ee9750
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730581"
---
# <a name="xtp-garbage-collection"></a>Сборка мусора XTP
  Объект производительности XTP Garbage Collection содержит счетчики, относящиеся к механизму сборщика мусора XTP.  
  
 Эта таблица описывает счетчики **XTP garbage Collection** .  
  
|Счетчик|Описание|  
|-------------|-----------------|  
|**Число попыток сканирования «пыльных углов»/с (от сборщика мусора)**|Число повторных попыток сканирования из-за конфликтов записи при обработке «пыльных углов», выданное сборщиком мусора (в среднем), в секунду Это счетчик очень низкого уровня, не предназначенный для пользователей.|  
|**Рабочие элементы основной сборки мусора/с**|Число рабочих элементов в секунду, обрабатываемых основным потоком сборки мусора.|  
|**Рабочие элементы параллельной сборки мусора/с**|Число выполнений рабочего элемента сборки мусора параллельным потоком|  
|**Обработано строк/с**|Число строк, обрабатываемых сборщиком мусора (в среднем), в секунду.|  
|**Обработано строк/с (сначала в контейнере и удалено)**|Число строк, обработанных сборщиком мусора, которые сначала были в соответствующем хэш-контейнере, и могли быть удалены немедленно (в среднем), в секунду.|  
|**Обработано строк/с (сначала в контейнере)**|Число строк, обработанных сборщиком мусора, которые сначала были в соответствующем хэш-контейнере (в среднем), в секунду.|  
|**Обработано строк/с (отмеченных для удаления связи)**|Число строк, обработанных сборщиком мусора, которые уже отмечены для удаления связи (в среднем), в секунду.|  
|**Обработано строк/с (очистка не требуется)**|Число строк, обработанных сборщиком мусора, которые не потребуют очистки «пыльных углов» (в среднем), в секунду.|  
|**Очистка удаленных просроченных строк/с**|Число просроченных строк, удаленных при очистке «пыльных углов» (в среднем), в секунду.|  
|**Очистка затронутых просроченных строк/с**|Число просроченных строк, затронутых при очистке «пыльных углов» (в среднем), в секунду.|  
|**Очистка затронутых строк с истекающим сроком действия/с**|Число строк с истекающим сроком действия, затронутых при очистке «пыльных углов» (в среднем), в секунду.|  
|**Очистка затронутых строк/с**|Число строк, затронутых при очистке «пыльных углов» (в среднем), в секунду.|  
|**Начатые очистки/с**|Число начатых очисток «пыльных углов» (в среднем), в секунду.|  
  
## <a name="see-also"></a>См. также:  
 [Счетчики производительности XTP &#40;в памяти OLTP&#41;](../../integration-services/performance/performance-counters.md)  
  
  