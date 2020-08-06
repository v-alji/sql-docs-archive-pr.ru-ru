---
title: Соединение с сервером (страница входа) — службы Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.login.f1
ms.assetid: fb012bc8-5105-438a-afcc-74264ebae035
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0cdbb890693c6f00d8515194804b96b6483cb956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740367"
---
# <a name="connect-to-server-login-page-analysis-services"></a><span data-ttu-id="0ea98-102">Соединение с сервером (страница входа) — службы Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0ea98-102">Connect to Server (Login Page) Analysis Services</span></span>
  <span data-ttu-id="0ea98-103">Эта вкладка используется для просмотра или указания следующих параметров при соединении с [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea98-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ea98-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ea98-104">Options</span></span>  
 <span data-ttu-id="0ea98-105">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="0ea98-105">**Server type**</span></span>  
 <span data-ttu-id="0ea98-106">При регистрации сервера из обозревателя объектов выберите тип сервера для подключения: [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services.</span><span class="sxs-lookup"><span data-stu-id="0ea98-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="0ea98-107">В остальной части диалогового окна показаны параметры, которые применяются только к выбранному типу сервера.</span><span class="sxs-lookup"><span data-stu-id="0ea98-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="0ea98-108">При регистрации сервера c панели "Зарегистрированные серверы" поле **Тип сервера** не может быть изменено и совпадает с типом сервера, показанного в компоненте "Зарегистрированные серверы".</span><span class="sxs-lookup"><span data-stu-id="0ea98-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="0ea98-109">Чтобы зарегистрировать другой тип сервера, выберите компонент [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services на панели инструментов «Зарегистрированные серверы», прежде чем начать регистрацию нового сервера.</span><span class="sxs-lookup"><span data-stu-id="0ea98-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="0ea98-110">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="0ea98-110">**Server name**</span></span>  
 <span data-ttu-id="0ea98-111">Выберите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="0ea98-111">Select the server instance to connect to.</span></span> <span data-ttu-id="0ea98-112">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="0ea98-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="0ea98-113">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="0ea98-113">**Authentication**</span></span>  
 <span data-ttu-id="0ea98-114">При подключении к экземпляру службы Analysis Services поддерживаются следующие режимы проверки подлинности: проверка подлинности [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="0ea98-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="0ea98-115">**Режим проверки подлинности Windows (проверка подлинности Windows)**</span><span class="sxs-lookup"><span data-stu-id="0ea98-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="0ea98-116">Режим проверки подлинности Windows позволяет подключаться с учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="0ea98-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="0ea98-117">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="0ea98-117">**Connect**</span></span>  
 <span data-ttu-id="0ea98-118">Подключиться к выбранному выше серверу.</span><span class="sxs-lookup"><span data-stu-id="0ea98-118">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="0ea98-119">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="0ea98-119">**Options**</span></span>  
 <span data-ttu-id="0ea98-120">Выберите этот пункт, чтобы изменить диалоговое окно и скрыть такие дополнительные параметры соединения сервера, как запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="0ea98-120">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
