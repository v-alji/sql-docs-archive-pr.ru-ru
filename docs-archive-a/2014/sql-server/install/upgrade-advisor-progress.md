---
title: Ход выполнения советника по переходу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], analysis progress status
- analyzing system [Upgrade Advisor], progress information
- SQL Server Upgrade Advisor, analysis progress status
- monitoring analysis progress
- progress information [Upgrade Advisor]
- status information [Upgrade Advisor]
ms.assetid: a9e3d1c8-d492-4beb-93c7-f1bc40d4a910
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b504b8f1c8392ad2cf55837dc65bbb2f019d6f48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659125"
---
# <a name="upgrade-advisor-progress"></a><span data-ttu-id="c9bc7-102">Ход выполнения помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="c9bc7-102">Upgrade Advisor Progress</span></span>
  <span data-ttu-id="c9bc7-103">Анализ помощника по обновлению начинается с запуска выделенного анализатора, производящего анализ каждого выбранного компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9bc7-103">Upgrade Advisor analysis starts with a dedicated analyzer that performs an analysis of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that you selected.</span></span> <span data-ttu-id="c9bc7-104">По мере анализа компонентов в диалоговом окне **ход** выполнения отображается ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-104">As components are analyzed, progress is reported in the **Progress** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9bc7-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="c9bc7-105">Options</span></span>  
 <span data-ttu-id="c9bc7-106">**Действие**</span><span class="sxs-lookup"><span data-stu-id="c9bc7-106">**Action**</span></span>  
 <span data-ttu-id="c9bc7-107">Указывает выбранный для анализа компонент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9bc7-107">Specifies the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that is selected for analysis.</span></span>  
  
 <span data-ttu-id="c9bc7-108">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c9bc7-108">**Status**</span></span>  
 <span data-ttu-id="c9bc7-109">Отображает значение состояния, возвращенное интерфейсом выполнения компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9bc7-109">Displays the status value returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component progress interface.</span></span>  
  
 <span data-ttu-id="c9bc7-110">**Message**</span><span class="sxs-lookup"><span data-stu-id="c9bc7-110">**Message**</span></span>  
 <span data-ttu-id="c9bc7-111">Отображает сообщения об ошибке, сбое или успешном завершении, возвращенные каждым отдельным анализатором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9bc7-111">Displays error, failure, or success messages returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] individual analyzer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9bc7-112">Если процесс анализа занял слишком много времени, можно остановить его, закрыв мастер анализа помощника по обновлению и перезапустив его.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-112">If the analysis is taking too long, you can stop the analysis, exit the Upgrade Advisor Analysis Wizard, and then rerun the wizard.</span></span> <span data-ttu-id="c9bc7-113">Чтобы сократить время анализа, выберите меньше компонентов для просмотра.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-113">To reduce analysis time, select fewer components to scan.</span></span>  
  
 <span data-ttu-id="c9bc7-114">После завершения анализа отчет будет записан в файл.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-114">When analysis is complete, the report is written to a file.</span></span> <span data-ttu-id="c9bc7-115">Чтобы просмотреть отчет, нажмите кнопку **запустить отчет** , чтобы запустить средство просмотра отчетов с этой страницы.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-115">You can view the report by clicking **Launch Report** to launch the report viewer from this page.</span></span> <span data-ttu-id="c9bc7-116">Если вы хотите просмотреть отчет позже, можно открыть **средство просмотра отчетов помощника по обновлению** на начальной странице помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-116">If you want to view the report later, you can open the **Upgrade Advisor Report Viewer** from the Upgrade Advisor start page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9bc7-117">Предыдущие отчеты сохраняются при каждом анализе сервера.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-117">Previous reports are saved every time you analyze a server.</span></span> <span data-ttu-id="c9bc7-118">При сохранении отчетов в качестве имени файла используется отметка времени.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-118">The reports are saved using the timestamp for the file name.</span></span> <span data-ttu-id="c9bc7-119">Средство просмотра отчетов отображает пять последних сохраненных отчетов.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-119">The report viewer displays the latest five saved reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bc7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9bc7-120">See Also</span></span>  
 <span data-ttu-id="c9bc7-121">[Руководство. Запуск помощника по обновлению](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="c9bc7-121">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="c9bc7-122">[Как запустить мастер анализа помощника по обновлению](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="c9bc7-122">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="c9bc7-123">[Компоненты SQL Server](../../../2014/sql-server/install/sql-server-components.md) </span><span class="sxs-lookup"><span data-stu-id="c9bc7-123">[SQL Server Components](../../../2014/sql-server/install/sql-server-components.md) </span></span>  
 <span data-ttu-id="c9bc7-124">[Справочник по пользовательскому интерфейсу помощника по обновлению](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c9bc7-124">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 [<span data-ttu-id="c9bc7-125">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="c9bc7-125">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
