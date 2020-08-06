---
title: Подключение к серверу (страница «Свойства подключения») Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodts.connectionproperties.f1
- sql12.ssiseditserverregistration.connectionproperties.f1
ms.assetid: c2513dab-8415-4e0c-9475-6d4ab97fea7c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 05f3d370a3f3a299bb90df53538b3fa3e90e28c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740376"
---
# <a name="connect-to-server-connection-properties-page-integration-services"></a><span data-ttu-id="b4f1a-102">Соединение с сервером (страница «Свойства соединения») — службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="b4f1a-102">Connect to Server (Connection Properties Page) Integration Services</span></span>
  <span data-ttu-id="b4f1a-103">Эта вкладка используется для просмотра или указания параметров при подключении к [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] [!INCLUDE[ssIS](../includes/ssis-md.md)] **зарегистрированным серверам**или регистрации в них.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] or registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="b4f1a-104">Кнопки**Соединить** и **Параметры** появляются в этом диалоговом окне только при соединении.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="b4f1a-105">Кнопки**Проверить** и **Сохранить** появляются в этом диалоговом окне только при регистрации компонента [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4f1a-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b4f1a-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="b4f1a-106">Options</span></span>  
 <span data-ttu-id="b4f1a-107">**Номер порта**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-107">**Port number**</span></span>  
 <span data-ttu-id="b4f1a-108">Введите номер порта, используемого службами [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4f1a-108">Enter the port number used by [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="b4f1a-109">**Время ожидания подключения**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-109">**Connection time-out**</span></span>  
 <span data-ttu-id="b4f1a-110">Введите время ожидания (в секундах) до установки соединения. Значение по умолчанию — 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-110">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="b4f1a-111">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-111">**Execution time-out**</span></span>  
 <span data-ttu-id="b4f1a-112">Введите время ожидания в секундах до завершения выполнения задачи на сервере.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-112">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="b4f1a-113">Значение по умолчанию равно 0. Это означает, что время ожидания не установлено.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-113">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="b4f1a-114">**Сбросить все**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-114">**Reset All**</span></span>  
 <span data-ttu-id="b4f1a-115">Заменить все введенные вручную значения свойств соединения значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-115">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="b4f1a-116">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-116">**Connect**</span></span>  
 <span data-ttu-id="b4f1a-117">Выполнить попытку соединения, используя значения из списка.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-117">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="b4f1a-118">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-118">**Options**</span></span>  
 <span data-ttu-id="b4f1a-119">Выберите этот пункт, чтобы изменить диалоговое окно и скрыть такие дополнительные параметры соединения сервера, как запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-119">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="b4f1a-120">**Тест**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-120">**Test**</span></span>  
 <span data-ttu-id="b4f1a-121">При регистрации компонента [!INCLUDE[ssIS](../includes/ssis-md.md)] в списке **Зарегистрированные серверы**выберите этот параметр для проверки соединения.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-121">When registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="b4f1a-122">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="b4f1a-122">**Save**</span></span>  
 <span data-ttu-id="b4f1a-123">Сохраняет параметры в списке **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="b4f1a-123">Saves the settings in **Registered Servers**.</span></span>  
  
  
