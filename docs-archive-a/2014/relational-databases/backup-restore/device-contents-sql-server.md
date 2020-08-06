---
title: Содержимое устройства (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658848"
---
# <a name="device-contents-sql-server"></a>Содержимое устройства (SQL Server)
  При помощи этого диалогового окна можно посмотреть сведения о резервном копировании. Сюда входят сведения об устройстве, носителе, наборе носителей, а также резервном наборе (наборах) данных.  
  
 **Использование среды SQL Server Management Studio для просмотра содержимого устройства резервного копирования**  
  
-   [Просмотр содержимого ленты или файла резервной копии (SQL Server)](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a>Параметры  
 **Носитель**  
 Диск или набор носителей на магнитных лентах, где хранятся резервные данные.  
  
 **Порядок носителей**  
 Список содержит порядковый номер носителя, порядковый номер семейства и идентификатор зеркального сервера, если такой существует. Для каждого физического носителя данных резервных копий указан порядковый номер, отражающий поcледовательность, в которой использовались носители. Первый носитель данных резервных копий обозначен цифрой 1, второй (первая дополнительная лента) обозначен цифрой 2 и т. д. При восстановлении из резервного набора данных наличие порядковых номеров носителей позволяет гарантировать, что оператор, выполняющий восстановление, подключает носители в правильном порядке.  
  
 **Создан**  
 Показывает дату записи носителя.  
  
 **Набор носителей**  
 Набор носителей представляет собой коллекцию носителей резервной копии, записанной в процессе одной или более операций резервного копирования с использованием постоянного числа устройств резервного копирования.  
  
 **имя**;  
 Отображает имя набора носителей.  
  
 **Описание**  
 Отображает набор носителей описания.  
  
 **Счетчик семейства носителей**  
 Отображает счетчик семейства носителей. Каждый набор носителей представляет собой коллекцию из одного или нескольких семейств носителей. Все выходные данные для отдельно взятого устройства резервного копирования (или группы зеркальных устройств резервного копирования) образуют одно семейство носителей. Каждый набор носителей содержит одно семейство носителей на каждое отдельное устройство (или группу зеркальных устройств резервного копирования). Например, если набор носителей использует два незеркальных устройства резервного копирования, то в нем содержатся два семейства носителей.  
  
 **Резервные наборы данных**  
 Показывает сведения об одном или нескольких резервных наборах данных, содержащихся на носителе. Резервный набор данных представляет собой результат успешного завершения операции резервного копирования, чье содержимое распределяется на носителе в наборе устройств резервного копирования.  
  
|Заголовок|Значения|  
|------------|------------|  
|**имя**;|Имя резервного набора данных.|  
|**Тип**|Тип выполняемого резервного копирования: полное, разностное или резервное копирование журнала транзакций.|  
|**Компонент**|Компонент, сохраненный в резервной копии: база данных, файл или *\<blank>* (для журналов транзакций).|  
|**Server**|Имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , выполнившего операцию резервного копирования.|  
|**База данных**|Имя базы данных, резервная копия которой была сделана.|  
|**Положение**|Расположение резервного набора данных в томе.|  
|**Дата**|Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.|  
|**Размер**|Размер резервного набора данных в байтах.|  
|**Имя пользователя**|Имя пользователя, выполнившего операцию резервного копирования.|  
|**Истечение срока**|Дата и время истечения срока действия резервного набора данных.|  
  
## <a name="see-also"></a>См. также:  
 [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  