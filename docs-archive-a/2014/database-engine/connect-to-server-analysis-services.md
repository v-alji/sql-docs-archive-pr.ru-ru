---
title: Соединение с сервером (службы Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.analysisserver.f1
ms.assetid: 7e277d22-8d4b-422e-8882-7c5dd7a6d915
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3530f38534e09ef19e77293880129274dfc211b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727342"
---
# <a name="connect-to-server-analysis-services"></a><span data-ttu-id="2f3cf-102">Соединение с сервером (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="2f3cf-102">Connect to Server (Analysis Services)</span></span>
  <span data-ttu-id="2f3cf-103">Используйте это диалоговое окно для просмотра или настройки параметров при подключении к [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f3cf-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="2f3cf-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f3cf-104">Options</span></span>  
 <span data-ttu-id="2f3cf-105">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-105">**Server type**</span></span>  
 <span data-ttu-id="2f3cf-106">При регистрации сервера из обозревателя объектов выберите тип сервера для подключения: [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="2f3cf-107">В остальной части диалогового окна показаны параметры, которые применяются только к выбранному типу сервера.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="2f3cf-108">При регистрации сервера c панели "Зарегистрированные серверы" поле **Тип сервера** не может быть изменено и совпадает с типом сервера, показанного в компоненте "Зарегистрированные серверы".</span><span class="sxs-lookup"><span data-stu-id="2f3cf-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="2f3cf-109">Чтобы зарегистрировать другой тип сервера, выберите компонент [!INCLUDE[ssDE](../includes/ssde-md.md)], службы Analysis Services, службы Reporting Services или службы Integration Services на панели инструментов «Зарегистрированные серверы», прежде чем начать регистрацию нового сервера.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="2f3cf-110">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-110">**Server name**</span></span>  
 <span data-ttu-id="2f3cf-111">Выберите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-111">Select the server instance to connect to.</span></span> <span data-ttu-id="2f3cf-112">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="2f3cf-113">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-113">**Authentication**</span></span>  
 <span data-ttu-id="2f3cf-114">При подключении к экземпляру службы Analysis Services поддерживаются следующие режимы проверки подлинности: проверка подлинности [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="2f3cf-115">**Режим проверки подлинности Windows (проверка подлинности Windows)**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="2f3cf-116">Режим **проверки подлинности Windows** позволяет пользователю подключаться с помощью учетной записи пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-116">**Windows Authentication** mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="2f3cf-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-117">**User name**</span></span>  
 <span data-ttu-id="2f3cf-118">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-118">This option is not available in this release.</span></span> <span data-ttu-id="2f3cf-119">Введите имя пользователя для соединения.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-119">Enter the user name to connect with.</span></span> <span data-ttu-id="2f3cf-120">Этот параметр доступен только в случае выбора режима **Проверка подлинности Windows**для подключения.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-120">This option is only available if you have selected to connect using **Windows Authentication**.</span></span>  
  
 <span data-ttu-id="2f3cf-121">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-121">**Password**</span></span>  
 <span data-ttu-id="2f3cf-122">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-122">This option is not available in this release.</span></span> <span data-ttu-id="2f3cf-123">Введите пароль для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-123">Enter the password for the login.</span></span> <span data-ttu-id="2f3cf-124">Этот параметр доступен для редактирования только при подключении с проверкой подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f3cf-124">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="2f3cf-125">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-125">**Connect**</span></span>  
 <span data-ttu-id="2f3cf-126">Нажмите, чтобы подключиться к выбранному выше серверу.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-126">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="2f3cf-127">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="2f3cf-127">**Options**</span></span>  
 <span data-ttu-id="2f3cf-128">Нажмите, чтобы вывести дополнительные параметры соединения с сервером, такие как регистрация сервера и запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="2f3cf-128">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
