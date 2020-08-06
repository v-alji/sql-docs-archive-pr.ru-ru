---
title: Запуск Windows PowerShell из среды SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658864"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a><span data-ttu-id="377ee-102">Запуск Windows PowerShell из среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="377ee-102">Run Windows PowerShell from SQL Server Management Studio</span></span>
  <span data-ttu-id="377ee-103">Можно запускать сеансы Windows PowerShell из **обозревателя объектов** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="377ee-103">You can start Windows PowerShell sessions from **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]<span data-ttu-id="377ee-104">запускает Windows PowerShell, загружает `sqlps` модуль и задает контекст пути для связанного узла в дереве **обозревателя объектов** .</span><span class="sxs-lookup"><span data-stu-id="377ee-104">launches Windows PowerShell, loads the `sqlps` module, and sets the path context to the associated node in the **Object Explorer** tree.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="377ee-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="377ee-105">Before You Begin</span></span>  
 <span data-ttu-id="377ee-106">При указании запуска PowerShell для объекта в **обозревателе объектов** [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] запускается сеанс Windows PowerShell, в котором были [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] загружены и зарегистрированы оснастки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="377ee-106">When you specify running PowerShell for an object in **Object Explorer**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starts a Windows PowerShell session in which the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins have been loaded and registered.</span></span> <span data-ttu-id="377ee-107">Путем для сеанса становится расположение объекта, выбранного правой кнопкой мыши в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="377ee-107">The path for the session is preset to the location of the object you right clicked in Object Explorer.</span></span> <span data-ttu-id="377ee-108">Например, если щелкнуть правой кнопкой мыши объект базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] в обозревателе объектов, а затем выбрать команду **Запустить PowerShell**, то путь Windows PowerShell будет иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="377ee-108">For example, if you right-click the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database object in Object Explorer and select **Start PowerShell**, the Windows PowerShell path is set to the following:</span></span>  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a><span data-ttu-id="377ee-109">Запуск PowerShell из среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="377ee-109">To run PowerShell from SQL Server Management Studio</span></span> 
  
1.  <span data-ttu-id="377ee-110">Откройте **Обозреватель объектов**.</span><span class="sxs-lookup"><span data-stu-id="377ee-110">Open **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="377ee-111">Перейдите к узлу для объекта, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="377ee-111">Navigate to the node for the object to be worked on.</span></span>  
  
3.  <span data-ttu-id="377ee-112">Щелкните объект правой кнопкой мыши и выберите команду **Запустить PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="377ee-112">Right-click the object and select **Start PowerShell**.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="377ee-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="377ee-113">Permissions</span></span>  
 <span data-ttu-id="377ee-114">При открытии из среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]программа PowerShell не запускается с правами администратора, что может стать причиной того, что некоторые действия не будут выполнены, например вызовы инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="377ee-114">When opened from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell does not run with Administrator privileges which may prevent some activities such as calls to WMI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377ee-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="377ee-115">See Also</span></span>  
 [<span data-ttu-id="377ee-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="377ee-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
