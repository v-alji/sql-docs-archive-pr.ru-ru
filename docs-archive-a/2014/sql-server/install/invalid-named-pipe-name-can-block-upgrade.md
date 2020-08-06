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
# <a name="invalid-named-pipe-name-can-block-upgrade"></a><span data-ttu-id="a1092-102">Неверное имя именованного канала может помешать обновлению</span><span class="sxs-lookup"><span data-stu-id="a1092-102">Invalid named pipe name can block upgrade</span></span>
  <span data-ttu-id="a1092-103">Обновление завершается ошибкой, если протокол именованных каналов настроен неправильно.</span><span class="sxs-lookup"><span data-stu-id="a1092-103">Upgrade fails if the named pipes protocol is incorrectly configured.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a1092-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="a1092-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a1092-105">Описание</span><span class="sxs-lookup"><span data-stu-id="a1092-105">Description</span></span>  
 <span data-ttu-id="a1092-106">Во время обновления программа установки запускает [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] экземпляр с поддержкой общей памяти, именованным каналом, который принимает только локальные соединения.</span><span class="sxs-lookup"><span data-stu-id="a1092-106">During upgrade, the Setup program starts the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] instance with shared memory support, a named pipe that only accepts local connections.</span></span> <span data-ttu-id="a1092-107">Если имя канала, указанное на сервере, не является пустым, оно должно начинаться с строки " \\ \\ .\pipe \\ ", которая должна быть допустимой.</span><span class="sxs-lookup"><span data-stu-id="a1092-107">If the pipe name specified on the server is not blank, it must begin with the string "\\\\.\pipe\\" to be valid.</span></span> <span data-ttu-id="a1092-108">Если задано недопустимое имя канала, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] не запустится и установка завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a1092-108">If the pipe name is not valid, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will not start, and setup will fail.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a1092-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="a1092-109">Corrective Action</span></span>  
 <span data-ttu-id="a1092-110">Используйте \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] служебную программу Network\*\* для указания допустимого имени канала, а затем запустите программу установки.</span><span class="sxs-lookup"><span data-stu-id="a1092-110">Use the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Utility** to supply a valid pipe name, and then run Setup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1092-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1092-111">See Also</span></span>  
 <span data-ttu-id="a1092-112">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a1092-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a1092-113">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="a1092-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
