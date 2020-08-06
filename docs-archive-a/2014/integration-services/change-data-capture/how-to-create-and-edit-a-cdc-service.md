---
title: Создание и изменение службы CDC Service​ | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1b3d47a5-dc89-482d-bbc7-fff04f194c43
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d90534b475901b08fcd2e09acdc0f7976f0fb6e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728618"
---
# <a name="how-to-create-and-edit-a-cdc-service"></a><span data-ttu-id="573ba-102">Создание и изменение службы CDC</span><span class="sxs-lookup"><span data-stu-id="573ba-102">How to Create and Edit a CDC Service</span></span>
  <span data-ttu-id="573ba-103">В этих процедурах описываются способы создания и изменения службы Oracle CDC Service при помощи консоли конфигурации службы CDC.</span><span class="sxs-lookup"><span data-stu-id="573ba-103">These procedures describe how to create and edit a new Oracle CDC Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="573ba-104">Эту процедуру может выполнять пользователь Windows с правами администратора на компьютере, где настроена служба Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="573ba-104">This procedure requires a Windows user with administrator privileges on the computer where the Oracle CDC service is configured.</span></span>  
  
### <a name="to-create-a-new-cdc-service"></a><span data-ttu-id="573ba-105">Создание службы CDC</span><span class="sxs-lookup"><span data-stu-id="573ba-105">To create a new CDC service</span></span>  
  
1.  <span data-ttu-id="573ba-106">В меню **Пуск** выберите **Конфигурация службы CDC для Oracle**.</span><span class="sxs-lookup"><span data-stu-id="573ba-106">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="573ba-107">На панели слева щелкните правой кнопкой мыши «Локальные службы CDC» и выберите команду «Создать службу».</span><span class="sxs-lookup"><span data-stu-id="573ba-107">From the left pane, right click Local CDC Services and select New Service</span></span>  
  
     <span data-ttu-id="573ba-108">Можно также щелкнуть **Создать службу** на панели **Действия** .</span><span class="sxs-lookup"><span data-stu-id="573ba-108">You can also click **New Service** from the **Actions** pane.</span></span>  
  
3.  <span data-ttu-id="573ba-109">Введите или укажите требуемые сведения в диалоговом окне «Создание службы Oracle CDC Service».</span><span class="sxs-lookup"><span data-stu-id="573ba-109">Type or enter the required information in the New Oracle CDC Service dialog box.</span></span> <span data-ttu-id="573ba-110">Дополнительные сведения о вводе данных в диалоговое окно «Создание службы Oracle CDC Service» см. в разделе [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="573ba-110">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the New Oracle CDC Service dialog box.</span></span>  
  
     <span data-ttu-id="573ba-111">Имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , указанное в диалоговом окне «Создание службы Oracle CDC Service», используется службой Oracle CDC Service при работе.</span><span class="sxs-lookup"><span data-stu-id="573ba-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login provided in the New Oracle CDC Service dialog box is used by the Oracle CDC Service when the service runs.</span></span> <span data-ttu-id="573ba-112">Этому имени входа достаточно быть членом предопределенной роли сервера public, никаких других прав доступа не требуется.</span><span class="sxs-lookup"><span data-stu-id="573ba-112">This login only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="573ba-113">Когда добавляются новые экземпляры Oracle CDC, это имя входа получает доступ **db_owner** к соответствующим базам данных CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="573ba-113">Once new Oracle CDC Instances are added, that login receives **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
4.  <span data-ttu-id="573ba-114">Введя необходимые данные, нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="573ba-114">When you finish entering the required information, click **OK**.</span></span>  
  
     <span data-ttu-id="573ba-115">Чтобы создать определение службы Windows для Oracle CDC, программе требуется доступ с возможностью обновления к базе данных MSXDBCDC в соответствующем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="573ba-115">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="573ba-116">При нажатии кнопки **OK**появляется диалоговое окно с приглашением ввести имя входа, имеющее доступ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с возможностью обновления к базе данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="573ba-116">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
     <span data-ttu-id="573ba-117">Дополнительные сведения о вводе данных в диалоговое окно «Подключение к SQL Server» см. в разделе [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="573ba-117">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="573ba-118">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно «Создание службы Oracle CDC Service».</span><span class="sxs-lookup"><span data-stu-id="573ba-118">Click **OK** to close the New Oracle CDC Service dialog box.</span></span>  
  
### <a name="to-edit-a-cdc-service"></a><span data-ttu-id="573ba-119">Изменение службы CDC</span><span class="sxs-lookup"><span data-stu-id="573ba-119">To edit a CDC service</span></span>  
  
1.  <span data-ttu-id="573ba-120">В меню **Пуск** выберите **Конфигурация службы CDC для Oracle**.</span><span class="sxs-lookup"><span data-stu-id="573ba-120">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="573ba-121">На панели слева выберите **Локальные службы CDC** , щелкните правой кнопкой мыши локальную службу, которую нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="573ba-121">From the left pane, select **Local CDC Services** then right-click the local service you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="573ba-122">Можно также выбрать нужную службу в списке, расположенном в центре, и щелкнуть **Свойства** на панели **Действия**.</span><span class="sxs-lookup"><span data-stu-id="573ba-122">You can also select the service you are working with in the middle and then from the **Actions** pane, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="573ba-123">Введите или укажите требуемые сведения в диалоговом окне «Свойства службы CDC».</span><span class="sxs-lookup"><span data-stu-id="573ba-123">Type or enter the required information in the CDC Service Properties dialog box.</span></span> <span data-ttu-id="573ba-124">Сведения о вводе данных в диалоговое окно «Свойства службы CDC» см. в разделе [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="573ba-124">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the CDC Service Properties dialog box.</span></span>  
  
4.  <span data-ttu-id="573ba-125">Завершив ввод необходимых данных, нажмите кнопку **OK**. Откроется диалоговое окно «Подключение к SQL Server».</span><span class="sxs-lookup"><span data-stu-id="573ba-125">When you finish entering the required information, Click **OK**, the Connect to SQL Server dialog box opens.</span></span>  
  
     <span data-ttu-id="573ba-126">Если пользователь с именем входа, не имеющим разрешение на запись в базе данных MSXDBDCDC, попытается создать экземпляр Oracle CDC, выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="573ba-126">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="573ba-127">Нажмите кнопку **ОК** , чтобы открыть диалоговое окно «Подключение к SQL Server».</span><span class="sxs-lookup"><span data-stu-id="573ba-127">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span> <span data-ttu-id="573ba-128">Введите учетные данные, относящиеся к имени входа, имеющему разрешение на запись в базу данных MSXDBCDC, например учетные данные роли базы данных **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="573ba-128">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role.</span></span>  
  
     <span data-ttu-id="573ba-129">Дополнительные сведения о вводе данных в диалоговое окно «Подключение к SQL Server» см. в разделе [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="573ba-129">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="573ba-130">Нажмите кнопку **ОК** в диалоговом окне «Подключение к Oracle».</span><span class="sxs-lookup"><span data-stu-id="573ba-130">Click **OK** in the Connect to Oracle dialog box.</span></span> <span data-ttu-id="573ba-131">Оба диалоговых окна закроются. Служба будет обновлена и зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="573ba-131">Both dialog boxes close and the service is updated and registered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573ba-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="573ba-132">See Also</span></span>  
 <span data-ttu-id="573ba-133">[Конструктор системы отслеживания измененных данных для Oracle компании Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="573ba-133">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="573ba-134">Создание и изменение службы CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="573ba-134">Create and Edit an Oracle CDC Service</span></span>](create-and-edit-an-oracle-cdc-service.md)  
  
  
