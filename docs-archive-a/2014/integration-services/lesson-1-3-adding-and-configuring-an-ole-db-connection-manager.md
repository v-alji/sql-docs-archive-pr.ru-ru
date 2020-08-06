---
title: Шаг 3. Добавление и настройка диспетчера соединений OLE DB | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664361"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a><span data-ttu-id="35c31-102">Шаг 3. Добавление и настройка диспетчера соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="35c31-102">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>
  <span data-ttu-id="35c31-103">После добавления диспетчера соединений с неструктурированными файлами для подключения к источникам данных предстоит добавить диспетчер соединений OLE DB для соединения с назначением.</span><span class="sxs-lookup"><span data-stu-id="35c31-103">After you have added a Flat File connection manager to connect to the data source, the next task is to add an OLE DB connection manager to connect to the destination.</span></span> <span data-ttu-id="35c31-104">Диспетчер соединений OLE DB позволяет пакету получать данные из любого источника данных, совместимого с OLE DB, а также загружать данные в такой источник данных.</span><span class="sxs-lookup"><span data-stu-id="35c31-104">An OLE DB connection manager enables a package to extract data from or load data into any OLE DB-compliant data source.</span></span> <span data-ttu-id="35c31-105">Используя диспетчер соединений OLE DB, можно указать для соединения сервер, метод проверки подлинности и базу данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35c31-105">Using the OLE DB Connection manager, you can specify the server, the authentication method, and the default database for the connection.</span></span>  
  
 <span data-ttu-id="35c31-106">На этом занятии будет создан диспетчер соединений OLE DB, использующий проверку подлинности Windows для подключения к локальному экземпляру **AdventureWorksDB2012**.</span><span class="sxs-lookup"><span data-stu-id="35c31-106">In this lesson, you will create an OLE DB connection manager that uses Windows Authentication to connect to the local instance of **AdventureWorksDB2012**.</span></span> <span data-ttu-id="35c31-107">На создаваемый диспетчер соединений OLE DB также будут ссылаться другие компоненты, которые будут созданы позже в ходе работы с этим учебником, такие, как преобразование «Уточняющий запрос» и назначение OLE DB.</span><span class="sxs-lookup"><span data-stu-id="35c31-107">The OLE DB connection manager that you create will also be referenced by other components that you will create later in this tutorial, such as the Lookup transformation and the OLE DB destination.</span></span>  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a><span data-ttu-id="35c31-108">Добавление и настройка диспетчера соединений OLE DB для пакета служб SSIS</span><span class="sxs-lookup"><span data-stu-id="35c31-108">To add and configure an OLE DB Connection Manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="35c31-109">Щелкните правой кнопкой мыши область **Диспетчеры соединений** и выберите команду **Создать соединение OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="35c31-109">Right-click anywhere in the **Connection Managers** area, and then click **New OLE DB Connection**.</span></span>  
  
2.  <span data-ttu-id="35c31-110">В диалоговом окне **Настройка диспетчера соединений OLE DB** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="35c31-110">In the **Configure OLE DB Connection Manager** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="35c31-111">Введите **localhost**в поле **Имя сервера**.</span><span class="sxs-lookup"><span data-stu-id="35c31-111">For **Server name**, enter **localhost**.</span></span>  
  
     <span data-ttu-id="35c31-112">Если в качестве имени сервера указано значение localhost, диспетчер соединений соединяется с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , расположенном по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="35c31-112">When you specify localhost as the server name, the connection manager connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="35c31-113">Чтобы использовать удаленный экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], замените localhost именем сервера, с которым нужно соединиться.</span><span class="sxs-lookup"><span data-stu-id="35c31-113">To use a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], replace localhost with the name of the server to which you want to connect.</span></span>  
  
4.  <span data-ttu-id="35c31-114">Убедитесь, что в группе **Вход на сервер** выбран вариант **Использовать проверку подлинности Windows** .</span><span class="sxs-lookup"><span data-stu-id="35c31-114">In the **Log on to the server** group, verify that **Use Windows Authentication** is selected.</span></span>  
  
5.  <span data-ttu-id="35c31-115">В группе **соединение с базой данных** в поле **выберите или введите имя базы данных** введите или выберите `AdventureWorksDW2012` .</span><span class="sxs-lookup"><span data-stu-id="35c31-115">In the **Connect to a database** group, in the **Select or enter a database name** box, type or select `AdventureWorksDW2012`.</span></span>  
  
6.  <span data-ttu-id="35c31-116">Нажмите кнопку **Проверить соединение** , чтобы убедиться, что параметры соединения указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="35c31-116">Click **Test Connection** to verify that the connection settings you have specified are valid.</span></span>  
  
7.  <span data-ttu-id="35c31-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35c31-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="35c31-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35c31-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="35c31-119">Убедитесь, что на панели **Подключение к данным** в диалоговом окне **Настройка диспетчера соединений OLE DB** выбрано значение **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="35c31-119">In the **Data Connections** pane of the **Configure OLE DB Connection Manager** dialog box, verify that **localhost.AdventureWorksDW2012** is selected.</span></span>  
  
10. <span data-ttu-id="35c31-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35c31-120">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="35c31-121">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="35c31-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="35c31-122">Этап 4. Добавление задачи потока данных в пакет</span><span class="sxs-lookup"><span data-stu-id="35c31-122">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="35c31-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="35c31-123">See Also</span></span>  
 [<span data-ttu-id="35c31-124">Диспетчер соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="35c31-124">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
