---
title: Занятие 1. Создание объектов хранилища Azure | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 74edd1fd-ab00-46f7-9e29-7ba3f1a446c5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d46c6d22ffd92dbf8035bff140960af8ef56122d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656110"
---
# <a name="lesson-1-create-azure-storage-objects"></a><span data-ttu-id="dcea3-102">Урок 1. Создание объектов службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="dcea3-102">Lesson 1: Create Azure Storage Objects</span></span>
  <span data-ttu-id="dcea3-103">Перед созданием резервных копий [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в облачном хранилище сначала необходимо создать учетную запись хранилища, а затем контейнер больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="dcea3-103">Before you can create [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups on cloud storage, you must first create a storage account, and then a blob container.</span></span> <span data-ttu-id="dcea3-104">На занятии 1 описано, как войти в портал управления Azure, создать учетную запись хранения и контейнер больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="dcea3-104">Lesson 1 walks you through the steps of Logging into the Azure Management Portal, creating a storage account and a blob container.</span></span>  
  
## <a name="create-a-storage-account"></a><span data-ttu-id="dcea3-105">Создание учетной записи хранения</span><span class="sxs-lookup"><span data-stu-id="dcea3-105">Create a storage Account</span></span>  
 <span data-ttu-id="dcea3-106">Чтобы создать учетную запись хранения из портал управления Azure, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dcea3-106">To create a storage account from the Azure Management Portal, use the following steps:</span></span>  
  
1.  <span data-ttu-id="dcea3-107">Войдите на портал управления Azure под вашей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="dcea3-107">Log in to the Azure Management Portal using your account.</span></span> <span data-ttu-id="dcea3-108">Если у вас нет учетной записи Azure, [посетите бесплатную пробную версию Azure на 3 месяца](https://go.microsoft.com/fwlink/?LinkId=271927).</span><span class="sxs-lookup"><span data-stu-id="dcea3-108">If you do not have an Azure account, [visit Azure 3-Month free trial](https://go.microsoft.com/fwlink/?LinkId=271927).</span></span>  
  
     <span data-ttu-id="dcea3-109">![Экран входа в Azure](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Экран входа в Azure")</span><span class="sxs-lookup"><span data-stu-id="dcea3-109">![Azure Login Screen](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure Login Screen")</span></span>  
  
2.  <span data-ttu-id="dcea3-110">Для созданий учетной записи воспользуйтесь подробной пошаговой инструкцией [здесь](https://go.microsoft.com/fwlink/?LinkId=271926).</span><span class="sxs-lookup"><span data-stu-id="dcea3-110">Use the step by step instructions detailed [here](https://go.microsoft.com/fwlink/?LinkId=271926), to create a storage account.</span></span>  
  
3.  <span data-ttu-id="dcea3-111">Просмотрите учетную запись хранилища, созданную на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="dcea3-111">Browse to the storage account you created in previous step.</span></span> <span data-ttu-id="dcea3-112">В центре нижней части веб-страницы нажмите кнопку **УПРАВЛЕНИЕ КЛЮЧАМИ**.</span><span class="sxs-lookup"><span data-stu-id="dcea3-112">From the bottom center of the web page, click **MANAGE KEYS**.</span></span> <span data-ttu-id="dcea3-113">Отобразятся сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="dcea3-113">The account information is displayed.</span></span> <span data-ttu-id="dcea3-114">Скопируйте имя учетной записи хранилища и ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="dcea3-114">Copy the storage account name, and the Access Keys.</span></span> <span data-ttu-id="dcea3-115">Эти сведения понадобятся для создания сохраненных учетных данных SQL.</span><span class="sxs-lookup"><span data-stu-id="dcea3-115">This information is required to create SQL Stored Credentials.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="dcea3-116">использует данную информацию для получения доступа к учетной записи хранилища и создания резервных копий.</span><span class="sxs-lookup"><span data-stu-id="dcea3-116">uses this information to access the storage account and create backups.</span></span>  
  
     <span data-ttu-id="dcea3-117">![Снимок экрана с ключами учетной записи хранения Azure](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Снимок экрана с ключами учетной записи хранения Azure")</span><span class="sxs-lookup"><span data-stu-id="dcea3-117">![Screen shot of Azure Storage Account Keys](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screen shot of Azure Storage Account Keys")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dcea3-118">Можно также создать учетную запись хранилища программным образом с помощью API-интерфейсов REST.</span><span class="sxs-lookup"><span data-stu-id="dcea3-118">You can also create a storage account programmatically using REST APIs.</span></span> <span data-ttu-id="dcea3-119">Дополнительные сведения см. в разделе [Создание учетной записи хранилища](https://go.microsoft.com/fwlink/?LinkId=271928).</span><span class="sxs-lookup"><span data-stu-id="dcea3-119">For more information, see [Create Storage Account](https://go.microsoft.com/fwlink/?LinkId=271928).</span></span>  
  
### <a name="create-a-blob-container"></a><span data-ttu-id="dcea3-120">Создание контейнера больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="dcea3-120">Create a Blob Container</span></span>  
 <span data-ttu-id="dcea3-121">Контейнер обеспечивает группирование набора больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="dcea3-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="dcea3-122">Все BLOB-объекты должны содержаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="dcea3-122">All blobs must be in a container.</span></span> <span data-ttu-id="dcea3-123">Учетная запись может содержать неограниченное количество контейнеров, но не менее одного.</span><span class="sxs-lookup"><span data-stu-id="dcea3-123">An account can contain an unlimited number of containers, but must have at least one container.</span></span> <span data-ttu-id="dcea3-124">Контейнер может хранить неограниченное количество больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="dcea3-124">A container can store an unlimited number of blobs.</span></span>  
  
 <span data-ttu-id="dcea3-125">Для создания контейнера выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dcea3-125">To create a Container, use the following steps:</span></span>  
  
1.  <span data-ttu-id="dcea3-126">Выберите учетную запись хранилища, перейдите на вкладку **КОНТЕЙНЕРЫ** и нажмите кнопку **ДОБАВИТЬ КОНТЕЙНЕР** в нижней части экрана. Откроется новое диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="dcea3-126">Select the storage account, click the **CONTAINERS** tab and click **ADD CONTAINER** at the bottom of the screen which opens a new dialog box.</span></span>  
  
     <span data-ttu-id="dcea3-127">![Создание контейнера в портале управления](../../2014/tutorials/media/backuptocloud.gif "Создание контейнера в портале управления")</span><span class="sxs-lookup"><span data-stu-id="dcea3-127">![Creating a Container in the Management Portal](../../2014/tutorials/media/backuptocloud.gif "Creating a Container in the Management Portal")</span></span>  
  
2.  <span data-ttu-id="dcea3-128">Введите имя контейнера.</span><span class="sxs-lookup"><span data-stu-id="dcea3-128">Enter the name for the container.</span></span> <span data-ttu-id="dcea3-129">Запишите указанное имя контейнера.</span><span class="sxs-lookup"><span data-stu-id="dcea3-129">Make a note of the container name you specified.</span></span> <span data-ttu-id="dcea3-130">Эти сведения используются в URL-адресе (пути к файлу резервной копии) в инструкциях T-SQL на занятиях 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="dcea3-130">This information is used in the URL (path to backup file) in the T-SQL statements in lesson 3 and 4.</span></span>  
  
3.  <span data-ttu-id="dcea3-131">Для **Типа доступа**выберите «Частный».</span><span class="sxs-lookup"><span data-stu-id="dcea3-131">Select Private for **Access Type**.</span></span> <span data-ttu-id="dcea3-132">Рекомендуется создавать частные контейнеры для защиты файлов резервной копии.</span><span class="sxs-lookup"><span data-stu-id="dcea3-132">We recommend creating private containers for securing your backup files.</span></span>  
  
     <span data-ttu-id="dcea3-133">![Создание нового контейнера больших двоичных объектов](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Создание нового контейнера больших двоичных объектов")</span><span class="sxs-lookup"><span data-stu-id="dcea3-133">![Creating a new blob container](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creating a new blob container")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dcea3-134">Для резервного копирования и восстановления [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] проводится проверка подлинности учетной записи хранилища даже при создании открытого контейнера.</span><span class="sxs-lookup"><span data-stu-id="dcea3-134">Authentication to the storage account is required for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore even if you choose to create a public container.</span></span>  
    >   
    >  <span data-ttu-id="dcea3-135">Можно также создать контейнер программным образом с помощью API-интерфейсов REST.</span><span class="sxs-lookup"><span data-stu-id="dcea3-135">You can also create a container programmatically using REST APIs.</span></span> <span data-ttu-id="dcea3-136">Дополнительные сведения см. в разделе [Создание контейнера](https://go.microsoft.com/fwlink/?LinkId=271946).</span><span class="sxs-lookup"><span data-stu-id="dcea3-136">For more information, see [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="dcea3-137">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="dcea3-137">Next Lesson</span></span>  
 <span data-ttu-id="dcea3-138">[Занятие 2. Создание учетных данных SQL Server](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="dcea3-138">[Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
  
