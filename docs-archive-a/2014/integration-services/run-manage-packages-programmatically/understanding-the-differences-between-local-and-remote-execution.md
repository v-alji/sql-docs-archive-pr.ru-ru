---
title: Основные сведения об отличиях между локальным и удаленным выполнением | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 399584c790f4c5a5dd136121c58a5ff7743f4969
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730837"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a><span data-ttu-id="4578f-102">Основные сведения об отличиях между локальным и удаленным выполнением</span><span class="sxs-lookup"><span data-stu-id="4578f-102">Understanding the Differences between Local and Remote Execution</span></span>
  <span data-ttu-id="4578f-103">Разработчики пакетов и администраторы должны знать, в чем состоят ограничения, связанные с местом выполнения пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4578f-103">Package developers and administrators should be aware that there are restrictions related to where an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package runs.</span></span>  
  
-   <span data-ttu-id="4578f-104">**Пакет выполняется на том же компьютере, что и запустившая его программа**.</span><span class="sxs-lookup"><span data-stu-id="4578f-104">**A package runs on the same computer as the program that launches it**.</span></span> <span data-ttu-id="4578f-105">Даже если программа загружает пакет, который хранится удаленно на другом сервере, пакет выполняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4578f-105">Even when a program loads a package that is stored remotely on another server, the package runs on the local computer.</span></span>  
  
-   <span data-ttu-id="4578f-106">**Вне среды разработки пакет может выполняться только на том компьютере, на котором установлены службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="4578f-106">**You can only run a package outside the development environment on a computer that has Integration Services installed**.</span></span> <span data-ttu-id="4578f-107">Невозможно выполнять пакеты вне среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] на клиентском компьютере, если не установлены службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Условия вашей лицензии на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут не допускать установку служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на дополнительных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4578f-107">You cannot run packages outside of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing may not permit you to install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="4578f-108">Службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] являются серверным компонентом и не могут устанавливаться на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4578f-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span> <span data-ttu-id="4578f-109">Чтобы выполнить пакеты с клиентского компьютера, необходимо запускать их таким способом, который позволяет гарантировать выполнение пакетов на сервере.</span><span class="sxs-lookup"><span data-stu-id="4578f-109">To run packages from a client computer, you need to launch them in a manner that ensures that the packages run on the server.</span></span>  
  
 <span data-ttu-id="4578f-110">Дополнительные сведения о загрузке и выполнении сохраненного пакета см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="4578f-110">For more information about loading and running a saved package, see:</span></span>  
  
-   [<span data-ttu-id="4578f-111">Программная загрузка и запуск локального пакета</span><span class="sxs-lookup"><span data-stu-id="4578f-111">Loading and Running a Local Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [<span data-ttu-id="4578f-112">Программная загрузка и запуск удаленного пакета</span><span class="sxs-lookup"><span data-stu-id="4578f-112">Loading and Running a Remote Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 <span data-ttu-id="4578f-113">Дополнительные сведения о выполнении пакета и загрузке его выхода в пользовательскую программу см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="4578f-113">For more information about running a package and loading its output into a custom program, see:</span></span>  
  
-   [<span data-ttu-id="4578f-114">Загрузка выхода локального пакета</span><span class="sxs-lookup"><span data-stu-id="4578f-114">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
<span data-ttu-id="4578f-115">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4578f-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4578f-116">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4578f-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4578f-117">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4578f-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4578f-118">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4578f-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4578f-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="4578f-119">See Also</span></span>  
 <span data-ttu-id="4578f-120">[Программная загрузка и запуск локального пакета](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="4578f-120">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 <span data-ttu-id="4578f-121">[Программная загрузка и запуск удаленного пакета](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="4578f-121">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="4578f-122">Загрузка выхода локального пакета</span><span class="sxs-lookup"><span data-stu-id="4578f-122">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
