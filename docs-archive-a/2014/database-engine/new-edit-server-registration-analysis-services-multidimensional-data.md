---
title: Создание или изменение регистрации сервера (вкладка «Общие») (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.analysisservices.f1
ms.assetid: ca6aed42-8940-4f41-beb7-619e084cd850
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cc768a2c4fd6375ecee40ccf40e462bbe4213d8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667885"
---
# <a name="new-or-edit-server-registration-general-tab-analysis-services---multidimensional-data"></a><span data-ttu-id="b0a48-102">Новая регистрация для сервера или изменение данных регистрации серверов (вкладка «Общие») (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="b0a48-102">New or Edit Server Registration (General Tab) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b0a48-103">В этой вкладке указываются параметры при регистрации экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0a48-103">Use this tab to specify options when registering an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b0a48-104">Чтобы открыть эту страницу, на панели инструментов "Зарегистрированные серверы" в окне "Зарегистрированные серверы" нажмите кнопку **Службы Analysis Services** , щелкните правой кнопкой мыши любую группу зарегистрированных серверов, например **Службы Analysis Services**, наведите указатель на пункт **Создать**и выберите пункт **Регистрация сервера**.</span><span class="sxs-lookup"><span data-stu-id="b0a48-104">To access this page, in Registered Servers click **Analysis Services** on the Registered Servers toolbar, right-click any registered servers group, such as **Analysis Services**, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0a48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0a48-105">Options</span></span>  
 <span data-ttu-id="b0a48-106">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="b0a48-106">**Server type**</span></span>  
 <span data-ttu-id="b0a48-107">При регистрации сервера из окна "Зарегистрированные серверы" поле **Тип сервера** доступно только для чтения и соответствует типу сервера, который выводится на панели "Зарегистрированные серверы".</span><span class="sxs-lookup"><span data-stu-id="b0a48-107">When a server is registered from Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in the Registered Servers pane.</span></span> <span data-ttu-id="b0a48-108">Чтобы зарегистрировать другой тип сервера, щелкните нужный сервер на панели инструментов **Зарегистрированные серверы** , прежде чем регистрировать новый сервер.</span><span class="sxs-lookup"><span data-stu-id="b0a48-108">To register a different type of server, click the server you want on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="b0a48-109">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="b0a48-109">**Server name**</span></span>  
 <span data-ttu-id="b0a48-110">Выберите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="b0a48-110">Select the server instance to connect to.</span></span> <span data-ttu-id="b0a48-111">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="b0a48-111">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="b0a48-112">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="b0a48-112">**Authentication**</span></span>  
 <span data-ttu-id="b0a48-113">Проверка подлинности Windows позволяет пользователю подключиться с использованием своих учетных данных [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows как пользователь Windows или член группы Windows.</span><span class="sxs-lookup"><span data-stu-id="b0a48-113">Windows Authentication allows a user to connect using their [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows credentials, as a Windows user or as a member of a Windows group.</span></span>  
  
 <span data-ttu-id="b0a48-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="b0a48-114">**User name**</span></span>  
 <span data-ttu-id="b0a48-115">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="b0a48-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="b0a48-116">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="b0a48-116">**Password**</span></span>  
 <span data-ttu-id="b0a48-117">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="b0a48-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="b0a48-118">**Запоминание пароля**</span><span class="sxs-lookup"><span data-stu-id="b0a48-118">**Remember password**</span></span>  
 <span data-ttu-id="b0a48-119">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="b0a48-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="b0a48-120">**Имя зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="b0a48-120">**Registered server name**</span></span>  
 <span data-ttu-id="b0a48-121">Имя, которое будет отображаться на панели «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="b0a48-121">The name you want to appear in Registered Servers.</span></span> <span data-ttu-id="b0a48-122">Это имя не должно совпадать с именем, указанным в поле **Имя сервера** .</span><span class="sxs-lookup"><span data-stu-id="b0a48-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="b0a48-123">**Описание зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="b0a48-123">**Registered server description**</span></span>  
 <span data-ttu-id="b0a48-124">Введите необязательное описание сервера.</span><span class="sxs-lookup"><span data-stu-id="b0a48-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="b0a48-125">**Тест**</span><span class="sxs-lookup"><span data-stu-id="b0a48-125">**Test**</span></span>  
 <span data-ttu-id="b0a48-126">Нажмите для проверки соединения с сервером, заданным в поле **Имя сервера**.</span><span class="sxs-lookup"><span data-stu-id="b0a48-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="b0a48-127">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="b0a48-127">**Save**</span></span>  
 <span data-ttu-id="b0a48-128">Нажмите эту кнопку, чтобы сохранить настройки зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="b0a48-128">Click to save the registered server settings.</span></span>  
  
  
