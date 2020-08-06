---
title: Изменение инструкций UPDATETEXT, считывающих и записывающих данные в большие двоичные объекты (BLOB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- UPDATETEXT statement
- text [SQL Server], UPDATETEXT statements
ms.assetid: b85da6a7-42f6-4707-a25e-3ded8958b94f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 061e7bad0bae5a74d103406265ad79195f79f7db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659184"
---
# <a name="modify-updatetext-statements-that-read-and-write-to-binary-large-objects-blobs"></a><span data-ttu-id="7dfaa-102">Внесите изменения в инструкции UPDATETEXT, которые считывают и записывают большие двоичные объекты</span><span class="sxs-lookup"><span data-stu-id="7dfaa-102">Modify UPDATETEXT statements that read and write to binary large objects (BLOBs)</span></span>
  <span data-ttu-id="7dfaa-103">Помощник по обновлению обнаружил инструкции UPDATETEXT, которые читают и записывают одни и те же большие двоичные объекты (BLOB) с использованием одного и того же текстового указателя.</span><span class="sxs-lookup"><span data-stu-id="7dfaa-103">Upgrade Advisor detected UPDATETEXT statements that read and write to the same binary large objects (BLOB) by using the same text pointer.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="7dfaa-104">не поддерживает подобное использование текстовых указателей.</span><span class="sxs-lookup"><span data-stu-id="7dfaa-104">does not support the use of text pointers in this manner.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7dfaa-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="7dfaa-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="7dfaa-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="7dfaa-106">Corrective Action</span></span>  
 <span data-ttu-id="7dfaa-107">Скопируйте большой двоичный объект во временную таблицу или табличную переменную, а затем присвойте это значение исходному столбцу.</span><span class="sxs-lookup"><span data-stu-id="7dfaa-107">Copy the BLOB to a temporary table or to a table variable, and then assign the value back to the original column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfaa-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="7dfaa-108">See Also</span></span>  
 <span data-ttu-id="7dfaa-109">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7dfaa-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="7dfaa-110">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="7dfaa-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
