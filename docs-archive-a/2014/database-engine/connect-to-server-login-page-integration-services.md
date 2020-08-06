---
title: Соединение с сервером (страница "Имя входа") службы Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 285518f4a1f3d9180d2c3c07a41bf75a00ea3593
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740364"
---
# <a name="connect-to-server-login-page-integration-services"></a><span data-ttu-id="5ea39-102">Соединение с сервером (страница «Имя входа») службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="5ea39-102">Connect to Server (Login Page) Integration Services</span></span>
  <span data-ttu-id="5ea39-103">Эта вкладка используется для просмотра или указания следующих параметров при соединении с [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ea39-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ea39-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ea39-104">Options</span></span>  
 <span data-ttu-id="5ea39-105">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="5ea39-105">**Server type**</span></span>  
 <span data-ttu-id="5ea39-106">При регистрации сервера из обозревателя объектов выберите тип сервера для подключения: [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services.</span><span class="sxs-lookup"><span data-stu-id="5ea39-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="5ea39-107">В остальной части диалогового окна показаны параметры, которые применяются только к выбранному типу сервера.</span><span class="sxs-lookup"><span data-stu-id="5ea39-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="5ea39-108">При регистрации сервера c панели "Зарегистрированные серверы" поле **Тип сервера** не может быть изменено и совпадает с типом сервера, показанного в компоненте "Зарегистрированные серверы".</span><span class="sxs-lookup"><span data-stu-id="5ea39-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="5ea39-109">Чтобы зарегистрировать другой тип сервера, выберите компонент [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services на панели инструментов «Зарегистрированные серверы», прежде чем начать регистрацию нового сервера.</span><span class="sxs-lookup"><span data-stu-id="5ea39-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="5ea39-110">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="5ea39-110">**Server name**</span></span>  
 <span data-ttu-id="5ea39-111">Выберите имя сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="5ea39-111">Select the server to connect to.</span></span> <span data-ttu-id="5ea39-112">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="5ea39-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ea39-113">Не используйте *\<servername>* \\ *\<instancename>* , поскольку не [!INCLUDE[ssIS](../includes/ssis-md.md)] поддерживает несколько экземпляров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5ea39-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="5ea39-114">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="5ea39-114">**Authentication**</span></span>  
 <span data-ttu-id="5ea39-115">Для служб [!INCLUDE[msCoName](../includes/msconame-md.md)] доступна только проверка подлинности [!INCLUDE[ssIS](../includes/ssis-md.md)]Windows.</span><span class="sxs-lookup"><span data-stu-id="5ea39-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="5ea39-116">Режим проверки подлинности Windows позволяет подключаться с учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="5ea39-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="5ea39-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="5ea39-117">**User name**</span></span>  
 <span data-ttu-id="5ea39-118">Этот параметр недоступен, поскольку для служб [!INCLUDE[ssIS](../includes/ssis-md.md)]возможен только режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5ea39-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="5ea39-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="5ea39-119">**Password**</span></span>  
 <span data-ttu-id="5ea39-120">Этот параметр недоступен, поскольку для служб [!INCLUDE[ssIS](../includes/ssis-md.md)]возможен только режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5ea39-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="5ea39-121">**Запоминание пароля**</span><span class="sxs-lookup"><span data-stu-id="5ea39-121">**Remember password**</span></span>  
 <span data-ttu-id="5ea39-122">Этот параметр недоступен, поскольку для служб [!INCLUDE[ssIS](../includes/ssis-md.md)]возможен только режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5ea39-122">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="5ea39-123">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="5ea39-123">**Connect**</span></span>  
 <span data-ttu-id="5ea39-124">Подключиться к выбранному выше серверу.</span><span class="sxs-lookup"><span data-stu-id="5ea39-124">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="5ea39-125">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="5ea39-125">**Options**</span></span>  
 <span data-ttu-id="5ea39-126">Выберите этот пункт, чтобы изменить диалоговое окно и скрыть такие дополнительные параметры соединения сервера, как запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="5ea39-126">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
