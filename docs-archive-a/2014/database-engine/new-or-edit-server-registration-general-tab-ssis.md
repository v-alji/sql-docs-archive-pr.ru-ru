---
title: Создание или изменение регистрации сервера (вкладка «Общие») (службы SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.dts.f1
ms.assetid: b586b736-344b-4e42-83ee-96f66ad433a5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4968c3f98b8bab5b2e641e6fb1e30a6d682f9b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667876"
---
# <a name="new-or-edit-server-registration-general-tab-ssis"></a><span data-ttu-id="76e85-102">Создать или редактировать регистрацию сервера (вкладка «Общие») (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="76e85-102">New or Edit Server Registration (General Tab) (SSIS)</span></span>
  <span data-ttu-id="76e85-103">Используйте эту вкладку для задания параметров при регистрации служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e85-103">Use this tab to specify options when registering [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="76e85-104">Для доступа к этой странице щелкните **Службы Integration Services** на панели инструментов **Зарегистрированные серверы** , правой кнопкой мыши щелкните любую группу зарегистрированных серверов, выберите меню **Создать**, а затем пункт **Регистрация сервера**.</span><span class="sxs-lookup"><span data-stu-id="76e85-104">To access this page, in Registered Servers, click **Integration Services** on the **Registered Servers** toolbar, right-click any registered servers group, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76e85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76e85-105">Options</span></span>  
 <span data-ttu-id="76e85-106">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="76e85-106">**Server type**</span></span>  
 <span data-ttu-id="76e85-107">Если сервер зарегистрирован, поле **Тип сервера** предназначено только для чтения и соответствует типу сервера, отображаемого на панели "Зарегистрированные серверы".</span><span class="sxs-lookup"><span data-stu-id="76e85-107">When a server is registered in Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in Registered Servers.</span></span> <span data-ttu-id="76e85-108">Для регистрации другого типа сервера выберите **Ядро СУБД**, **Сервер анализа данных**, **Reporting Services**, **SQL Server Compact** **Выпуск** или **Integration Services** на панели инструментов **Зарегистрированные серверы** перед регистрацией нового сервера.</span><span class="sxs-lookup"><span data-stu-id="76e85-108">To register a different type of server, click **Database Engine**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="76e85-109">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="76e85-109">**Server name**</span></span>  
 <span data-ttu-id="76e85-110">Выберите сервер для подключения.</span><span class="sxs-lookup"><span data-stu-id="76e85-110">Select the server to which to connect.</span></span> <span data-ttu-id="76e85-111">По умолчанию выводится сервер, к которому выполнялось последнее подключение.</span><span class="sxs-lookup"><span data-stu-id="76e85-111">The server last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="76e85-112">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="76e85-112">**Authentication**</span></span>  
 <span data-ttu-id="76e85-113">Режим проверки подлинности Windows позволяет пользователям подключаться с помощью учетных записей [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="76e85-113">Windows Authentication mode allows a user to connect through a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="76e85-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="76e85-114">**User name**</span></span>  
 <span data-ttu-id="76e85-115">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="76e85-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="76e85-116">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="76e85-116">**Password**</span></span>  
 <span data-ttu-id="76e85-117">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="76e85-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="76e85-118">**Запоминание пароля**</span><span class="sxs-lookup"><span data-stu-id="76e85-118">**Remember password**</span></span>  
 <span data-ttu-id="76e85-119">Этот параметр недоступен в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="76e85-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="76e85-120">**Имя зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="76e85-120">**Registered server name**</span></span>  
 <span data-ttu-id="76e85-121">Имя, которое должно отображаться в списке « **Зарегистрированные серверы**».</span><span class="sxs-lookup"><span data-stu-id="76e85-121">The name you want to appear in **Registered Servers**.</span></span> <span data-ttu-id="76e85-122">Это имя не должно совпадать с именем, указанным в поле **Имя сервера** .</span><span class="sxs-lookup"><span data-stu-id="76e85-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="76e85-123">**Описание зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="76e85-123">**Registered server description**</span></span>  
 <span data-ttu-id="76e85-124">Введите необязательное описание сервера.</span><span class="sxs-lookup"><span data-stu-id="76e85-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="76e85-125">**Тест**</span><span class="sxs-lookup"><span data-stu-id="76e85-125">**Test**</span></span>  
 <span data-ttu-id="76e85-126">Нажмите для проверки соединения с сервером, заданным в поле **Имя сервера**.</span><span class="sxs-lookup"><span data-stu-id="76e85-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="76e85-127">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="76e85-127">**Save**</span></span>  
 <span data-ttu-id="76e85-128">Нажмите для сохранения настроек для зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="76e85-128">Click to save the Registered Servers settings.</span></span>  
  
  
