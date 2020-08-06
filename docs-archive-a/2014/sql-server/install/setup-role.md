---
title: Роль установки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c7e9db15-89f2-4d4d-8860-1e64c5821c4d
author: heidisteen
ms.author: heidist
ms.openlocfilehash: add000eed671303c78ab0500303f826bafe4ab77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659165"
---
# <a name="setup-role"></a><span data-ttu-id="fd35f-102">Роль установки</span><span class="sxs-lookup"><span data-stu-id="fd35f-102">Setup Role</span></span>
  <span data-ttu-id="fd35f-103">На этой странице можно указать, будет страница «Выбор компонентов» использоваться для выбора отдельных функций или для установки с использованием роли установки.</span><span class="sxs-lookup"><span data-stu-id="fd35f-103">Use this page to specify whether to use the Feature Selection page to select individual features, or to install using a setup role.</span></span>  
  
 <span data-ttu-id="fd35f-104">`setup role` представляет собой фиксированный выбор для всех функций и общих компонентов, которые необходимы для реализации стандартной конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd35f-104">A `setup role` is a fixed selection of all the features and shared components that are required to implement a predefined [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configuration.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd35f-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="fd35f-105">Options</span></span>  
 <span data-ttu-id="fd35f-106">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Установка компонентов**</span><span class="sxs-lookup"><span data-stu-id="fd35f-106">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Feature Installation**</span></span>  
 <span data-ttu-id="fd35f-107">Укажите этот параметр для выбора отдельных функций и общих компонентов.</span><span class="sxs-lookup"><span data-stu-id="fd35f-107">Choose this option to select individual features and shared components.</span></span> <span data-ttu-id="fd35f-108">В число компонентов экземпляра входят службы Database Engine Services, Analysis Services (в собственном режиме) и Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd35f-108">Instance features include Database Engine Services, Analysis Services (native mode), and Reporting Services.</span></span>  
  
 <span data-ttu-id="fd35f-109">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]PowerPivot для SharePoint**</span><span class="sxs-lookup"><span data-stu-id="fd35f-109">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot for SharePoint**</span></span>  
 <span data-ttu-id="fd35f-110">Укажите этот параметр для установки компонентов сервера служб Analysis Services на ферме SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="fd35f-110">Choose this option to install Analysis Services server components in a SharePoint 2010 farm.</span></span> <span data-ttu-id="fd35f-111">В этом случае служба PowerPivot System и сервер служб Analysis Services развертываются на ферме, обеспечивая обработку запросов и данных для опубликованных книг Excel, которые содержат внедренные данные [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd35f-111">This option deploys the PowerPivot System Service and the Analysis Services server in a farm, enabling query and data processing for published Excel workbooks that contain embedded [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span>  
  
 <span data-ttu-id="fd35f-112">Дополнительно в установку можно включить экземпляр ядра СУБД для реляционных баз данных, если он необходим для размещения баз данных в ферме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd35f-112">Optionally, you can add a relational database engine instance to your installation if you require it to host databases in a SharePoint farm.</span></span> <span data-ttu-id="fd35f-113">Если ферма уже настроена, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="fd35f-113">If the farm is already configured, you can skip this option.</span></span>  
  
 <span data-ttu-id="fd35f-114">После завершения установки необходимо настроить программное обеспечение с помощью одного из следующих подходов: средство настройки PowerPivot, командлеты PowerShell или центр администрирования SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="fd35f-114">After Setup is finished, you must configure the software using one of the following approaches: PowerPivot Configuration tool, PowerShell cmdlets, or SharePoint 2010 Central Administration.</span></span> <span data-ttu-id="fd35f-115">В отличие от предыдущих выпусков, программа установки больше не выполняет какие-либо задачи по настройке установки PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fd35f-115">In contrast with previous releases, Setup no longer performs any configuration tasks for a PowerPivot installation.</span></span>  
  
 <span data-ttu-id="fd35f-116">Установка на основе роли не включает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot для клиентского приложения Excel.</span><span class="sxs-lookup"><span data-stu-id="fd35f-116">A role-based installation does not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot for Excel client application.</span></span> <span data-ttu-id="fd35f-117">Клиентское приложение устанавливается отдельно.</span><span class="sxs-lookup"><span data-stu-id="fd35f-117">The client application is installed separately.</span></span>  
  
 <span data-ttu-id="fd35f-118">**Все компоненты по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="fd35f-118">**All Features With Defaults**</span></span>  
 <span data-ttu-id="fd35f-119">Выберите эту роль установки, чтобы установить все компоненты, доступные для этой версии.</span><span class="sxs-lookup"><span data-stu-id="fd35f-119">Choose this setup role to install all features that are available for this release.</span></span> <span data-ttu-id="fd35f-120">Обратите внимание, что PowerPivot для SharePoint исключен из этой роли.</span><span class="sxs-lookup"><span data-stu-id="fd35f-120">Note that PowerPivot for SharePoint is excluded from this role.</span></span> <span data-ttu-id="fd35f-121">Чтобы установить этот компонент, необходимо использовать роль программы установки PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd35f-121">You must use the PowerPivot for SharePoint setup role to install that feature.</span></span>  
  
 <span data-ttu-id="fd35f-122">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] настраивается для запуска с использованием учетной записи **NT AUTHORITY\NETWORK SERVICE** .</span><span class="sxs-lookup"><span data-stu-id="fd35f-122">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to start using the **NT AUTHORITY\NETWORK SERVICE** account.</span></span> <span data-ttu-id="fd35f-123">Текущий пользователь подготавливается в качестве члена роли [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="fd35f-123">The current user will be provisioned as a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**sysadmin** role.</span></span> <span data-ttu-id="fd35f-124">Значения, заданные этим параметром, могут быть переопределены с помощью дополнительных параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="fd35f-124">Values set by this option can be overridden by specifying additional command line parameters.</span></span>  
  
 <span data-ttu-id="fd35f-125">Если операционная система не является контроллером домена, по умолчанию в компоненте Database Engine и службах Reporting Services используется учетная запись NTAUTHORITY\NETWORK SERVICE, в Integration Services — учетная запись NTAUTHORITY\NETWORK SERVICE, а в средстве запуска управляющей программы полнотекстовой фильтрации SQL — учетная запись NTAUTHORITY\LOCAL SERVICE.</span><span class="sxs-lookup"><span data-stu-id="fd35f-125">When the operating system is not a domain controller, by default the Database Engine and Reporting Services will use the NTAUTHORITY\NETWORK SERVICE account, Integration Services will use the NTAUTHORITY\NETWORK SERVICE account, and the SQL Full text Filter Daemon Launcher will use the NTAUTHORITY\LOCAL SERVICE account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd35f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd35f-126">See Also</span></span>  
 <span data-ttu-id="fd35f-127">[Установка PowerPivot для SharePoint](https://go.microsoft.com/fwlink/?LinkId=206906) </span><span class="sxs-lookup"><span data-stu-id="fd35f-127">[Installing PowerPivot for SharePoint](https://go.microsoft.com/fwlink/?LinkId=206906) </span></span>  
 <span data-ttu-id="fd35f-128">[Требования к оборудованию и программному обеспечению (PowerPivot для SharePoint](https://go.microsoft.com/fwlink/?LinkId=216823) </span><span class="sxs-lookup"><span data-stu-id="fd35f-128">[Hardware and Software Requirements (PowerPivot for SharePoint](https://go.microsoft.com/fwlink/?LinkId=216823) </span></span>  
 [<span data-ttu-id="fd35f-129">Выбор компонентов</span><span class="sxs-lookup"><span data-stu-id="fd35f-129">Feature Selection</span></span>](../../../2014/sql-server/install/feature-selection.md)  
  
  
