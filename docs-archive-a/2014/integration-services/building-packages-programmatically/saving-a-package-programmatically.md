---
title: Сохранение пакета программным образом | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically saving a package
- saving a package programmatically
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2879c4213b2c9c0bf395c103de0d1bc37e4daab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657855"
---
# <a name="saving-a-package-programmatically"></a><span data-ttu-id="dfcff-102">Сохранение пакета программным образом</span><span class="sxs-lookup"><span data-stu-id="dfcff-102">Saving a Package Programmatically</span></span>
  <span data-ttu-id="dfcff-103">После программного построения нового или изменения существующего пакета обычно необходимо сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="dfcff-103">After building a new package programmatically, or modifying an existing one, you usually want to save your changes.</span></span>  
  
 <span data-ttu-id="dfcff-104">Все методы, используемые в данном разделе для сохранения пакетов, требуют наличия ссылки на сборку `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="dfcff-104">All of the methods used in this topic to save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="dfcff-105">После добавления ссылки в новый проект импортируйте пространство имен <xref:Microsoft.SqlServer.Dts.Runtime> с помощью инструкции `using` или `Imports`.</span><span class="sxs-lookup"><span data-stu-id="dfcff-105">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="saving-a-package-programmatically"></a><span data-ttu-id="dfcff-106">Сохранение пакета программным образом</span><span class="sxs-lookup"><span data-stu-id="dfcff-106">Saving a Package Programmatically</span></span>  
 <span data-ttu-id="dfcff-107">Для программного сохранения пакета вызовите один из следующих методов класса [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application>.</span><span class="sxs-lookup"><span data-stu-id="dfcff-107">To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:</span></span>  
  
|<span data-ttu-id="dfcff-108">Место хранения</span><span class="sxs-lookup"><span data-stu-id="dfcff-108">Storage Location</span></span>|<span data-ttu-id="dfcff-109">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="dfcff-109">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dfcff-110">Файл</span><span class="sxs-lookup"><span data-stu-id="dfcff-110">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|<span data-ttu-id="dfcff-111">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="dfcff-111">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> <span data-ttu-id="dfcff-112">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="dfcff-112">or</span></span><br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dfcff-113">Методы класса <xref:Microsoft.SqlServer.Dts.Runtime.Application> для работы с хранилищем пакетов служб SSIS поддерживают только «.» и имя сервера для локального сервера.</span><span class="sxs-lookup"><span data-stu-id="dfcff-113">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server.</span></span> <span data-ttu-id="dfcff-114">Использование имен «(local)» и «localhost» невозможно.</span><span class="sxs-lookup"><span data-stu-id="dfcff-114">You cannot use "(local)" or "localhost".</span></span>  
  
<span data-ttu-id="dfcff-115">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dfcff-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dfcff-116">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="dfcff-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dfcff-117">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="dfcff-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dfcff-118">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="dfcff-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcff-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfcff-119">See Also</span></span>  
 [<span data-ttu-id="dfcff-120">Сохранение пакетов</span><span class="sxs-lookup"><span data-stu-id="dfcff-120">Save Packages</span></span>](../save-packages.md)  
  
  
