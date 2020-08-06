---
title: Если строки не поддерживаются в инструкциях CREATE STATISTICS в режиме совместимости 90 или более поздней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH ROWS in CREATE STATISTICS statement
ms.assetid: 197b2ecf-a1a3-4a3a-a523-a0ee919c1dde
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d28a05e7cd025e213e2cebdce9d582a9df446fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659097"
---
# <a name="with-rows-is-not-supported-in-create-statistics-statements-in-the-compatibility-mode-of-90-or-later"></a><span data-ttu-id="21620-102">Параметр WITH ROWS не поддерживается в инструкциях CREATE STATISTICS в режиме совместимости 90 и выше</span><span class="sxs-lookup"><span data-stu-id="21620-102">WITH ROWS is not supported in CREATE STATISTICS statements in the compatibility mode of 90 or later</span></span>
  <span data-ttu-id="21620-103">Параметр WITH ROWS в инструкциях CREATE STATISTICS не поддерживается, если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает в режиме совместимости 90 и более.</span><span class="sxs-lookup"><span data-stu-id="21620-103">Specifying WITH ROWS in CREATE STATISTICS statements is not supported when you run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set to the compatibility mode of 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="21620-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="21620-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="21620-105">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="21620-105">Corrective Action</span></span>  
 <span data-ttu-id="21620-106">Измените инструкции CREATE STATISTICS, которые включают в себя строки, указав с помощью строк с ВЫБОРкой *чисел* , или указав другие параметры, которые соответствуют задокументированному синтаксису.</span><span class="sxs-lookup"><span data-stu-id="21620-106">Modify CREATE STATISTICS statements that include WITH ROWS by specifying WITH SAMPLE *number* ROWS, or by specifying other options that comply with the documented syntax.</span></span> <span data-ttu-id="21620-107">Дополнительные сведения см. в разделе «CREATE STATISTICS (Transact-SQL)» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="21620-107">For more information, see the topic "CREATE STATISTICS (Transact-SQL) in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21620-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="21620-108">See Also</span></span>  
 <span data-ttu-id="21620-109">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="21620-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="21620-110">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="21620-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
