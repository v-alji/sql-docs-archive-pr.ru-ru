---
title: Как работать со службами CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db5c718a-6e7f-48ec-82a3-9d5b131716e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cfb5a0ed0e9ded8e0be118deb3c819626448896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658351"
---
# <a name="how-to-work-with-cdc-services"></a><span data-ttu-id="0f584-102">Как работать со службами CDC</span><span class="sxs-lookup"><span data-stu-id="0f584-102">How to Work with CDC Services</span></span>
  <span data-ttu-id="0f584-103">В этой процедуре описано, как использовать консоль управления службой CDC для подготовки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] со службами Oracle CDC и для создания новой службы CDC.</span><span class="sxs-lookup"><span data-stu-id="0f584-103">This procedure describes how to use the CDC Service Configuration Console to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to work with Oracle CDC Services and to create a new CDC service.</span></span>  
  
### <a name="to-work-with-cdc-services"></a><span data-ttu-id="0f584-104">Работа со службами CDC</span><span class="sxs-lookup"><span data-stu-id="0f584-104">To work with CDC services</span></span>  
  
1.  <span data-ttu-id="0f584-105">В меню **Пуск** выберите пункт **Конфигурация служб CDC для Oracle**.</span><span class="sxs-lookup"><span data-stu-id="0f584-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="0f584-106">На левой панели выберите **Локальные службы CDC** (корневой уровень).</span><span class="sxs-lookup"><span data-stu-id="0f584-106">From the left pane, select **Local CDC Services** (the root level).</span></span>  
  
3.  <span data-ttu-id="0f584-107">Выполните одну или обе следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="0f584-107">You carry out the one or both of the following tasks:</span></span>  
  
    -   <span data-ttu-id="0f584-108">**Подготовка SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0f584-108">**Prepare SQL Server**</span></span>  
  
         <span data-ttu-id="0f584-109">Выберите этот параметр на панели **Действия** в правой части консоли конфигурации службы CDC.</span><span class="sxs-lookup"><span data-stu-id="0f584-109">Select this option from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="0f584-110">Можно также щелкнуть правой кнопкой **Локальные службы CDC** и выбрать **Подготовить SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0f584-110">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
         <span data-ttu-id="0f584-111">Откроется диалоговое окно подготовки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="0f584-111">The Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC dialog box opens.</span></span>  
  
         <span data-ttu-id="0f584-112">Чтобы можно было подготовить экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для служб Oracle CDC, имя входа должно соответствовать имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с предопределенной ролью сервера `dbcreator` .</span><span class="sxs-lookup"><span data-stu-id="0f584-112">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC services, the login must have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with the `dbcreator` fixed server role.</span></span> <span data-ttu-id="0f584-113">Это имя входа используется для создания базы данных MSXDBCDC, которая необходима для добавления служб Oracle CDC и позднее экземпляров Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="0f584-113">This login is used to create the MSXDBCDC database that is required for adding Oracle CDC Services and, later on, Oracle CDC Instances.</span></span>  
  
         <span data-ttu-id="0f584-114">Сведения о том, как использовать это диалоговое окно, см. в разделе [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="0f584-114">For information on how to use this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span> <span data-ttu-id="0f584-115">Сведения о включении экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для CDC см. в разделе [Подготовка SQL Server для CDC](how-to-prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="0f584-115">For information on how to enable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for CDC, see [How to Prepare SQL Server for CDC](how-to-prepare-sql-server-for-cdc.md).</span></span>  
  
    -   <span data-ttu-id="0f584-116">**Создайте новую службу CDC.**</span><span class="sxs-lookup"><span data-stu-id="0f584-116">**Create a new CDC service**</span></span>  
  
         <span data-ttu-id="0f584-117">Щелкните пункт **Создать службу** на панели **Действия** в правой половине консоли настройки службы CDC.</span><span class="sxs-lookup"><span data-stu-id="0f584-117">Click **New Service** from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="0f584-118">Можно также щелкнуть правой кнопкой **Локальные службы CDC** и выбрать **Создать службу**.</span><span class="sxs-lookup"><span data-stu-id="0f584-118">You can also right-Click **Local CDC Services** and select **New Service**.</span></span>  
  
         <span data-ttu-id="0f584-119">Откроется диалоговое окно создания новой службы Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="0f584-119">The New Oracle CDC Service dialog box opens.</span></span>  
  
         <span data-ttu-id="0f584-120">Сведения о том, как использовать это диалоговое окно, см. в разделе [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="0f584-120">For information on how to use this dialog box, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span></span> <span data-ttu-id="0f584-121">Сведения о создании и редактировании службы CDC см. в разделе [Создание и изменение службы CDC](how-to-create-and-edit-a-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="0f584-121">For information on how to create or edit a CDC service, see [How to Create and Edit a CDC Service](how-to-create-and-edit-a-cdc-service.md).</span></span>  
  
         <span data-ttu-id="0f584-122">Имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которое будет использоваться только службой Oracle CDC, должно быть членом предопределенной роли сервера `public` . В дополнение к этому других разрешений не требуется.</span><span class="sxs-lookup"><span data-stu-id="0f584-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the `public` fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="0f584-123">Однако чтобы создать службу Oracle CDC, для имени входа необходимо установить разрешение на запись в базу данных MSXDBCDC, например для имени входа на сервер необходимо назначить роль **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="0f584-123">However, to create the Oracle CDC Service, the login must have write permission to the MSXDBCDC database, for example the **db_owner** database role must be assigned to the login.</span></span> <span data-ttu-id="0f584-124">Если пользователь с именем входа, не имеющим разрешение на запись в базе данных MSXDBDCDC, попытается создать экземпляр Oracle CDC, выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0f584-124">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="0f584-125">Нажмите кнопку **ОК** , чтобы открыть диалоговое окно «Подключение к SQL Server».</span><span class="sxs-lookup"><span data-stu-id="0f584-125">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span>  
  
         <span data-ttu-id="0f584-126">Сведения о вводе учетных данных для имени входа с разрешением на запись в базу данных MSXDBCDC, например для роли **db_owner** , см. в разделах [Создание и изменение службы CDC Oracle](create-and-edit-an-oracle-cdc-service.md) и [Соединение с SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f584-126">For information on how to enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) and [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f584-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f584-127">See Also</span></span>  
 [<span data-ttu-id="0f584-128">Работа со службами CDC</span><span class="sxs-lookup"><span data-stu-id="0f584-128">Work with CDC Services</span></span>](work-with-cdc-services.md)  
  
  
