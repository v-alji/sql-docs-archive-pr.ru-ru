---
title: Параметры (страница «результаты запроса и службы зависимостей») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.DependencyServicesGeneral
ms.assetid: dd7f6c31-7d7f-4972-854a-1419a2826dca
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 356714ee933fb40eda7038f4088309b6187f3ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667395"
---
# <a name="options-query-results-and-dependency-services-page"></a><span data-ttu-id="35061-102">Параметры ("Результаты запроса" и страница "Службы зависимостей")</span><span class="sxs-lookup"><span data-stu-id="35061-102">Options (Query Results and Dependency Services Page)</span></span>
  <span data-ttu-id="35061-103">Используйте эту страницу, чтобы указать сервер для подключения к службам зависимостей.</span><span class="sxs-lookup"><span data-stu-id="35061-103">Use this page to specify the server to connect for Dependency Services.</span></span> <span data-ttu-id="35061-104">Службы зависимостей позволяют извлекать данные о зависимостях между объектами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], сохраненными на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="35061-104">Dependency Services enables you to extract information about dependencies between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects stored on different servers.</span></span> <span data-ttu-id="35061-105">Просмотреть зависимости объектов можно с помощью диалогового окна « **зависимости объектов** » в среде [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35061-105">You view object dependencies by using the **Object Dependencies** dialog box in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="35061-106">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="35061-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="35061-107">Откройте диалоговое окно «Параметры» (страницу результатов запроса или служб зависимостей)</span><span class="sxs-lookup"><span data-stu-id="35061-107">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="35061-108">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="35061-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-options-query-resultsdependency-services-page-dialog-box"></a><a name="open_dialog"></a><span data-ttu-id="35061-109">Открытие диалогового окна «Параметры» (страница «результаты запроса/службы зависимостей»)</span><span class="sxs-lookup"><span data-stu-id="35061-109">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>  
  
1.  <span data-ttu-id="35061-110">В выберите [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] пункт **Параметры** в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="35061-110">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="35061-111">Разверните **Результаты запроса** и нажмите кнопку **Службы зависимостей**.</span><span class="sxs-lookup"><span data-stu-id="35061-111">Expand **Query Results**, and then click **Dependency Services**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="35061-112">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="35061-112">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="35061-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="35061-113">Options</span></span>  
 <span data-ttu-id="35061-114">**Сервер служб зависимостей**</span><span class="sxs-lookup"><span data-stu-id="35061-114">**Dependency Services server**</span></span>  
 <span data-ttu-id="35061-115">Укажите сервер, на котором установлены службы зависимостей.</span><span class="sxs-lookup"><span data-stu-id="35061-115">Specify the server that Dependency Services is installed on.</span></span>  
  
 <span data-ttu-id="35061-116">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="35061-116">**Authentication**</span></span>  
 <span data-ttu-id="35061-117">Выберите проверку подлинности Windows, чтобы войти в систему с использованием учетной записи Microsoft Windows, или выберите проверку подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35061-117">Select Windows Authentication to log on using a Microsoft Windows user account, or select SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="35061-118">При подключении пользователя с указанным именем и паролем через недоверенное соединение, SQL Server выполняет проверку подлинности посредством проверки настройки учетной записи входа SQL Server и совпадения указанного пароля с предварительно сохраненными.</span><span class="sxs-lookup"><span data-stu-id="35061-118">When a user connects with a specified login name and password from a non-trusted connection, SQL Server performs the authentication by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="35061-119">Если SQL Server не может найти такое имя входа, проверка подлинности прекращается и пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="35061-119">If SQL Server cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="35061-120">**User name**</span><span class="sxs-lookup"><span data-stu-id="35061-120">**User name**</span></span>  
 <span data-ttu-id="35061-121">При использовании проверки подлинности SQL Server укажите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="35061-121">If using SQL Server Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="35061-122">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="35061-122">**Password**</span></span>  
 <span data-ttu-id="35061-123">При использовании проверки подлинности SQL Server укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="35061-123">If using SQL Server Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="35061-124">**Тест**</span><span class="sxs-lookup"><span data-stu-id="35061-124">**Test**</span></span>  
 <span data-ttu-id="35061-125">Щелкните, чтобы проверить соединение.</span><span class="sxs-lookup"><span data-stu-id="35061-125">Click to test the connection.</span></span>