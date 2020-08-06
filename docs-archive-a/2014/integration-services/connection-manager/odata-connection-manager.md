---
title: Диспетчер подключений OData | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3caa4372-aff3-4c0f-9ecd-97870948b8d0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 46eedaa008b284661fd1d364d2e2bc87c373a9f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665485"
---
# <a name="odata-connection-manager"></a><span data-ttu-id="4ce56-102">Диспетчер соединений OData</span><span class="sxs-lookup"><span data-stu-id="4ce56-102">OData Connection Manager</span></span>
  <span data-ttu-id="4ce56-103">Диспетчер соединений OData позволяет пакету подключаться к источнику OData.</span><span class="sxs-lookup"><span data-stu-id="4ce56-103">An OData connection manager enables a package to connect to an OData source.</span></span> <span data-ttu-id="4ce56-104">Компонент источника OData подключается к источнику OData с помощью диспетчера соединений OData и использует данные из службы.</span><span class="sxs-lookup"><span data-stu-id="4ce56-104">An OData Source component connects to an OData source using an OData connection manager and consumes data from the service.</span></span> <span data-ttu-id="4ce56-105">Подробные сведения, включая инструкции по установке этих компонентов, см. в разделе [OData Source](../data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="4ce56-105">See [OData Source](../data-flow/odata-source.md)section for detailed information including the installation instructions for these components.</span></span>  
  
## <a name="adding-connection-manager-to-an-ssis-package"></a><span data-ttu-id="4ce56-106">Добавление диспетчера соединений в пакет SSIS</span><span class="sxs-lookup"><span data-stu-id="4ce56-106">Adding Connection Manager to an SSIS Package</span></span>  
 <span data-ttu-id="4ce56-107">Новый диспетчер соединений OData можно добавить в пакет служб SSIS тремя способами.</span><span class="sxs-lookup"><span data-stu-id="4ce56-107">You can add a new OData Connection Manager to an SSIS package in three ways:</span></span>  
  
-   <span data-ttu-id="4ce56-108">Нажмите кнопку **Создать…** в **редакторе источника OData**.</span><span class="sxs-lookup"><span data-stu-id="4ce56-108">Click the **New...** button in the **OData Source Editor**</span></span>  
  
-   <span data-ttu-id="4ce56-109">Щелкните правой кнопкой мыши папку **Диспетчеры соединений** в **обозревателе решений** и выберите команду **Новый диспетчер соединений**.</span><span class="sxs-lookup"><span data-stu-id="4ce56-109">Right-click **Connection Managers** folder in the **Solution Explorer** and click **New Connection Manager**.</span></span> <span data-ttu-id="4ce56-110">Для параметра **Тип диспетчера соединений** выберите **ODATA**.</span><span class="sxs-lookup"><span data-stu-id="4ce56-110">Select **ODATA** for **Connection manager type**.</span></span>  
  
-   <span data-ttu-id="4ce56-111">Щелкните правой кнопкой мыши панель **Диспетчеры соединений** в нижней части конструктора пакетов и выберите **создать соединение...**. Выберите **ODATA** для **типа диспетчера соединений**.</span><span class="sxs-lookup"><span data-stu-id="4ce56-111">Right-click in the **Connection Managers** pane at the bottom of the package designer, and select **New Connection...**. Select **ODATA** for **Connection manager type**.</span></span>  
  
## <a name="connection-manager-authentication"></a><span data-ttu-id="4ce56-112">Проверка подлинности диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="4ce56-112">Connection Manager Authentication</span></span>  
 <span data-ttu-id="4ce56-113">Диспетчер соединений OData поддерживает два режима проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ce56-113">The OData Connection Manager supports two modes of authentication.</span></span>  
  
-   <span data-ttu-id="4ce56-114">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="4ce56-114">Windows Authentication</span></span>  
  
-   <span data-ttu-id="4ce56-115">Обычная проверка подлинности (имя пользователя или пароль)</span><span class="sxs-lookup"><span data-stu-id="4ce56-115">Basic Authentication (username/password)</span></span>  
  
 <span data-ttu-id="4ce56-116">Для анонимного доступа выберите режим проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="4ce56-116">For anonymous access, select the Windows Authentication option</span></span>  
  
### <a name="specifying-and-securing-credentials"></a><span data-ttu-id="4ce56-117">Указание и защита учетных данных</span><span class="sxs-lookup"><span data-stu-id="4ce56-117">Specifying and Securing Credentials</span></span>  
 <span data-ttu-id="4ce56-118">Если служба OData использует обычную проверку подлинности, то можно указать имя пользователя и пароль в [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4ce56-118">If your OData service requires basic authentication, you can specify a username and password in the [OData Connection Manager Editor](../odata-connection-manager-editor.md).</span></span> <span data-ttu-id="4ce56-119">Значения, указываемые в редакторе, сохраняются в пакете.</span><span class="sxs-lookup"><span data-stu-id="4ce56-119">The values you enter in the editor are persisted in the package.</span></span> <span data-ttu-id="4ce56-120">Значение пароля шифруется в соответствии с уровнем защиты пакета.</span><span class="sxs-lookup"><span data-stu-id="4ce56-120">The password value is encrypted according to the package protection level.</span></span>  
  
 <span data-ttu-id="4ce56-121">Существует несколько способов обработки или параметризация значений имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="4ce56-121">There are multiple ways to externalize/parameterize the username and password values.</span></span> <span data-ttu-id="4ce56-122">В [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] для этого есть два основных способа: использование параметров или указание свойств диспетчера соединений непосредственно при запуске пакета с помощью среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="4ce56-122">The two primary ways of doing this in [!INCLUDE[ssISversion11](../../includes/ssisversion11-md.md)] are by using parameters, or by setting the connection manager properties directly when you run the package using SQL Server Management Studio.</span></span>  
  
## <a name="odata-connection-manager-properties"></a><span data-ttu-id="4ce56-123">Свойства диспетчера соединений OData</span><span class="sxs-lookup"><span data-stu-id="4ce56-123">OData Connection Manager Properties</span></span>  
 <span data-ttu-id="4ce56-124">В следующем списке описываются некоторые свойства диспетчера соединений OData, которые может потребоваться изменить.</span><span class="sxs-lookup"><span data-stu-id="4ce56-124">The following list describes some of the OData Connection Manager properties that you may want to change.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ce56-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="4ce56-125">Property</span></span>|<span data-ttu-id="4ce56-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4ce56-126">Description</span></span>|  
|<span data-ttu-id="4ce56-127">Url</span><span class="sxs-lookup"><span data-stu-id="4ce56-127">Url</span></span>|<span data-ttu-id="4ce56-128">URL-адрес сервисного документа.</span><span class="sxs-lookup"><span data-stu-id="4ce56-128">URL to the service document.</span></span>|  
|<span data-ttu-id="4ce56-129">UserName</span><span class="sxs-lookup"><span data-stu-id="4ce56-129">UserName</span></span>|<span data-ttu-id="4ce56-130">Имя пользователя для обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ce56-130">Username to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="4ce56-131">Пароль</span><span class="sxs-lookup"><span data-stu-id="4ce56-131">Password</span></span>|<span data-ttu-id="4ce56-132">Пароль, используемый для обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4ce56-132">Password to use for Basic Authentication.</span></span>|  
|<span data-ttu-id="4ce56-133">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="4ce56-133">ConnectionString</span></span>|<span data-ttu-id="4ce56-134">Отражает другие свойства диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="4ce56-134">Reflects other properties of the connection manager.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ce56-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ce56-135">See Also</span></span>  
 [<span data-ttu-id="4ce56-136">Редактор диспетчера соединений c OData</span><span class="sxs-lookup"><span data-stu-id="4ce56-136">OData Connection Manager Editor</span></span>](../odata-connection-manager-editor.md)  
  
  
