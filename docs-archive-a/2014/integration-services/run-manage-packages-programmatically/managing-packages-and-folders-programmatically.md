---
title: Программное управление пакетами и папками | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], managing
- custom enumerators [Integration Services]
ms.assetid: ec59b75d-ba09-44ac-9039-9d593bb462d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 695ff4ad020dbdfb2564b4964a55324db4248517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740130"
---
# <a name="managing-packages-and-folders-programmatically"></a><span data-ttu-id="62784-102">Программное управление пакетами и папками</span><span class="sxs-lookup"><span data-stu-id="62784-102">Managing Packages and Folders Programmatically</span></span>
  <span data-ttu-id="62784-103">В процессе программирования при работе с пакетами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] может возникнуть необходимость определить, существует ли отдельный пакет или папка, либо управлять папками, где хранятся пакеты.</span><span class="sxs-lookup"><span data-stu-id="62784-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to manage the folders in which packages are stored.</span></span> <span data-ttu-id="62784-104">Класс <xref:Microsoft.SqlServer.Dts.Runtime.Application> из пространства имен <xref:Microsoft.SqlServer.Dts.Runtime> предоставляет разнообразные методы, выполняющие эти требования.</span><span class="sxs-lookup"><span data-stu-id="62784-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="62784-105">Определение существования пакета или папки</span><span class="sxs-lookup"><span data-stu-id="62784-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="62784-106">Чтобы определить программным способом, существует ли сохраненный пакет, перед попыткой загрузить и выполнить его вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="62784-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run the package:</span></span>  
  
|<span data-ttu-id="62784-107">Место хранения</span><span class="sxs-lookup"><span data-stu-id="62784-107">Storage Location</span></span>|<span data-ttu-id="62784-108">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="62784-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="62784-109">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="62784-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="62784-110">Чтобы определить программным способом, существует ли папка, перед попыткой получить список пакетов, хранящихся в этой папке, вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="62784-110">To determine programmatically whether a folder exists, call one of the following methods before attempting to list the packages stored in the folder, :</span></span>  
  
|<span data-ttu-id="62784-111">Место хранения</span><span class="sxs-lookup"><span data-stu-id="62784-111">Storage Location</span></span>|<span data-ttu-id="62784-112">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="62784-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="62784-113">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="62784-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  

  
##  <a name="managing-packages-and-folders"></a><a name="managing"></a> <span data-ttu-id="62784-114">Управление пакетами и папками</span><span class="sxs-lookup"><span data-stu-id="62784-114">Managing Packages and Folders</span></span>  
 <span data-ttu-id="62784-115">Класс <xref:Microsoft.SqlServer.Dts.Runtime.Application> пространства имен <xref:Microsoft.SqlServer.Dts.Runtime> предоставляет дополнительные методы для управления пакетами и папками, в которых эти пакеты хранятся.</span><span class="sxs-lookup"><span data-stu-id="62784-115">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides additional methods for managing packages and the folders in which they are stored.</span></span>  
  
###  <a name="removing-a-package"></a><a name="managing_rempkg"></a> <span data-ttu-id="62784-116">Удаление пакета</span><span class="sxs-lookup"><span data-stu-id="62784-116">Removing a Package</span></span>  
 <span data-ttu-id="62784-117">Для удаления сохраненного пакета программным способом вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="62784-117">To remove a saved package programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="62784-118">Место хранения</span><span class="sxs-lookup"><span data-stu-id="62784-118">Storage Location</span></span>|<span data-ttu-id="62784-119">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="62784-119">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="62784-120">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="62784-120">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromSqlServer%2A>|  
  

  
###  <a name="creating-a-folder"></a><a name="managing_create"></a> <span data-ttu-id="62784-121">Создание папки</span><span class="sxs-lookup"><span data-stu-id="62784-121">Creating a Folder</span></span>  
 <span data-ttu-id="62784-122">Для создания папки хранения программным способом вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="62784-122">To create a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="62784-123">Место хранения</span><span class="sxs-lookup"><span data-stu-id="62784-123">Storage Location</span></span>|<span data-ttu-id="62784-124">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="62784-124">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="62784-125">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="62784-125">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnSqlServer%2A>|  
  

  
###  <a name="removing-a-folder"></a><a name="managing_remfldr"></a> <span data-ttu-id="62784-126">Удаление папки</span><span class="sxs-lookup"><span data-stu-id="62784-126">Removing a Folder</span></span>  
 <span data-ttu-id="62784-127">Для удаления папки хранения программным способом вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="62784-127">To remove a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="62784-128">Место хранения</span><span class="sxs-lookup"><span data-stu-id="62784-128">Storage Location</span></span>|<span data-ttu-id="62784-129">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="62784-129">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="62784-130">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="62784-130">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromSqlServer%2A>|  
  
  
  
###  <a name="renaming-a-folder"></a><a name="managing_rename"></a> <span data-ttu-id="62784-131">Переименование папки</span><span class="sxs-lookup"><span data-stu-id="62784-131">Renaming a Folder</span></span>  
 <span data-ttu-id="62784-132">Для переименования папки хранения программным способом вызовите один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="62784-132">To rename a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="62784-133">Место хранения</span><span class="sxs-lookup"><span data-stu-id="62784-133">Storage Location</span></span>|<span data-ttu-id="62784-134">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="62784-134">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="62784-135">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="62784-135">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnSqlServer%2A>|  
  

  
<span data-ttu-id="62784-136">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="62784-136">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="62784-137">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="62784-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="62784-138">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="62784-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="62784-139">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="62784-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62784-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="62784-140">See Also</span></span>  
 <span data-ttu-id="62784-141">[Управление пакетами &#40;служб SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="62784-141">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="62784-142">Программное перечисление доступных пакетов</span><span class="sxs-lookup"><span data-stu-id="62784-142">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
