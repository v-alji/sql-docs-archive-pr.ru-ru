---
title: символ 0xFFFF не является допустимым идентификатором объекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- 0xFFFF character [SQL Server]
ms.assetid: b2c9c8cf-9194-45e0-be6b-2d5ec52e8153
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4594c1cca0fc183100d927842cc2b533694bf90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659263"
---
# <a name="0xffff-character-is-not-valid-as-an-object-identifier"></a><span data-ttu-id="17d6f-102">Символ с кодом 0xFFFF не является допустимым идентификатором объекта</span><span class="sxs-lookup"><span data-stu-id="17d6f-102">0xFFFF character is not valid as an object identifier</span></span>
  <span data-ttu-id="17d6f-103">Помощник по обновлению обнаружил символ 0xFFFF в идентификаторе объекта.</span><span class="sxs-lookup"><span data-stu-id="17d6f-103">Upgrade Advisor has detected the 0xFFFF character in an object identifier.</span></span> <span data-ttu-id="17d6f-104">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях такие объекты, как базы данных, таблицы и столбцы, идентификаторы которых содержат этот символ, не могут быть переименованы или указаны по ссылке, если для режима совместимости базы данных установлено значение 90 или больше.</span><span class="sxs-lookup"><span data-stu-id="17d6f-104">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, objects such as databases, tables, and columns that contain this character in their identifiers cannot be referenced or renamed when the database compatibility mode is set to 90 or later.</span></span> <span data-ttu-id="17d6f-105">При обновлении до [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] пользовательские базы данных сохраняют свой режим совместимости.</span><span class="sxs-lookup"><span data-stu-id="17d6f-105">When you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], user databases maintain their compatibility mode.</span></span> <span data-ttu-id="17d6f-106">Прежде чем задать для режима совместимости значение 90 или выше, переименуйте объект, который содержит символ 0xFFFF.</span><span class="sxs-lookup"><span data-stu-id="17d6f-106">Before you change the database compatibility mode to 90 or later, rename the object that contains the 0xFFFF character.</span></span>  
  
 <span data-ttu-id="17d6f-107">Дополнительные сведения см. в разделе «Идентификаторы» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17d6f-107">For more information about identifiers, see "Identifiers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="17d6f-108">Дополнительные сведения о режимах совместимости базы данных см. в разделе «sp_dbcmptlevel» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17d6f-108">For more information about database compatibility modes, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="17d6f-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="17d6f-109">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="17d6f-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="17d6f-110">See Also</span></span>  
 <span data-ttu-id="17d6f-111">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="17d6f-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="17d6f-112">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="17d6f-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
