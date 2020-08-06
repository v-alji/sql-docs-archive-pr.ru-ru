---
title: Диалоговое окно "Проверка" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackagevalidate.f1
- sql12.ssis.ssms.isprojectvalidate.f1
ms.assetid: 134e14ce-4f8d-4a20-889a-918014c841d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 69e29d106dc9f4f100bf191911c5c34e0250be8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655887"
---
# <a name="validate-dialog-box"></a><span data-ttu-id="d3206-102">Проверка диалогового окна</span><span class="sxs-lookup"><span data-stu-id="d3206-102">Validate Dialog Box</span></span>
  <span data-ttu-id="d3206-103">Воспользуйтесь диалоговым окном **Проверка** для поиска типичных проблем в проекте или пакете служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3206-103">Use the **Validate** dialog box to check for common problems in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a project or package.</span></span>  
  
 <span data-ttu-id="d3206-104">При обнаружении проблемы в верхней части диалогового окна отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="d3206-104">If there is a problem, a message is displayed at the top of the dialog box.</span></span> <span data-ttu-id="d3206-105">В противном случае в верхней части диалогового окна отображается сообщение «Готово».</span><span class="sxs-lookup"><span data-stu-id="d3206-105">Otherwise, the term Ready displays at the top.</span></span>  
  
 <span data-ttu-id="d3206-106">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="d3206-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="d3206-107">Открытие диалогового окна «Проверка»</span><span class="sxs-lookup"><span data-stu-id="d3206-107">Open the Validate dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="d3206-108">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="d3206-108">Set the options on the General page</span></span>](#general)  
  
##  <a name="open-the-validate-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="d3206-109">Открытие диалогового окна «Проверка»</span><span class="sxs-lookup"><span data-stu-id="d3206-109">Open the Validate dialog box</span></span>  
  
1.  <span data-ttu-id="d3206-110">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3206-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="d3206-111">Устанавливается соединение с экземпляром [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], в котором размещена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="d3206-111">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="d3206-112">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="d3206-112">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="d3206-113">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="d3206-113">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="d3206-114">Разверните папку, содержащую проект или пакет, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="d3206-114">Expand the folder that contains the project or package you want to validate.</span></span>  
  
5.  <span data-ttu-id="d3206-115">Щелкните правой кнопкой мыши пакет или проект и выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="d3206-115">Right-click the package or package, and then click **Validate**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="d3206-116">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="d3206-116">Set the options on the General page</span></span>  
 <span data-ttu-id="d3206-117">**Среда**</span><span class="sxs-lookup"><span data-stu-id="d3206-117">**Environment**</span></span>  
 <span data-ttu-id="d3206-118">Выберите среду, которая будет использована для проверки проекта или пакета.</span><span class="sxs-lookup"><span data-stu-id="d3206-118">Select the environment that you want to use to validate the project or package.</span></span>  
  
 <span data-ttu-id="d3206-119">**32-разрядная среда выполнения**</span><span class="sxs-lookup"><span data-stu-id="d3206-119">**32-bit runtime**</span></span>  
 <span data-ttu-id="d3206-120">Для выполнения пакета выберите 32-разрядную среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="d3206-120">Select to use a 32-bit runtime to execute a package.</span></span>  
  
 <span data-ttu-id="d3206-121">На вкладке **Параметры** перечислены значения параметров, которые используются для проверки проекта или пакета.</span><span class="sxs-lookup"><span data-stu-id="d3206-121">The **Parameters** tab lists the parameter values that you use to validate the project or package.</span></span> <span data-ttu-id="d3206-122">Ниже приведены параметры на вкладке «Параметры».</span><span class="sxs-lookup"><span data-stu-id="d3206-122">The following are the options on the Parameters tab.</span></span>  
  
 <span data-ttu-id="d3206-123">**Контейнер**</span><span class="sxs-lookup"><span data-stu-id="d3206-123">**Container**</span></span>  
 <span data-ttu-id="d3206-124">Выводит список объектов, содержащих параметр.</span><span class="sxs-lookup"><span data-stu-id="d3206-124">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="d3206-125">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="d3206-125">**Parameter**</span></span>  
 <span data-ttu-id="d3206-126">Выводит список названий параметров</span><span class="sxs-lookup"><span data-stu-id="d3206-126">Lists the name of the parameters</span></span>  
  
 <span data-ttu-id="d3206-127">**Value**</span><span class="sxs-lookup"><span data-stu-id="d3206-127">**Value**</span></span>  
 <span data-ttu-id="d3206-128">Выводит список значений параметра.</span><span class="sxs-lookup"><span data-stu-id="d3206-128">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="d3206-129">На вкладке **Диспетчеры соединений** перечислены значения свойств диспетчеров соединений, которые используются для проверки проекта или пакета.</span><span class="sxs-lookup"><span data-stu-id="d3206-129">The **Connection Managers** tab lists the connection manager property values that you use to validate the project or package.</span></span>  
  
 <span data-ttu-id="d3206-130">Ниже приведены параметры на вкладке **Диспетчеры соединений** .</span><span class="sxs-lookup"><span data-stu-id="d3206-130">The following are the options on the **Connection Managers** tab.</span></span>  
  
 <span data-ttu-id="d3206-131">**Контейнер**</span><span class="sxs-lookup"><span data-stu-id="d3206-131">**Container**</span></span>  
 <span data-ttu-id="d3206-132">Выводит список объектов, содержащих диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="d3206-132">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="d3206-133">**Название**</span><span class="sxs-lookup"><span data-stu-id="d3206-133">**Name**</span></span>  
 <span data-ttu-id="d3206-134">Выводит список имен диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="d3206-134">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="d3206-135">**Имя свойства**</span><span class="sxs-lookup"><span data-stu-id="d3206-135">**Property name**</span></span>  
 <span data-ttu-id="d3206-136">Выводит список названий свойств диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="d3206-136">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="d3206-137">**Value**</span><span class="sxs-lookup"><span data-stu-id="d3206-137">**Value**</span></span>  
 <span data-ttu-id="d3206-138">Выводит список значений, присвоенных свойствам диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="d3206-138">Lists the value assigned to the connection manager property.</span></span>  
  
  
