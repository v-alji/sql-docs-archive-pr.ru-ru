---
title: Диалоговое окно "активные операции" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isoperations.executions.f1
- sql12.ssis.ssms.isoperations.general.f1
ms.assetid: 5bb0fcd6-0ce9-488a-85b8-25dddaa03cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49861de7be207875c554e02d3f3b1b2f941fff64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656538"
---
# <a name="active-operations-dialog-box"></a><span data-ttu-id="9767c-102">Диалоговое окно «Активные операции»</span><span class="sxs-lookup"><span data-stu-id="9767c-102">Active Operations Dialog Box</span></span>
  <span data-ttu-id="9767c-103">Воспользуйтесь диалоговым окном **Активные операции** , чтобы просмотреть состояние выполняемых в настоящий момент операций [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , таких как развертывание, проверка и выполнение пакетов.</span><span class="sxs-lookup"><span data-stu-id="9767c-103">Use the **Active Operations** dialog box to view the status of currently running [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, such as deployment, validation, and package execution.</span></span> <span data-ttu-id="9767c-104">Эти данные хранятся в каталоге SSISDB.</span><span class="sxs-lookup"><span data-stu-id="9767c-104">This data is stored in the SSISDB catalog.</span></span>  
  
 <span data-ttu-id="9767c-105">Дополнительные сведения о связанных представлениях [!INCLUDE[tsql](../includes/tsql-md.md)] см. в разделах [catalog.operations (база данных SSISDB)](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations (база данных SSISDB)](/sql/integration-services/system-views/catalog-validations-ssisdb-database) и [catalog.executions (база данных SSISDB)](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="9767c-105">For more information about related [!INCLUDE[tsql](../includes/tsql-md.md)] views, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), and [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span></span>  
  
 <span data-ttu-id="9767c-106">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="9767c-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="9767c-107">Открытие диалогового окна «активные операции»</span><span class="sxs-lookup"><span data-stu-id="9767c-107">Open the Active Operations Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="9767c-108">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="9767c-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-active-operations-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="9767c-109">Открытие диалогового окна «Активные операции»</span><span class="sxs-lookup"><span data-stu-id="9767c-109">Open the Active Operations Dialog Box</span></span>  
  
1.  <span data-ttu-id="9767c-110">Откройте среду [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9767c-110">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="9767c-111">Подключение компонента Microsoft SQL Server Database Engine</span><span class="sxs-lookup"><span data-stu-id="9767c-111">Connect Microsoft SQL Server Database Engine</span></span>  
  
3.  <span data-ttu-id="9767c-112">В обозревателе объектов разверните узел **Службы Integration Services** , щелкните правой кнопкой мыши элемент **SSISDB**и выберите пункт **Активные операции**.</span><span class="sxs-lookup"><span data-stu-id="9767c-112">In Object Explorer, expand the **Integration Services** node, right-click **SSISDB**, and then click **Active Operations**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="9767c-113">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="9767c-113">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="9767c-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="9767c-114">Options</span></span>  
 <span data-ttu-id="9767c-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9767c-115">**Type**</span></span>  
 <span data-ttu-id="9767c-116">Задает тип операции.</span><span class="sxs-lookup"><span data-stu-id="9767c-116">Specifies the type of operation.</span></span> <span data-ttu-id="9767c-117">Ниже приведены возможные значения для поля **Type** и соответствующие значения в столбце Operations_type представления TRANSACT-SQL `catalog.operations` .</span><span class="sxs-lookup"><span data-stu-id="9767c-117">The following are the possible values for the **Type** field and the corresponding values in the operations_type column of the Transact-SQL `catalog.operations` view.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9767c-118">Инициализация служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="9767c-118">Integration Services initialization</span></span>|<span data-ttu-id="9767c-119">1</span><span class="sxs-lookup"><span data-stu-id="9767c-119">1</span></span>|  
|<span data-ttu-id="9767c-120">Очистка операций (задание агента SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9767c-120">Operations cleanup (SQL Agent job)</span></span>|<span data-ttu-id="9767c-121">2</span><span class="sxs-lookup"><span data-stu-id="9767c-121">2</span></span>|  
|<span data-ttu-id="9767c-122">Очистка версий проекта (задание агента SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9767c-122">Project versions cleanup (SQL Agent job)</span></span>|<span data-ttu-id="9767c-123">3</span><span class="sxs-lookup"><span data-stu-id="9767c-123">3</span></span>|  
|<span data-ttu-id="9767c-124">Развернуть проект</span><span class="sxs-lookup"><span data-stu-id="9767c-124">Deploy project</span></span>|<span data-ttu-id="9767c-125">101</span><span class="sxs-lookup"><span data-stu-id="9767c-125">101</span></span>|  
|<span data-ttu-id="9767c-126">Восстановить проект</span><span class="sxs-lookup"><span data-stu-id="9767c-126">Restore project</span></span>|<span data-ttu-id="9767c-127">106</span><span class="sxs-lookup"><span data-stu-id="9767c-127">106</span></span>|  
|<span data-ttu-id="9767c-128">Создать и запустить выполнение пакета</span><span class="sxs-lookup"><span data-stu-id="9767c-128">Create and start package execution</span></span>|<span data-ttu-id="9767c-129">200</span><span class="sxs-lookup"><span data-stu-id="9767c-129">200</span></span>|  
|<span data-ttu-id="9767c-130">Остановить операцию (остановка проверки или выполнения</span><span class="sxs-lookup"><span data-stu-id="9767c-130">Stop operation (stopping a validation or execution</span></span>|<span data-ttu-id="9767c-131">202</span><span class="sxs-lookup"><span data-stu-id="9767c-131">202</span></span>|  
|<span data-ttu-id="9767c-132">Проверить проект</span><span class="sxs-lookup"><span data-stu-id="9767c-132">Validate project</span></span>|<span data-ttu-id="9767c-133">300</span><span class="sxs-lookup"><span data-stu-id="9767c-133">300</span></span>|  
|<span data-ttu-id="9767c-134">Проверить пакет</span><span class="sxs-lookup"><span data-stu-id="9767c-134">Validate package</span></span>|<span data-ttu-id="9767c-135">301</span><span class="sxs-lookup"><span data-stu-id="9767c-135">301</span></span>|  
|<span data-ttu-id="9767c-136">Настроить каталог</span><span class="sxs-lookup"><span data-stu-id="9767c-136">Configure catalog</span></span>|<span data-ttu-id="9767c-137">1000</span><span class="sxs-lookup"><span data-stu-id="9767c-137">1000</span></span>|  
  
 <span data-ttu-id="9767c-138">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="9767c-138">**Stop**</span></span>  
 <span data-ttu-id="9767c-139">Щелкните, чтобы остановить выполняемую в настоящий момент операцию.</span><span class="sxs-lookup"><span data-stu-id="9767c-139">Click to stop a currently running operation.</span></span>  
  
  
