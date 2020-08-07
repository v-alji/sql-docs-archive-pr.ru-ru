---
title: Возврат результатов из задачи "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], status information
- ExecutionValue property
- status information [Integration Services]
- TaskResult property
- SSIS Script task, status information
ms.assetid: ac06805b-c2db-44bd-af5c-5a0debe36dd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bef3e93644377f715b5ad24e0a53df053197a03a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731886"
---
# <a name="returning-results-from-the-script-task"></a><span data-ttu-id="38c07-102">Возврат результатов из задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="38c07-102">Returning Results from the Script Task</span></span>
  <span data-ttu-id="38c07-103">Задача «Скрипт» использует свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> и дополнительное свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> для возвращения сведений о состоянии в среду выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], которые могут быть использованы для определения пути рабочего процесса по завершении задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="38c07-103">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> and the optional <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> properties to return status information to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime that can be used to determine the path of the workflow after the Script task has finished.</span></span>  
  
## <a name="taskresult"></a><span data-ttu-id="38c07-104">TaskResult</span><span class="sxs-lookup"><span data-stu-id="38c07-104">TaskResult</span></span>  
 <span data-ttu-id="38c07-105">Свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> сообщает о том, успешным или неуспешным было выполнение задачи.</span><span class="sxs-lookup"><span data-stu-id="38c07-105">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> property reports whether the task succeeded or failed.</span></span> <span data-ttu-id="38c07-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="38c07-106">For example:</span></span>  
  
 `Dts.TaskResult = ScriptResults.Success`  
  
## <a name="executionvalue"></a><span data-ttu-id="38c07-107">ExecutionValue</span><span class="sxs-lookup"><span data-stu-id="38c07-107">ExecutionValue</span></span>  
 <span data-ttu-id="38c07-108">При необходимости свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> возвращает определяемый пользователем объект, который содержит количественные или иные дополнительные сведения об успешном или неуспешном выполнении задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="38c07-108">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property optionally returns a user-defined object that quantifies or provides more information about the success or failure of the Script task.</span></span> <span data-ttu-id="38c07-109">Например, задача «FTP» использует свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> для возврата числа переданных файлов.</span><span class="sxs-lookup"><span data-stu-id="38c07-109">For example, the FTP task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property to return the number of files transferred.</span></span> <span data-ttu-id="38c07-110">Задача «Выполнение SQL» возвращает число строк, затронутых при выполнении задачи.</span><span class="sxs-lookup"><span data-stu-id="38c07-110">The Execute SQL task returns the number of rows affected by the task.</span></span> <span data-ttu-id="38c07-111">Свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> может также использоваться для определения пути рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="38c07-111">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> can also be used to determine the path of the workflow.</span></span> <span data-ttu-id="38c07-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="38c07-112">For example:</span></span>  
  
 `Dim rowsAffected as Integer`  
  
 `...`  
  
 `rowsAffected = 1000`  
  
 `Dts.ExecutionValue = rowsAffected`  
  
<span data-ttu-id="38c07-113">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="38c07-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="38c07-114">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="38c07-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="38c07-115">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="38c07-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="38c07-116">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="38c07-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
