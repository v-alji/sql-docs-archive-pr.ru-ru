---
title: Диалоговое окно "Свойства пакета" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b386bf4e75ff784cd8d4a96363515786d242d2a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658355"
---
# <a name="package-properties-dialog-box"></a><span data-ttu-id="a1ff2-102">диалоговое окно «Свойства пакета»</span><span class="sxs-lookup"><span data-stu-id="a1ff2-102">Package Properties Dialog Box</span></span>
  <span data-ttu-id="a1ff2-103">Используйте диалоговое окно **Свойства пакета** для просмотра свойств пакетов, хранящихся на сервере служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1ff2-103">Use the **Package Properties** dialog box to view properties for packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="a1ff2-104">Дополнительные сведения см. в разделе [Службы Integration Services (сервер служб SSIS)](integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a1ff2-104">For more information, see [Integration Services &#40;SSIS&#41; Server](integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="a1ff2-105">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="a1ff2-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="a1ff2-106">Открытие диалогового окна «Свойства пакета»</span><span class="sxs-lookup"><span data-stu-id="a1ff2-106">Open the Package Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="a1ff2-107">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="a1ff2-107">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-package-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="a1ff2-108">Открытие диалогового окна «Свойства пакета»</span><span class="sxs-lookup"><span data-stu-id="a1ff2-108">Open the Package Properties dialog box</span></span>  
  
1.  <span data-ttu-id="a1ff2-109">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1ff2-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="a1ff2-110">Устанавливается соединение с экземпляром [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], в котором размещена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="a1ff2-111">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="a1ff2-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="a1ff2-112">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="a1ff2-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="a1ff2-113">Разверните папку, содержащую пакет, свойства которого требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-113">Expand the folder that contains the package you want to view properties for.</span></span>  
  
5.  <span data-ttu-id="a1ff2-114">Щелкните правой кнопкой мыши пакет и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-114">Right-click the package, and then select **Properties**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="a1ff2-115">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="a1ff2-115">Configure the Options</span></span>  
 <span data-ttu-id="a1ff2-116">На странице **Общие** можно просмотреть свойства выбранного пакета.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-116">Use the **General** page to view the properties of the selected package.</span></span>  
  
 <span data-ttu-id="a1ff2-117">Все свойства на странице **Общие** доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-117">All properties on the **General** page are read-only.</span></span>  
  
 <span data-ttu-id="a1ff2-118">**Название**</span><span class="sxs-lookup"><span data-stu-id="a1ff2-118">**Name**</span></span>  
 <span data-ttu-id="a1ff2-119">Отображает имя пакета.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-119">Displays the name of the package.</span></span>  
  
 <span data-ttu-id="a1ff2-120">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="a1ff2-120">**Identifier**</span></span>  
 <span data-ttu-id="a1ff2-121">Выводит идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-121">Lists the package ID.</span></span>  
  
 <span data-ttu-id="a1ff2-122">**Точка входа**</span><span class="sxs-lookup"><span data-stu-id="a1ff2-122">**Entry Point**</span></span>  
 <span data-ttu-id="a1ff2-123">Значение `True` указывает, что пакет запущен непосредственно.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-123">The value of `True` indicates that the package is started directly.</span></span> <span data-ttu-id="a1ff2-124">Значение `False` указывает, что пакет запущен из другого пакета с помощью задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="a1ff2-124">The value of `False` indicates that the package is started by another package using the Execute Package task.</span></span> <span data-ttu-id="a1ff2-125">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-125">The default value is `True`.</span></span>  
  
 <span data-ttu-id="a1ff2-126">Это свойство задается в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] как для родительского пакета, так и для дочерних пакетов. Для этого щелкните пакет правой кнопкой мыши в обозревателе решений, а затем выберите **Входной пакет**.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-126">You set this property in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for both the parent package and the child packages by right-clicking the package in Solution Explorer and then clicking **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="a1ff2-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a1ff2-127">**Description**</span></span>  
 <span data-ttu-id="a1ff2-128">Показывает необязательное описание пакета.</span><span class="sxs-lookup"><span data-stu-id="a1ff2-128">Displays the optional description of the package.</span></span>  
  
  
