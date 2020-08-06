---
title: MSSQLSERVER_3151 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664247"
---
# <a name="mssqlserver_3151"></a>MSSQLSERVER_3151
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|3151|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|LDDB_MASTER_LOAD_FAILED|  
|Текст сообщения|Ошибка при восстановлении базы данных master. Завершение работы SQL Server. Проверьте журналы ошибок и перестройте базу данных master. Дополнительные сведения о перестроении базы данных master см. в электронной документации по SQL Server.|  
  
## <a name="explanation"></a>Объяснение  
 Это общее сообщение об ошибке, которое может означать разные проблемы с базой данных **master**.  
  
## <a name="user-action"></a>Действие пользователя  
 Проверьте журналы ошибок для получения дополнительных сведений. Чтобы создать работоспособную базу данных **master**, запустите файл Setup.exe с параметром REBUILDDATABASE. Дополнительные сведения см. в разделе "Как установить SQL Server из командной строки" в электронной документации по SQL Server.  
  
  
