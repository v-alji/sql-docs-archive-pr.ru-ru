---
title: Сравнение решений со скриптами и пользовательских объектов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- managed tasks [Integration Services]
- Script task [Integration Services], vs. custom managed tasks
- SSIS Script task, vs. custom managed tasks
- custom tasks [Integration Services], scripts
ms.assetid: c0aea822-a21e-44e1-a3d3-8777bd0a1c34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: acf6faf9cdd78e951b8298c4e3b144d3444fb1ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655873"
---
# <a name="comparing-scripting-solutions-and-custom-objects"></a><span data-ttu-id="e79fd-102">Сравнение решений со сценариями и пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="e79fd-102">Comparing Scripting Solutions and Custom Objects</span></span>
  <span data-ttu-id="e79fd-103">Задача «Скрипт» или компонент скрипта служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] может реализовать значительную часть функций, которые обеспечиваются пользовательской управляемой задачей или компонентом потока данных.</span><span class="sxs-lookup"><span data-stu-id="e79fd-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task or Script component can implement much of the same functionality that is possible in a custom managed task or data flow component.</span></span> <span data-ttu-id="e79fd-104">Ниже приведены некоторые рекомендации, которые помогут выбрать тип задачи, отвечающий потребностям пользователя.</span><span class="sxs-lookup"><span data-stu-id="e79fd-104">Here are some considerations to help you choose the appropriate type of task for your needs:</span></span>  
  
-   <span data-ttu-id="e79fd-105">Если конфигурация или функция относятся к отдельному пакету, следует создать задачу «Скрипт» или компонент скрипта, а не разрабатывать пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="e79fd-105">If the configuration or functionality is specific to an individual package, you should use the Script task or the Script component instead of a developing a custom object.</span></span>  
  
-   <span data-ttu-id="e79fd-106">Если функциональность имеет общий характер и может использоваться в дальнейшем для других пакетов или другими разработчиками, то вместо решения, основанного на использовании сценариев, следует создать пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="e79fd-106">If the functionality is generic, and might be used in the future for other packages and by other developers, you should create a custom object instead of using a scripting solution.</span></span> <span data-ttu-id="e79fd-107">Пользовательский объект может быть использован в любом пакете, в то время как скрипт может использоваться только в пакете, для которого он был создан.</span><span class="sxs-lookup"><span data-stu-id="e79fd-107">You can use a custom object in any package, whereas a script can be used only in the package for which it was created.</span></span>  
  
-   <span data-ttu-id="e79fd-108">Если код может быть использован повторно в рамках того же пакета, целесообразно рассмотреть возможность создания пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="e79fd-108">If the code will be reused within the same package, you should consider creating a custom object.</span></span> <span data-ttu-id="e79fd-109">Копирование кода из одной задачи «Скрипт» (или компонента скриптов) в другую приведет к усложнению сопровождения кода из-за необходимости поддерживать работоспособность и обеспечивать обновление нескольких копий кода.</span><span class="sxs-lookup"><span data-stu-id="e79fd-109">Copying code from one Script task or component to another leads to reduced maintainability by making it more difficult to maintain and update multiple copies of the code.</span></span>  
  
-   <span data-ttu-id="e79fd-110">Если со временем предполагается внести изменения в реализацию, рассмотрите возможность использования пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="e79fd-110">If the implementation will change over time, consider using a custom object.</span></span> <span data-ttu-id="e79fd-111">Пользовательские объекты можно разрабатывать и развертывать отдельно от родительского пакета, в то время как обновление, которое вносится в решение на основе сценария, требует повторного развертывания всего пакета.</span><span class="sxs-lookup"><span data-stu-id="e79fd-111">Custom objects can be developed and deployed separately from the parent package, whereas an update made to a scripting solution requires the redeployment of the whole package.</span></span>  
  
<span data-ttu-id="e79fd-112">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e79fd-112">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e79fd-113">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="e79fd-113">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e79fd-114">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="e79fd-114">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e79fd-115">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="e79fd-115">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79fd-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e79fd-116">See Also</span></span>  
 [<span data-ttu-id="e79fd-117">Расширение пакетов с помощью пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="e79fd-117">Extending Packages with Custom Objects</span></span>](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
  
  
