---
title: SERVERPROPERTY возвращает правильный результат для свойства LCID в SQL Server 2005 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SERVERPROPERTY function
ms.assetid: 833a2fc9-b480-4697-aa7b-9677e78ee0b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebb125a86e6e30f2c3638004593da7657f02f1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732290"
---
# <a name="serverproperty-returns-correct-result-for-lcid-property-in-sql-server-2005"></a><span data-ttu-id="6eed7-102">В SQL Server 2005 функция SERVERPROPERTY возвращает правильный результат для свойства LCID</span><span class="sxs-lookup"><span data-stu-id="6eed7-102">SERVERPROPERTY returns correct result for LCID property in SQL Server 2005</span></span>
  <span data-ttu-id="6eed7-103">При выполнении функции SERVERPROPERTY('LCID') на серверах с параметрами двоичной сортировки эта функция возвращает значение LCID, соответствующее параметрам сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="6eed7-103">When SERVERPROPERTY('LCID') is run on binary collation servers, the function returns the Windows locale identifier (LCID) that corresponds to the collation of the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6eed7-104">Для пакетных файлов и файлов трассировки, использующих функцию SERVERPROPERTY ('LCID') и запускаемых на других экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], помощник по обновлению обнаружит это изменение в поведении, только если параметры сортировки у других экземпляров и текущего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] совпадают.</span><span class="sxs-lookup"><span data-stu-id="6eed7-104">For batch and trace files that contain references to SERVERPROPERTY ('LCID') and are run on other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Upgrade Advisor will detect this behavior change only if the other instances have the same collation as the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6eed7-105">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="6eed7-105">Corrective Action</span></span>  
 <span data-ttu-id="6eed7-106">Следует изменить приложения, чтобы они ожидали от функции SERVERPROPERTY('LCID') возвращения кода языка Windows, соответствующего параметрам сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="6eed7-106">Modify applications to expect SERVERPROPERTY('LCID') to return the Windows LCID that corresponds to the collation of the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eed7-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="6eed7-107">See Also</span></span>  
 <span data-ttu-id="6eed7-108">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6eed7-108">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6eed7-109">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="6eed7-109">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
