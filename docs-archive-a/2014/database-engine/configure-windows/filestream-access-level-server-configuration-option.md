---
title: Параметр конфигурации сервера "filestream access level" | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], access level
- filestream access level
ms.assetid: b88f6ff2-795e-4730-bfb8-dbc6a958f2ad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dfa43b8e6e1762e87dd9c2abbdf7a583963e196e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668465"
---
# <a name="filestream-access-level-server-configuration-option"></a>Параметр конфигурации сервера «уровень доступа файлового потока»
  Параметр файлового потока filestream_access_level используется для изменения уровня доступа к данным типа FILESTREAM для данного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!NOTE]  
>  Чтобы этот параметр вступил в силу, необходимо включить настройки администрирования Windows для FILESTREAM. Эти параметры можно включить при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
|Значение|Определение|  
|-----------|----------------|  
|0|Отключает поддержку FILESTREAM для данного экземпляра.|  
|1|Включает FILESTREAM для доступа с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] .|  
|2|Включает FILESTREAM для доступа с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] и потокового доступа Win32.|  
  
## <a name="see-also"></a>См. также:  
 [Настройка компонента Database Engine — Filestream](../../sql-server/install/database-engine-configuration-filestream.md)   
 [Включение и настройка FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md)  
  
  
