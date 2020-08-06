---
title: Просмотр пакетов Integration Services в SQL Server Management Studio (службы SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- viewing packages
- connections [Integration Services], packages
ms.assetid: 783e653c-0f1f-45ed-b3ef-5ba07b019f27
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4ba86320f1b1a685eab6e80399f3e8c21bd110eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728442"
---
# <a name="view-integration-services-packages-in-sql-server-management-studio-ssis-service"></a><span data-ttu-id="1f2f1-102">Просмотр пакетов служб Integration Services в среде SQL Server Management Studio (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="1f2f1-102">View Integration Services Packages in SQL Server Management Studio (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="1f2f1-103">В данном разделе описывается компонент [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] — служба Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f2f1-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="1f2f1-104">поддерживает эту службу для обеспечения обратной совместимости с более ранними версиями служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f2f1-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="1f2f1-105">Начиная с [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], на сервере служб Integration Services можно управлять пакетами.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="1f2f1-106">Эта процедура описывает подключение к службам [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и просмотр списка пакетов, которыми управляют службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f2f1-106">This procedure describes how to connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and view a list of the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
### <a name="to-connect-to-integration-services"></a><span data-ttu-id="1f2f1-107">Подключение к службам Integration Services</span><span class="sxs-lookup"><span data-stu-id="1f2f1-107">To connect to Integration Services</span></span>  
  
1.  <span data-ttu-id="1f2f1-108">Нажмите кнопку **Пуск**, укажите пункт **Все программы**, пункт **Microsoft SQL Server**, а затем выберите команду **Среда SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="1f2f1-109">В диалоговом окне **Соединение с сервером** выберите **Службы Integration Services** в списке **Тип сервера** , введите имя сервера в поле **Имя сервера** и нажмите **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-109">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and then click **Connect**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1f2f1-110">Если подключиться к [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]не удается, возможно, что служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] не запущена.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-110">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="1f2f1-111">Чтобы узнать о состоянии службы, нажмите кнопку **Пуск**и последовательно выберите пункты **Все программы**, **Microsoft SQL Server**, **Средства настройки**и **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-111">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="1f2f1-112">На левой панели щелкните **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-112">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="1f2f1-113">На панели справа найдите службу [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f2f1-113">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="1f2f1-114">Если служба не запущена, запустите ее.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-114">Start the service if it is not already running.</span></span>  
  
     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1f2f1-115">.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-115">opens.</span></span> <span data-ttu-id="1f2f1-116">По умолчанию окно «Обозреватель объектов» открыто и находится в нижнем левом углу среды разработки.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-116">By default the Object Explorer window is open and positioned in the lower-left corner of the studio.</span></span> <span data-ttu-id="1f2f1-117">Если обозреватель объектов не открыт, выберите **Обозреватель объектов** в меню **Вид** .</span><span class="sxs-lookup"><span data-stu-id="1f2f1-117">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>  
  
### <a name="to-view-the-packages-that-integration-services-service-manages"></a><span data-ttu-id="1f2f1-118">Просмотр пакетов, управляемых службой служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="1f2f1-118">To view the packages that Integration Services service manages</span></span>  
  
1.  <span data-ttu-id="1f2f1-119">В обозревателе объектов разверните папку «Сохраненные пакеты».</span><span class="sxs-lookup"><span data-stu-id="1f2f1-119">In Object Explorer, expand the Stored Packages folder.</span></span>  
  
2.  <span data-ttu-id="1f2f1-120">Разверните вложенные папки в папке «Сохраненные пакеты», чтобы показать пакеты.</span><span class="sxs-lookup"><span data-stu-id="1f2f1-120">Expand the Stored Packages subfolders to show packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2f1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f2f1-121">See Also</span></span>  
 <span data-ttu-id="1f2f1-122">[Управление пакетами &#40;служб SSIS&#41;](service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="1f2f1-122">[Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="1f2f1-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f2f1-123">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
