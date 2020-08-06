---
title: Удалите вызовы нерекомендуемой команды DBCC CONCURRENCYVIOLATION | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2cc9f6ff-de36-4e94-bd04-59f5c45c4911
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cde04ebfc2ea9996d1c9ed233123e5b66f6e81fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737544"
---
# <a name="remove-calls-to-the-deprecated-dbcc-concurrencyviolation-command"></a><span data-ttu-id="9c432-102">Удаление вызовов устаревшей команды DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="9c432-102">Remove calls to the deprecated DBCC CONCURRENCYVIOLATION command</span></span>
  <span data-ttu-id="9c432-103">Помощник по обновлению обнаружил использование команды DBCC CONCURRENCYVIOLATION.</span><span class="sxs-lookup"><span data-stu-id="9c432-103">Upgrade Advisor detected the use of the DBCC CONCURRENCYVIOLATION command.</span></span> <span data-ttu-id="9c432-104">Эта команда больше не доступна.</span><span class="sxs-lookup"><span data-stu-id="9c432-104">This command is no longer available.</span></span> <span data-ttu-id="9c432-105">При выполнении данной команды возвращается ошибка 2526.</span><span class="sxs-lookup"><span data-stu-id="9c432-105">Executing this command returns error 2526.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9c432-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="9c432-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9c432-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9c432-107">Description</span></span>  
 <span data-ttu-id="9c432-108">Регулятор рабочей нагрузки не входит ни в одну из последних версий выпуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . В связи с этим данная команда была удалена.</span><span class="sxs-lookup"><span data-stu-id="9c432-108">No recent version of edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes a workload governor; therefore the command has been removed.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9c432-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="9c432-109">Corrective Action</span></span>  
 <span data-ttu-id="9c432-110">Внесите изменения в приложения и скрипты, удалив ссылки на эту устаревшую команду.</span><span class="sxs-lookup"><span data-stu-id="9c432-110">Update applications and scripts to remove references to this deprecated command.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9c432-111">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="9c432-111">External Resources</span></span>  
  
