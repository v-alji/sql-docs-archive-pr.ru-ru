---
title: Соединение с сервером (страница "Свойства соединения") служб Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.connectionproperties.f1
ms.assetid: 26cf53e3-3bcb-4697-8a88-53e93bc68b56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 04706671ea8b0a50f2bf72cd7b73db88dce34d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727338"
---
# <a name="connect-to-server-connection-properties-page-analysis-services"></a><span data-ttu-id="58cb5-102">Соединение с сервером (страница «Свойства соединения») (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="58cb5-102">Connect to Server (Connection Properties Page) Analysis Services</span></span>
  <span data-ttu-id="58cb5-103">Эта вкладка используется для просмотра или указания параметров при подключении к [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] [!INCLUDE[ssAS](../includes/ssas-md.md)] **зарегистрированным серверам**или регистрации в них.</span><span class="sxs-lookup"><span data-stu-id="58cb5-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] or registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="58cb5-104">Кнопки**Соединить** и **Параметры** появляются в этом диалоговом окне только при соединении.</span><span class="sxs-lookup"><span data-stu-id="58cb5-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="58cb5-105">Кнопки**Проверить** и **Сохранить** появляются в этом диалоговом окне только при регистрации компонента [!INCLUDE[ssAS](../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58cb5-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssAS](../includes/ssas-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="58cb5-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="58cb5-106">Options</span></span>  
 <span data-ttu-id="58cb5-107">**Подключение к базе данных**</span><span class="sxs-lookup"><span data-stu-id="58cb5-107">**Connect to database**</span></span>  
 <span data-ttu-id="58cb5-108">Выберите базу данных для подключения из списка.</span><span class="sxs-lookup"><span data-stu-id="58cb5-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="58cb5-109">При выборе этого значения **\<default>** будет выполнено подключение к базе данных по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="58cb5-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="58cb5-110">При выборе можно **\<Browse server>** Просмотреть сервер для базы данных, к которой необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="58cb5-110">If you select **\<Browse server>**, you can browse the server for the database you would like to connect to.</span></span>  
  
 <span data-ttu-id="58cb5-111">**Время ожидания подключения**</span><span class="sxs-lookup"><span data-stu-id="58cb5-111">**Connection timeout**</span></span>  
 <span data-ttu-id="58cb5-112">Введите время ожидания (в секундах) до установки соединения. Значение по умолчанию — 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="58cb5-112">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="58cb5-113">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="58cb5-113">**Execution timeout**</span></span>  
 <span data-ttu-id="58cb5-114">Введите время ожидания в секундах до завершения выполнения задачи на сервере.</span><span class="sxs-lookup"><span data-stu-id="58cb5-114">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="58cb5-115">Значение по умолчанию равно 0. Это означает, что время ожидания не установлено.</span><span class="sxs-lookup"><span data-stu-id="58cb5-115">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="58cb5-116">**Шифровать соединение**</span><span class="sxs-lookup"><span data-stu-id="58cb5-116">**Encrypt connection**</span></span>  
 <span data-ttu-id="58cb5-117">Задает принудительное шифрование соединения.</span><span class="sxs-lookup"><span data-stu-id="58cb5-117">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="58cb5-118">**Сбросить все**</span><span class="sxs-lookup"><span data-stu-id="58cb5-118">**Reset All**</span></span>  
 <span data-ttu-id="58cb5-119">Заменить все введенные вручную значения свойств соединения значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58cb5-119">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="58cb5-120">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="58cb5-120">**Connect**</span></span>  
 <span data-ttu-id="58cb5-121">Выполнить попытку соединения, используя значения из списка.</span><span class="sxs-lookup"><span data-stu-id="58cb5-121">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="58cb5-122">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="58cb5-122">**Options**</span></span>  
 <span data-ttu-id="58cb5-123">Выберите этот пункт, чтобы изменить диалоговое окно и скрыть такие дополнительные параметры соединения сервера, как запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="58cb5-123">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="58cb5-124">**Тест**</span><span class="sxs-lookup"><span data-stu-id="58cb5-124">**Test**</span></span>  
 <span data-ttu-id="58cb5-125">При регистрации компонента [!INCLUDE[ssAS](../includes/ssas-md.md)] в списке **Зарегистрированные серверы**выберите этот параметр для проверки соединения.</span><span class="sxs-lookup"><span data-stu-id="58cb5-125">When registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="58cb5-126">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="58cb5-126">**Save**</span></span>  
 <span data-ttu-id="58cb5-127">Сохраняет параметры в списке **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="58cb5-127">Saves the settings in **Registered Servers**.</span></span>  
  
  
