---
title: Создание шаблона на основе выполняемой трассировки (SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
ms.assetid: 25a3b845-affb-4b2a-a382-198a4bdd9ad1
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72744ce942cc49038129cf6064349e23c3e9a41d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727570"
---
# <a name="derive-a-template-from-a-running-trace-sql-server-profiler"></a><span data-ttu-id="cd9e0-102">создать шаблон на основе выполняемой трассировки (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="cd9e0-102">Derive a Template from a Running Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="cd9e0-103">В данном разделе описывается, как с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]создать шаблон на основе существующей трассировки.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-103">This topic describes how to create a trace template from an existing trace while it is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-derive-a-template-from-a-running-trace"></a><span data-ttu-id="cd9e0-104">Создание шаблона на основе выполняемой трассировки</span><span class="sxs-lookup"><span data-stu-id="cd9e0-104">To derive a template from a running trace</span></span>  
  
1.  <span data-ttu-id="cd9e0-105">При необходимости переключитесь в окно, содержащее трассировку.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-105">If necessary, switch to the window that contains the trace.</span></span>  
  
2.  <span data-ttu-id="cd9e0-106">В меню **Файл** укажите **Сохранить как**и выберите **Шаблон трассировки**.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-106">On the **File** menu, point to **Save As**, and then click **Trace Template**.</span></span>  
  
3.  <span data-ttu-id="cd9e0-107">Введите имя или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-107">Type a name or select one from the list.</span></span> <span data-ttu-id="cd9e0-108">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-108">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd9e0-109">При выборе существующего файла шаблона будет предложено подтвердить перезапись файла.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-109">If you select an existing template file, you are asked if you want to overwrite the file.</span></span> <span data-ttu-id="cd9e0-110">Можно выбрать только пользовательский шаблон.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-110">You can only select a user-defined template.</span></span> <span data-ttu-id="cd9e0-111">Системные шаблоны трассировки не могут быть перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="cd9e0-111">Predefined system trace templates cannot be overwritten.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9e0-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd9e0-112">See Also</span></span>  
 <span data-ttu-id="cd9e0-113">[Шаблоны и разрешения приложения SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="cd9e0-113">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="cd9e0-114">[Создание шаблона трассировки (приложение SQL Server Profiler)](create-a-trace-template-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="cd9e0-114">[Create a Trace Template &#40;SQL Server Profiler&#41;](create-a-trace-template-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="cd9e0-115">[Изменение шаблона трассировки (приложение SQL Server Profiler)](../../database-engine/modify-a-trace-template-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="cd9e0-115">[Modify a Trace Template &#40;SQL Server Profiler&#41;](../../database-engine/modify-a-trace-template-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="cd9e0-116">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="cd9e0-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
