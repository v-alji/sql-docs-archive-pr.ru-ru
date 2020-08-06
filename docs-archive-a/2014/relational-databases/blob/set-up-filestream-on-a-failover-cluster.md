---
title: Настойка FILESTREAM в отказоустойчивом кластере | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728362"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a>Установка FILESTREAM в отказоустойчивом кластере
  В этом разделе описано включение FILESTREAM в отказоустойчивом кластере. Перед началом этой процедуры необходимо ознакомиться с принципами работы [отказоустойчивой кластеризации](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) и включить FILESTREAM. Сведения о включении FILESTREAM см. в разделе [Включение и настройка FILESTREAM](enable-and-configure-filestream.md).  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a>Установка FILESTREAM в отказоустойчивом кластере  
  
1.  Установите основной узел отказоустойчивого кластера.  
  
     После завершения программы установки включите FILESTREAM на основном узле с помощью **диспетчера конфигурации SQL Server**. Тем самым включаются параметры, требующие права доступа администратора Windows. Если нужен удаленный доступ, установите флажок **Разрешить удаленным клиентам потоковый доступ к данным FILESTREAM**. Этим создается кластерный ресурс общей папки.  
  
2.  Установите пассивный узел.  
  
     После завершения программы установки включите FILESTREAM на пассивном узле с помощью **диспетчера конфигурации SQL Server**. Имя указываемого **общего ресурса Windows** должно быть одинаковым для всех узлов кластера.  
  
3.  Чтобы установить дополнительные пассивные узлы, повторите шаг 2.  
  
4.  После добавления всех узлов завершите процесс, выполнив хранимую процедуру sp_configure на каждом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
5.  Чтобы в любое время добавить и задействовать дополнительные узлы кластера, можно повторить шаги 2, 3 и 4.  
  
## <a name="see-also"></a>См. также:  
 [Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [Создание отказоустойчивого кластера SQL Server (программа установки)](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md)   
 [Удаление экземпляра отказоустойчивого кластера SQL Server (программа установки)](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md)   
 [Добавление или удаление узлов отказоустойчивого кластера SQL Server (программа установки)](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  
