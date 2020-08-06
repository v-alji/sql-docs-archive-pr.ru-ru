---
title: WITH CHECK OPTION не поддерживается в представлениях, содержащих TOP в режиме совместимости 90 или более поздней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TOP clause
- WITH CHECK OPTION clause
ms.assetid: 1b9581d0-bad9-43e0-b8fc-f32d8a8a04ca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee7775c875e33f104341a1da39f5fe6c9326f284
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659098"
---
# <a name="with-check-option-is-not-supported-in-views-that-contain-top-in-90-or-later-compatibility-modes"></a><span data-ttu-id="60d54-102">Предложение WITH CHECK OPTION не поддерживается в представлениях, содержащих предложение TOP, в режиме совместимости 90 и выше</span><span class="sxs-lookup"><span data-stu-id="60d54-102">WITH CHECK OPTION is not supported in views that contain TOP in 90 or later compatibility modes</span></span>
  <span data-ttu-id="60d54-103">Помощник по обновлению обнаружил представление, в котором присутствует предложение WITH CHECK OPTION и предложение TOP в инструкции SELECT представления или в представлении, на которое оно ссылается.</span><span class="sxs-lookup"><span data-stu-id="60d54-103">Upgrade Advisor detected a view that uses the WITH CHECK OPTION and a TOP clause in the SELECT statement of the view or in a referenced view.</span></span> <span data-ttu-id="60d54-104">В режиме совместимости 80 и ниже представления, определенные таким образом, ошибочно позволяют изменять данные через представление и могут выдавать неточные результаты.</span><span class="sxs-lookup"><span data-stu-id="60d54-104">Views defined this way incorrectly allow data to be modified through the view and may produce inaccurate results when the database compatibility mode is set to 80 and earlier.</span></span> <span data-ttu-id="60d54-105">В режиме совместимости 90 и выше данные не могут вставляться или обновляться через представления с предложением WITH CHECK OPTION, если в этом представлении или представлении, на которое оно ссылается, присутствует предложение TOP.</span><span class="sxs-lookup"><span data-stu-id="60d54-105">Data cannot be inserted or updated through a view that uses WITH CHECK OPTION when the view or a referenced view uses the TOP clause and the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="60d54-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="60d54-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="60d54-107">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="60d54-107">Corrective Action</span></span>  
 <span data-ttu-id="60d54-108">При обновлении пользовательские базы данных сохраняют свой режим совместимости.</span><span class="sxs-lookup"><span data-stu-id="60d54-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="60d54-109">Прежде чем устанавливать режим совместимости базы данных в значение 100 и выше, следует внести изменения в представления, использующие одновременно инструкцию WITH CHECK OPTION и предложение TOP, если необходимо выполнять изменение данных через представление.</span><span class="sxs-lookup"><span data-stu-id="60d54-109">Before you change the database compatibility mode to 100 or later, modify views that use both WITH CHECK OPTION and TOP if data modification through the view is required.</span></span> <span data-ttu-id="60d54-110">Дополнительные сведения см. в разделе [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60d54-110">For more information, see [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d54-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="60d54-111">See Also</span></span>  
 <span data-ttu-id="60d54-112">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="60d54-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="60d54-113">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="60d54-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
