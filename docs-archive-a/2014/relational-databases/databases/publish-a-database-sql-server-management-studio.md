---
title: Публикация базы данных (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 98b2914e-7147-40af-ba7d-87253bbe8bf9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652f2341d24c19e6c5ce34196b0e1c4dc5b09084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658811"
---
# <a name="publish-a-database-sql-server-management-studio"></a><span data-ttu-id="53ec9-102">Публикация базы данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="53ec9-102">Publish a Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="53ec9-103">**Мастер формирования и публикации скриптов** служит для публикации всей базы данных или отдельных ее объектов на поставщике услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="53ec9-103">You can use the **Generate and Publish Scripts Wizard** to publish an entire database or individual database objects to a Web hosting provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53ec9-104">Функциональные возможности, использование которых описано в этом разделе, раньше обеспечивал мастер публикации базы данных.</span><span class="sxs-lookup"><span data-stu-id="53ec9-104">The functionality described in this topic used to be provided by the Publish Database Wizard.</span></span> <span data-ttu-id="53ec9-105">В мастер формирования и публикации скриптов также было добавлено средство публикации, а мастер публикации базы данных больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="53ec9-105">The publishing functionality has been added to the Generate and Publish Scripts Wizard, and the Publish Database Wizard has been discontinued.</span></span>  
  
## <a name="generate-and-publish-scripts-wizard"></a><span data-ttu-id="53ec9-106">Мастер формирования и публикации скриптов</span><span class="sxs-lookup"><span data-stu-id="53ec9-106">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="53ec9-107">Мастер формирования и публикации скриптов можно использовать для публикации базы данных или отдельных ее объектов на поставщике услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="53ec9-107">The Generate and Publish Scripts Wizard can be used to publish a database or selected database objects to a Web hosting provider.</span></span> <span data-ttu-id="53ec9-108">Поставщик услуг размещения SQL Server представляет собой интерфейс обмена данными для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="53ec9-108">A SQL Server Web hosting provider is a connectivity interface to a Web service.</span></span> <span data-ttu-id="53ec9-109">Веб-служба создается с помощью проекта Database Publishing Service в пакете SQL Server Hosting Toolkit на CodePlex.</span><span class="sxs-lookup"><span data-stu-id="53ec9-109">The Web service is created by using the Database Publishing Services project from the SQL Server Hosting Toolkit on CodePlex.</span></span> <span data-ttu-id="53ec9-110">Веб-служба облегчает клиентам поставщика услуг размещения публикацию баз данных с помощью мастера формирования и публикации скриптов.</span><span class="sxs-lookup"><span data-stu-id="53ec9-110">The Web service makes it easy for the Web hoster customers to publish their databases to the service by using the Generate and Publish Scripts Wizard.</span></span> <span data-ttu-id="53ec9-111">Дополнительные сведения о загрузке пакета SQL Server Hosting Toolkit см. на странице [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span><span class="sxs-lookup"><span data-stu-id="53ec9-111">For more information about downloading the SQL Server Hosting Toolkit, see [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span></span>  
  
 <span data-ttu-id="53ec9-112">Мастер формирования и публикации скриптов также может использоваться для создания скриптов переноса базы данных.</span><span class="sxs-lookup"><span data-stu-id="53ec9-112">The Generate and Publish Scripts Wizard can also be used to create a script for transferring a database.</span></span>  
  
#### <a name="to-publish-a-database-to-a-web-service"></a><span data-ttu-id="53ec9-113">Публикация базы данных на веб-службе</span><span class="sxs-lookup"><span data-stu-id="53ec9-113">To publish a database to a Web service</span></span>  
  
1.  <span data-ttu-id="53ec9-114">В обозревателе объектов разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем **Формирование и публикация скриптов**.</span><span class="sxs-lookup"><span data-stu-id="53ec9-114">In Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Generate and Publish Scripts**.</span></span> <span data-ttu-id="53ec9-115">Следуя шагам мастера, создайте скрипт для публикации объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="53ec9-115">Follow the steps in the wizard to script the database objects for publishing.</span></span>  
  
2.  <span data-ttu-id="53ec9-116">На странице **Выбор объектов** выберите объекты для публикации в веб-службе размещения.</span><span class="sxs-lookup"><span data-stu-id="53ec9-116">On the **Choose Objects** page, select the objects to be published to the Web hosting service.</span></span>  
  
3.  <span data-ttu-id="53ec9-117">На странице **Задание параметров скрипта** выберите пункт **Опубликовать в веб-службе**.</span><span class="sxs-lookup"><span data-stu-id="53ec9-117">On the **Set Scripting Options** page, select **Publish to Web Service**.</span></span>  
  
    1.  <span data-ttu-id="53ec9-118">В поле **Поставщик** задайте поставщика для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="53ec9-118">In the **Provider** box, specify the provider for your Web service.</span></span> <span data-ttu-id="53ec9-119">Если настроенный поставщик услуг размещения отсутствует, нажмите кнопку **Управление поставщиками** и в диалоговом окне **Управление поставщиками** настройте поставщика для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="53ec9-119">If you have not configured a Web hosting provider, select **Manage Providers** and use the **Manage Providers** dialog box to configure a provider for your Web service.</span></span>  
  
    2.  <span data-ttu-id="53ec9-120">Чтобы задать дополнительные параметры публикации, нажмите кнопку **Дополнительно** в разделе **Опубликовать в веб-службе** .</span><span class="sxs-lookup"><span data-stu-id="53ec9-120">To specify advanced publishing options, select the **Advanced** button in the **Publish to Web Service** section.</span></span>  
  
4.  <span data-ttu-id="53ec9-121">На странице **Сводка** просмотрите выбранные параметры.</span><span class="sxs-lookup"><span data-stu-id="53ec9-121">On the **Summary** page, review your selections.</span></span> <span data-ttu-id="53ec9-122">Чтобы изменить выбранные параметры, нажмите кнопку **Назад** .</span><span class="sxs-lookup"><span data-stu-id="53ec9-122">Click **Previous** to change your selections.</span></span> <span data-ttu-id="53ec9-123">Для публикации выделенных объектов нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="53ec9-123">Click **Next** to publish the objects you selected.</span></span>  
  
5.  <span data-ttu-id="53ec9-124">На странице **Сохранение или публикация скриптов** можно наблюдать ход выполнения публикации.</span><span class="sxs-lookup"><span data-stu-id="53ec9-124">On the **Save or Publish Scripts** page, monitor the progress of the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ec9-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="53ec9-125">See Also</span></span>  
 <span data-ttu-id="53ec9-126">[Формирование скриптов (среда SQL Server Management Studio)](../scripting/generate-scripts-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="53ec9-126">[Generate Scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="53ec9-127">Копирование баз данных на другие серверы</span><span class="sxs-lookup"><span data-stu-id="53ec9-127">Copy Databases to Other Servers</span></span>](copy-databases-to-other-servers.md)  
  
  
