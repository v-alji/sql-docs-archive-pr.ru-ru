---
title: Редактор диспетчера соединений WMI | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmiconnection.f1
helpviewer_keywords:
- WMI Connection Manager Editor
ms.assetid: 0ef2c913-0779-4a07-989e-3361cd83170b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e85cdd2157c8ebe4cb9e6b53f8c3b47ff102a7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667772"
---
# <a name="wmi-connection-manager-editor"></a><span data-ttu-id="dfc54-102">редактор диспетчера WMI-сеансов</span><span class="sxs-lookup"><span data-stu-id="dfc54-102">WMI Connection Manager Editor</span></span>
  <span data-ttu-id="dfc54-103">Диалоговое окно **Диспетчер WMI-соединений** позволяет выбрать соединение инструментария управления Windows (Microsoft WMI) к серверу.</span><span class="sxs-lookup"><span data-stu-id="dfc54-103">Use the **WMI Connection Manager** dialog box to specify a Microsoft Windows Management Instrumentation (WMI) connection to a server.</span></span>  
  
 <span data-ttu-id="dfc54-104">Дополнительные сведения о диспетчере WMI-сеансов см. в разделе [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dfc54-104">To learn more about the WMI connection manager, see [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dfc54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfc54-105">Options</span></span>  
 <span data-ttu-id="dfc54-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="dfc54-106">**Name**</span></span>  
 <span data-ttu-id="dfc54-107">Задает уникальное имя диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="dfc54-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="dfc54-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dfc54-108">**Description**</span></span>  
 <span data-ttu-id="dfc54-109">Задайте описание диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="dfc54-109">Describe the connection manager.</span></span> <span data-ttu-id="dfc54-110">Рекомендуется описать назначение диспетчера соединений, чтобы сделать пакеты самодокументируемыми и более простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="dfc54-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="dfc54-111">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="dfc54-111">**Server name**</span></span>  
 <span data-ttu-id="dfc54-112">Введите имя сервера, с которым требуется установить WMI-сеанс.</span><span class="sxs-lookup"><span data-stu-id="dfc54-112">Provide the name of the server to which you want to make the WMI connection.</span></span>  
  
 <span data-ttu-id="dfc54-113">**Пространство имен**</span><span class="sxs-lookup"><span data-stu-id="dfc54-113">**Namespace**</span></span>  
 <span data-ttu-id="dfc54-114">Укажите пространство имен инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="dfc54-114">Specify the WMI namespace.</span></span>  
  
 <span data-ttu-id="dfc54-115">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="dfc54-115">**Use Windows authentication**</span></span>  
 <span data-ttu-id="dfc54-116">Выберите этот режим для проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="dfc54-116">Select to use Windows Authentication.</span></span> <span data-ttu-id="dfc54-117">При использовании проверки подлинности Windows не будет необходимости ввода имени пользователя и пароля для установки соединения.</span><span class="sxs-lookup"><span data-stu-id="dfc54-117">If you use Windows Authentication, you do not need to provide a user name or password for the connection.</span></span>  
  
 <span data-ttu-id="dfc54-118">**User name**</span><span class="sxs-lookup"><span data-stu-id="dfc54-118">**User name**</span></span>  
 <span data-ttu-id="dfc54-119">Если проверка подлинности Windows не используется, необходимо ввести имя пользователя для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="dfc54-119">If you do not use Windows Authentication, you must provide a user name for the connection.</span></span>  
  
 <span data-ttu-id="dfc54-120">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="dfc54-120">**Password**</span></span>  
 <span data-ttu-id="dfc54-121">Если проверка подлинности Windows не используется, необходимо ввести пароль для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="dfc54-121">If you do not use Windows Authentication, you must provide the password for the connection.</span></span>  
  
 <span data-ttu-id="dfc54-122">**Тест**</span><span class="sxs-lookup"><span data-stu-id="dfc54-122">**Test**</span></span>  
 <span data-ttu-id="dfc54-123">Проверка настроек диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="dfc54-123">Test the connection manager settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc54-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfc54-124">See Also</span></span>  
 <span data-ttu-id="dfc54-125">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dfc54-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="dfc54-126">[Основные понятия о поставщике WMI для управления конфигурацией](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="dfc54-126">[WMI Provider for Configuration Management Concepts](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="dfc54-127">Основные понятия о поставщике WMI для событий сервера</span><span class="sxs-lookup"><span data-stu-id="dfc54-127">WMI Provider for Server Events Concepts</span></span>](../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)  
  
  
