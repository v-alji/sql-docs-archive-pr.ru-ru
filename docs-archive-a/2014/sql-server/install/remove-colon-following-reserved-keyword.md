---
title: Удалить двоеточие после зарезервированного ключевого слова | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reserved keywords
ms.assetid: 4f23f7e4-7b4d-4e19-86c9-7527bb8b107d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fc6882439338509a3c716129d9504f209ab1e555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751711"
---
# <a name="remove-colon-following-reserved-keyword"></a><span data-ttu-id="dc477-102">Удалите двоеточие после зарезервированного ключевого слова</span><span class="sxs-lookup"><span data-stu-id="dc477-102">Remove colon following reserved keyword</span></span>
  <span data-ttu-id="dc477-103">Помощник по обновлению обнаружил скрипт, содержащий символ двоеточия (:) после зарезервированного слова.</span><span class="sxs-lookup"><span data-stu-id="dc477-103">The Upgrade Advisor detected a script that contains a colon (:) following a reserved keyword.</span></span> <span data-ttu-id="dc477-104">В предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]такие синтаксические конструкции пропускаются, а инструкции успешно выполняются.</span><span class="sxs-lookup"><span data-stu-id="dc477-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this syntax is ignored and the statements execute successfully.</span></span> <span data-ttu-id="dc477-105">Теперь такой синтаксис приводит к ошибке при выполнении инструкции, если уровень совместимости базы данных установлен в значение 100 или выше.</span><span class="sxs-lookup"><span data-stu-id="dc477-105">Now, this syntax causes the statement to fail when the database compatibility mode is set to 100 or later.</span></span>  
  
 <span data-ttu-id="dc477-106">Пользовательские базы данных сохраняют свой режим совместимости.</span><span class="sxs-lookup"><span data-stu-id="dc477-106">User databases maintain their compatibility mode.</span></span>  
  
## <a name="component"></a><span data-ttu-id="dc477-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="dc477-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="dc477-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="dc477-108">Corrective Action</span></span>  
 <span data-ttu-id="dc477-109">Прежде чем установить для уровня совместимости базы данных значение 100 или более высокое, следует изменить скрипты, убрав двоеточия после зарезервированных ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="dc477-109">Before you change the database compatibility mode to 100 or later, modify your scripts by removing colons that follow reserved keywords.</span></span> <span data-ttu-id="dc477-110">Дополнительные сведения см. в разделе «sp_dbcmptlevel» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc477-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc477-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="dc477-111">See Also</span></span>  
 <span data-ttu-id="dc477-112">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="dc477-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="dc477-113">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="dc477-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
