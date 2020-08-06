---
title: Соединение с сервером (страница "Свойства подключения") ядра СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttosqlserver.connectionproperties.f1
ms.assetid: edc1143c-6a47-4b02-92ab-441bdea8ea8a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 41f2aa3fd5004a371515ee5d8905c7bb73699829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739032"
---
# <a name="connect-to-server-connection-properties-page-database-engine"></a><span data-ttu-id="2ee37-102">Соединение с сервером (страница "Свойства подключения") ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="2ee37-102">Connect to Server (Connection Properties Page) Database Engine</span></span>
  <span data-ttu-id="2ee37-103">На этой вкладке можно просмотреть или задать параметры при подключении к экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] или регистрации компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в списке **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="2ee37-103">Use this tab to view or specify options when connecting to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or registering [!INCLUDE[ssDE](../../includes/ssde-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="2ee37-104">Кнопки**Соединить** и **Параметры** появляются в этом диалоговом окне только при соединении с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee37-104">**Connect** and **Options** only appear in this dialog box when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2ee37-105">Кнопки**Проверить** и **Сохранить** появляются в этом диалоговом окне только при регистрации компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee37-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ee37-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="2ee37-106">Options</span></span>  
 <span data-ttu-id="2ee37-107">**Подключение к базе данных**</span><span class="sxs-lookup"><span data-stu-id="2ee37-107">**Connect to database**</span></span>  
 <span data-ttu-id="2ee37-108">Выберите базу данных для подключения из списка.</span><span class="sxs-lookup"><span data-stu-id="2ee37-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="2ee37-109">При выборе этого значения **\<default>** будет выполнено подключение к базе данных по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="2ee37-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="2ee37-110">При выборе можно **\<Browse server>** Просмотреть сервер для базы данных, к которой необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="2ee37-110">If you select **\<Browse server>**, you can browse the server for the database to which to connect.</span></span>  
  
 <span data-ttu-id="2ee37-111">При соединении с экземпляром ядра СУБД [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] через [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]необходимо использовать проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и указать базу данных в диалоговом окне **Соединение с сервером** на вкладке **Свойства соединения** . Обязательно установите флажок **Шифрование соединения** .</span><span class="sxs-lookup"><span data-stu-id="2ee37-111">When connecting to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine through [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], you must use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication and specify a database in the **Connect to Server** dialog box, on the **Connection Properties** tab. Ensure that you select the **Encrypt connection** checkbox.</span></span>  
  
 <span data-ttu-id="2ee37-112">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] соединяется с базой данных **master**.</span><span class="sxs-lookup"><span data-stu-id="2ee37-112">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to **master**.</span></span> <span data-ttu-id="2ee37-113">Если указать пользовательскую базу данных, то в обозревателе объектов будет видна только эта база данных и ее объекты.</span><span class="sxs-lookup"><span data-stu-id="2ee37-113">If you specify a user database, you will only see that database and its objects in Object Explorer.</span></span> <span data-ttu-id="2ee37-114">Если соединиться с базой данных **master**, будут видны все базы данных.</span><span class="sxs-lookup"><span data-stu-id="2ee37-114">If you connect to **master**, you will be able to see all databases.</span></span> <span data-ttu-id="2ee37-115">Дополнительные сведения см. в статье [Общие сведения о базе данных SQL Azure](/azure/sql-database/sql-database-technical-overview).</span><span class="sxs-lookup"><span data-stu-id="2ee37-115">For more information, see the [Azure SQL Database Overview](/azure/sql-database/sql-database-technical-overview).</span></span>  
  
 <span data-ttu-id="2ee37-116">**Сетевой протокол**</span><span class="sxs-lookup"><span data-stu-id="2ee37-116">**Network protocol**</span></span>  
 <span data-ttu-id="2ee37-117">Выберите протокол из списка.</span><span class="sxs-lookup"><span data-stu-id="2ee37-117">Select a protocol from the list.</span></span> <span data-ttu-id="2ee37-118">Доступны те клиентские протоколы, которые настроены с помощью «Настройки сети клиента» в меню «Управление компьютером».</span><span class="sxs-lookup"><span data-stu-id="2ee37-118">The available client protocols are those that you configured using the Client Network Configuration in Computer Management.</span></span>  
  
 <span data-ttu-id="2ee37-119">**Размер сетевого пакета**</span><span class="sxs-lookup"><span data-stu-id="2ee37-119">**Network packet size**</span></span>  
 <span data-ttu-id="2ee37-120">Введите размер пакетов, отправляемых по сети.</span><span class="sxs-lookup"><span data-stu-id="2ee37-120">Enter the size of the network packets to be sent.</span></span> <span data-ttu-id="2ee37-121">Значение по умолчанию равно 4096 байт.</span><span class="sxs-lookup"><span data-stu-id="2ee37-121">The default is 4096 bytes.</span></span>  
  
 <span data-ttu-id="2ee37-122">**Время ожидания подключения**</span><span class="sxs-lookup"><span data-stu-id="2ee37-122">**Connection timeout**</span></span>  
 <span data-ttu-id="2ee37-123">Введите время ожидания (в секундах) до установки соединения. Значение по умолчанию — 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="2ee37-123">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="2ee37-124">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="2ee37-124">**Execution timeout**</span></span>  
 <span data-ttu-id="2ee37-125">Введите время ожидания в секундах до завершения выполнения задачи на сервере.</span><span class="sxs-lookup"><span data-stu-id="2ee37-125">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="2ee37-126">Значение по умолчанию равно 0. Это означает, что время ожидания не установлено.</span><span class="sxs-lookup"><span data-stu-id="2ee37-126">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="2ee37-127">**Шифровать соединение**</span><span class="sxs-lookup"><span data-stu-id="2ee37-127">**Encrypt connection**</span></span>  
 <span data-ttu-id="2ee37-128">Задает принудительное шифрование соединения.</span><span class="sxs-lookup"><span data-stu-id="2ee37-128">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="2ee37-129">**Использовать пользовательский цвет**</span><span class="sxs-lookup"><span data-stu-id="2ee37-129">**Use custom color**</span></span>  
 <span data-ttu-id="2ee37-130">Выберите, чтобы указать цвет фона для строки состояния в окне редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ee37-130">Select to specify the background color for the status bar in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="2ee37-131">Чтобы указать цвет, нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="2ee37-131">To specify the color, click **Select**.</span></span> <span data-ttu-id="2ee37-132">В диалоговом окне **Цвет** выберите стандартный цвет в сетке **Основные цвета** или нажмите кнопку **Определить цвет** , чтобы определить и применить пользовательский цвет.</span><span class="sxs-lookup"><span data-stu-id="2ee37-132">In the **Color** dialog box, select a predefined color from the **Basic Colors** grid or click **Define Custom Colors** to define and use a custom color.</span></span>  
  
-   <span data-ttu-id="2ee37-133">Если указан цвет для записи сервера на панели **Обозреватель объектов** , он используется при открытии окна "Редактор запросов".</span><span class="sxs-lookup"><span data-stu-id="2ee37-133">When you specify a color for a server entry in the **Object Explorer** pane, that color is used when you open a Query Editor window.</span></span> <span data-ttu-id="2ee37-134">Чтобы открыть окно "Редактор запросов", щелкните правой кнопкой мыши запись сервера и выберите команду **Создать запрос**или, если область **Обозреватель объектов** активна и в ее фокусе находится требуемый сервер, нажмите кнопку **Создать запрос** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="2ee37-134">To open a Query Editor window, either right-click the server entry and select **New Query**; or, when the **Object Explorer** pane is active and focused on this server, click **New Query** on the toolbar.</span></span>  
  
-   <span data-ttu-id="2ee37-135">Если указан цвет для записи сервера на панели **Зарегистрированные серверы** , он используется при открытии окна редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="2ee37-135">When you specify a color for a server entry in the **Registered Servers** pane, that color is used when you open a Query Editor window.</span></span> <span data-ttu-id="2ee37-136">Чтобы открыть окно редактора запросов, щелкните правой кнопкой мыши запись сервера и выберите команду **Создать запрос**или, если область **Зарегистрированный сервер** активна и в ее фокусе находится требуемый сервер, нажмите кнопку **Создать запрос** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="2ee37-136">To open a Query Editor window, either right-click the server entry and select **New Query**; or, when the **Registered Server** pane is active and focused on this server, click **New Query** on the toolbar.</span></span>  
  
-   <span data-ttu-id="2ee37-137">В меню **Файл** после выбора команд **Создать** и **Запрос ядра СУБД**цвет, указанный в диалоговом окне **Соединение с сервером** , применяется к окну редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="2ee37-137">On the **File** menu, when you click **New** and then **Database Engine Query**, the color you that you specify in the **Connect to Server** dialog box applies to that Query Editor window.</span></span>  
  
 <span data-ttu-id="2ee37-138">**Сбросить все**</span><span class="sxs-lookup"><span data-stu-id="2ee37-138">**Reset All**</span></span>  
 <span data-ttu-id="2ee37-139">Заменяет все значения введенных вручную свойств соединения значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ee37-139">Replace all manually entered connection property values with their defaults.</span></span>  
  
 <span data-ttu-id="2ee37-140">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="2ee37-140">**Connect**</span></span>  
 <span data-ttu-id="2ee37-141">Выполнить попытку соединения, используя значения из списка.</span><span class="sxs-lookup"><span data-stu-id="2ee37-141">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="2ee37-142">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="2ee37-142">**Options**</span></span>  
 <span data-ttu-id="2ee37-143">Нажмите, чтобы изменить вид диалогового окна и скрыть дополнительные параметры соединения с сервером (такие как «Запомнить пароль»).</span><span class="sxs-lookup"><span data-stu-id="2ee37-143">Click to change the dialog box and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="2ee37-144">**Тест**</span><span class="sxs-lookup"><span data-stu-id="2ee37-144">**Test**</span></span>  
 <span data-ttu-id="2ee37-145">При регистрации компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в списке **Зарегистрированные серверы**выберите этот параметр для проверки соединения.</span><span class="sxs-lookup"><span data-stu-id="2ee37-145">When registering [!INCLUDE[ssDE](../../includes/ssde-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="2ee37-146">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="2ee37-146">**Save**</span></span>  
 <span data-ttu-id="2ee37-147">Сохраняет параметры в списке **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="2ee37-147">Saves the settings in **Registered Servers**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee37-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ee37-148">See Also</span></span>  
 [<span data-ttu-id="2ee37-149">диалоговое окно «Свойства соединения»</span><span class="sxs-lookup"><span data-stu-id="2ee37-149">Connection Properties Dialog Box</span></span>](../../database-engine/connection-properties-dialog-box.md)  
  
  
