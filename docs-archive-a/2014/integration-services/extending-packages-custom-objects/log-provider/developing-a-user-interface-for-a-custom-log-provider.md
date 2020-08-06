---
title: Разработка пользовательского интерфейса для пользовательского регистратора | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom user interface [Integration Services], custom log providers
- custom log providers [Integration Services], developing custom user interface
ms.assetid: 6fd2d269-d87a-4134-82a1-40a09b3b5453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c3ce6cf5ad744e307bbb049347047bf94fc5a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655880"
---
# <a name="developing-a-user-interface-for-a-custom-log-provider"></a><span data-ttu-id="09ef3-102">Разработка пользовательского интерфейса для пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="09ef3-102">Developing a User Interface for a Custom Log Provider</span></span>
  <span data-ttu-id="09ef3-103">Многие регистраторы служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] имеют собственный пользовательский интерфейс, в котором реализован интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI>, а вместо содержимого текстового поля **Конфигурация** в диалоговом окне **Настройка журналов служб SSIS** используется фильтруемый раскрывающийся список доступных диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="09ef3-103">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="09ef3-104">Однако пользовательские интерфейсы для пользовательских регистраторов не реализуются в службах [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09ef3-104">However, custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
<span data-ttu-id="09ef3-105">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="09ef3-105">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="09ef3-106">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="09ef3-106">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="09ef3-107">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="09ef3-107">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="09ef3-108">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="09ef3-108">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ef3-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="09ef3-109">See Also</span></span>  
 <span data-ttu-id="09ef3-110">[Создание пользовательского регистратора](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="09ef3-110">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="09ef3-111">Создание кода пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="09ef3-111">Coding a Custom Log Provider</span></span>](coding-a-custom-log-provider.md)  
  
  
