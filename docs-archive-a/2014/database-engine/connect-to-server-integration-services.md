---
title: Соединение с сервером (службы Integration Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.dtsserver.f1
ms.assetid: 5be897bd-f36c-4c6a-a91a-13d0d016f8b6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8821018c45fdd77c4b3b896afc47b8f5b425af88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740370"
---
# <a name="connect-to-server-integration-services"></a><span data-ttu-id="6eac1-102">Соединение с сервером (службы Integration Services)</span><span class="sxs-lookup"><span data-stu-id="6eac1-102">Connect to Server (Integration Services)</span></span>
  <span data-ttu-id="6eac1-103">Используйте это диалоговое окно для просмотра или настройки параметров при подключении к [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eac1-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="6eac1-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="6eac1-104">Options</span></span>  
 <span data-ttu-id="6eac1-105">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="6eac1-105">**Server type**</span></span>  
 <span data-ttu-id="6eac1-106">При регистрации сервера из обозревателя объектов выберите тип сервера для подключения: [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services.</span><span class="sxs-lookup"><span data-stu-id="6eac1-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="6eac1-107">В остальной части диалогового окна показаны параметры, которые применяются только к выбранному типу сервера.</span><span class="sxs-lookup"><span data-stu-id="6eac1-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="6eac1-108">При регистрации сервера в окне «Зарегистрированные серверы» поле «Тип сервера» доступно только для чтения и соответствует типу сервера, который выводится в компоненте «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="6eac1-108">When registering a server from Registered Servers, the Server type box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="6eac1-109">Чтобы зарегистрировать другой тип сервера, выберите компонент [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services на панели инструментов «Зарегистрированные серверы», прежде чем начать регистрацию нового сервера.</span><span class="sxs-lookup"><span data-stu-id="6eac1-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="6eac1-110">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="6eac1-110">**Server name**</span></span>  
 <span data-ttu-id="6eac1-111">Выберите имя сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="6eac1-111">Select the server to connect to.</span></span> <span data-ttu-id="6eac1-112">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="6eac1-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6eac1-113">Не используйте *\<servername>* \\ *\<instancename>* , поскольку не [!INCLUDE[ssIS](../includes/ssis-md.md)] поддерживает несколько экземпляров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6eac1-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="6eac1-114">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="6eac1-114">**Authentication**</span></span>  
 <span data-ttu-id="6eac1-115">Для служб [!INCLUDE[msCoName](../includes/msconame-md.md)] доступна только проверка подлинности [!INCLUDE[ssIS](../includes/ssis-md.md)]Windows.</span><span class="sxs-lookup"><span data-stu-id="6eac1-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="6eac1-116">Режим проверки подлинности Windows позволяет подключаться с учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="6eac1-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="6eac1-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="6eac1-117">**User name**</span></span>  
 <span data-ttu-id="6eac1-118">Этот параметр недоступен, поскольку для служб [!INCLUDE[ssIS](../includes/ssis-md.md)]возможен только режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="6eac1-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="6eac1-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="6eac1-119">**Password**</span></span>  
 <span data-ttu-id="6eac1-120">Этот параметр недоступен, поскольку для служб [!INCLUDE[ssIS](../includes/ssis-md.md)]возможен только режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="6eac1-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="6eac1-121">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="6eac1-121">**Connect**</span></span>  
 <span data-ttu-id="6eac1-122">Нажмите, чтобы подключиться к выбранному выше серверу.</span><span class="sxs-lookup"><span data-stu-id="6eac1-122">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="6eac1-123">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="6eac1-123">**Options**</span></span>  
 <span data-ttu-id="6eac1-124">Нажмите, чтобы вывести дополнительные параметры соединения с сервером, такие как регистрация сервера и запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="6eac1-124">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
