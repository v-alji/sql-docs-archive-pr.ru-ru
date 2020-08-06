---
title: Вложенный триггер AFTER срабатывает, даже если вложенность триггера ОТКЛЮЧЕНа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, nested
- nested triggers option
- triggers [SQL Server], nested
ms.assetid: 94d72960-676e-40d9-81bc-08bffe778110
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f91c04e8d69880b451c1479e2907cd1910e8f9c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751715"
---
# <a name="nested-after-trigger-fires-even-when-trigger-nesting-is-off"></a><span data-ttu-id="34e1b-102">Вложенный триггер AFTER срабатывает даже в том случае, если вложенные триггеры отключены</span><span class="sxs-lookup"><span data-stu-id="34e1b-102">Nested AFTER trigger fires even when trigger nesting is OFF</span></span>
  <span data-ttu-id="34e1b-103">Советник по переходу обнаружил триггер AFTER, вложенный в триггер INSTEAD OF, который определен для одной или нескольких таблиц.</span><span class="sxs-lookup"><span data-stu-id="34e1b-103">Upgrade Advisor detected an AFTER trigger nested inside an INSTEAD OF trigger that is defined on one or more tables.</span></span> <span data-ttu-id="34e1b-104">Вложенные триггеры AFTER могут срабатывать, даже если параметр конфигурации сервера `nested triggers` установлен в 0.</span><span class="sxs-lookup"><span data-stu-id="34e1b-104">Nested AFTER triggers may fire even when the `nested triggers` server configuration option is set to 0.</span></span>  
  
## <a name="component"></a><span data-ttu-id="34e1b-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="34e1b-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="34e1b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="34e1b-106">Description</span></span>  
 <span data-ttu-id="34e1b-107">Первый триггер AFTER, вложенный в триггер INSTEAD OF, срабатывает, даже если параметру конфигурации сервера `nested triggers` присвоено значение 0.</span><span class="sxs-lookup"><span data-stu-id="34e1b-107">The first AFTER trigger nested inside an INSTEAD OF trigger fires even if the `nested triggers` server configuration option is set to 0.</span></span> <span data-ttu-id="34e1b-108">Однако при такой настройке последующие триггеры не срабатывают.</span><span class="sxs-lookup"><span data-stu-id="34e1b-108">However, under this setting, subsequent AFTER triggers do not fire.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="34e1b-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="34e1b-109">Corrective Action</span></span>  
 <span data-ttu-id="34e1b-110">Проверьте приложения на наличие вложенных триггеров, чтобы определить, соответствуют ли приложения бизнес-правилам в случае, если параметру конфигурации сервера `nested triggers` присвоено значение 0, и проведите соответствующие изменения.</span><span class="sxs-lookup"><span data-stu-id="34e1b-110">Review your applications for nested triggers to determine whether the applications still comply with your business rules with regard to this new behavior when the `nested triggers` server configuration option is set to 0, and then make appropriate modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e1b-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="34e1b-111">See Also</span></span>  
 <span data-ttu-id="34e1b-112">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="34e1b-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="34e1b-113">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="34e1b-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
