---
title: Альтернативные способы подключения к данным (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aebc5f3d-97d5-4d54-b525-753fed073a9a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2be693469318172b2a55fbcb17b33e1deaaed3df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656257"
---
# <a name="alternative-ways-to-get-a-data-connection-report-builder"></a><span data-ttu-id="84063-102">Альтернативные способы создания подключения к данным (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="84063-102">Alternative Ways to Get a Data Connection (Report Builder)</span></span>
  <span data-ttu-id="84063-103">Подключение к данным содержит сведения, необходимые для подключения к внешнему источнику данных, например к базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84063-103">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="84063-104">Обычно сведения о соединении и учетные данные, которые будут использоваться при соединении с источником данных, можно получить у владельца источника данных.</span><span class="sxs-lookup"><span data-stu-id="84063-104">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span>  
  
 <span data-ttu-id="84063-105">Чтобы указать подключение к данным, можно воспользоваться общим источником данных с сервера отчетов или создать внедренный источник данных, используемый только в отдельном отчете.</span><span class="sxs-lookup"><span data-stu-id="84063-105">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in a specific report.</span></span>  
  
 <span data-ttu-id="84063-106">В большинстве учебников используются внедренные источники данных, но при наличии доступа к общим источникам данных можно воспользоваться и ими.</span><span class="sxs-lookup"><span data-stu-id="84063-106">In most tutorials you use embedded data sources, but if you have access to shared data sources, then you can use them instead.</span></span>  
  
## <a name="getting-a-data-connection-from-a-shared-data-source"></a><span data-ttu-id="84063-107">Создание подключения к данным из общего источника данных</span><span class="sxs-lookup"><span data-stu-id="84063-107">Getting a Data Connection From a Shared Data Source</span></span>  
 <span data-ttu-id="84063-108">Если на сервере отчетов имеется доступный общий источник данных, для использования которого достаточно прав, можно использовать его вместо внедренного источника данных.</span><span class="sxs-lookup"><span data-stu-id="84063-108">If the report server has available shared data source that you have permissions to use, you can use them instead of an embedded data source.</span></span> <span data-ttu-id="84063-109">В следующей процедуре описан поиск общих источников данных и ввод учетных данных, необходимых для их использования.</span><span class="sxs-lookup"><span data-stu-id="84063-109">The following procedures tell how to locate the shared data sources and provide any credentials needed to use them.</span></span>  
  
 <span data-ttu-id="84063-110">Чтобы воспользоваться общим источником данных, необходимо перейти к серверу отчетов и выбрать источник.</span><span class="sxs-lookup"><span data-stu-id="84063-110">To use a shared data source, you must browse to a report server and select one.</span></span> <span data-ttu-id="84063-111">Обычно URL-адрес сервера отчетов можно получить у администратора сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="84063-111">Usually, you get the report server URL from the report server administrator.</span></span>  
  
#### <a name="to-specify-a-data-connection-from-a-list-of-shared-data-sources"></a><span data-ttu-id="84063-112">Выбор подключения к данным из списка общих источников данных</span><span class="sxs-lookup"><span data-stu-id="84063-112">To specify a data connection from a list of shared data sources</span></span>  
  
1.  <span data-ttu-id="84063-113">На странице **Выбор набора данных** выберите команду **Создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84063-113">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="84063-114">Откроется страница **Выберите соединение с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="84063-114">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="84063-115">В списке источников данных выберите источник, на доступ к которому имеется разрешение.</span><span class="sxs-lookup"><span data-stu-id="84063-115">From the list of data sources, select a data source that you have permission to access.</span></span>  
  
3.  <span data-ttu-id="84063-116">Нажмите кнопку **Проверить соединение**, чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="84063-116">To verify that you can connect to the data source, click **Test Connection**.</span></span> <span data-ttu-id="84063-117">Отобразится сообщение «Соединение установлено успешно».</span><span class="sxs-lookup"><span data-stu-id="84063-117">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="84063-118">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84063-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="84063-119">При необходимости введите учетные данные.</span><span class="sxs-lookup"><span data-stu-id="84063-119">If necessary, enter your credentials.</span></span> <span data-ttu-id="84063-120">Чтобы сохранить учетные данные локально, установите флажок **Сохранить пароль с соединением**.</span><span class="sxs-lookup"><span data-stu-id="84063-120">To save the credentials locally, select **Save password with connection**.</span></span> <span data-ttu-id="84063-121">Если этот параметр не выбран, ввод учетных данных будет требоваться каждый раз при запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="84063-121">If you not select this option, you will be prompted for credentials every time that you run the report</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-specify-a-data-connection-by-browsing-to-a-shared-data-source-on-a-report-server"></a><span data-ttu-id="84063-122">Указание подключения к данным путем выбора общего источника данных на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="84063-122">To specify a data connection by browsing to a shared data source on a report server</span></span>  
  
1.  <span data-ttu-id="84063-123">На странице **Выбор набора данных** выберите команду **Создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84063-123">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="84063-124">Откроется страница **Выберите соединение с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="84063-124">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="84063-125">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="84063-125">Click **Browse**.</span></span> <span data-ttu-id="84063-126">Откроется диалоговое окно **Выбор источника данных** .</span><span class="sxs-lookup"><span data-stu-id="84063-126">The **Select Data Source** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="84063-127">В раскрывающемся списке **Папка** выберите пункт **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="84063-127">From the **Look in** drop-down list, select **Recent Sites and Servers**.</span></span> <span data-ttu-id="84063-128">На панели источника данных щелкните URL-адрес сервера и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="84063-128">In the data source pane, click the URL for your server, and then click **Open**.</span></span>  
  
     <span data-ttu-id="84063-129">Отобразится список источников данных или моделей.</span><span class="sxs-lookup"><span data-stu-id="84063-129">The list of data sources or models appears.</span></span>  
  
4.  <span data-ttu-id="84063-130">Либо в поле **Имя**введите URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="84063-130">Alternatively, in **Name**, type the URL to the report server.</span></span> <span data-ttu-id="84063-131">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="84063-131">Click **Open**.</span></span>  
  
     <span data-ttu-id="84063-132">Построитель отчетов подключится к серверу отчетов и загрузит источники данных, доступные в корневой папке.</span><span class="sxs-lookup"><span data-stu-id="84063-132">Report Builder connects to the report server and loads the data sources that are available at the root folder.</span></span>  
  
5.  <span data-ttu-id="84063-133">Перейдите к папке, содержащей источник данных, на подключение к которому имеются разрешения, выберите источник данных и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="84063-133">Navigate to a folder that contains a data source that you have sufficient permissions to connect to, select the data source, and then click **Open**.</span></span>  
  
     <span data-ttu-id="84063-134">Снова откроется страница **Выбор соединения с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="84063-134">You are back on the **Choose a connection to a data source** page.</span></span>  
  
6.  <span data-ttu-id="84063-135">Нажмите кнопку **Проверить соединение**, чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="84063-135">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="84063-136">Отобразится сообщение «Соединение установлено успешно».</span><span class="sxs-lookup"><span data-stu-id="84063-136">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="84063-137">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="84063-137">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="84063-138">При запросе имени пользователя и пароля введите учетные данные.</span><span class="sxs-lookup"><span data-stu-id="84063-138">If you are prompted for a user name and password, enter your credentials.</span></span> <span data-ttu-id="84063-139">Чтобы сохранить учетные данные локально, установите флажок **Сохранить пароль с соединением**.</span><span class="sxs-lookup"><span data-stu-id="84063-139">To save the credentials locally, select **Save password with connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84063-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="84063-140">See Also</span></span>  
 <span data-ttu-id="84063-141">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="84063-141">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="84063-142">Учебники &#40;построитель отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="84063-142">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
