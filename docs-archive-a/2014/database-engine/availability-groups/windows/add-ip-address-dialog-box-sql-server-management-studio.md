---
title: Диалоговое окно "Добавление IP-адреса" (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistener.addipaddress.f1
ms.assetid: 98c9ad3b-ff3c-4c1d-b344-59a72fca137c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5192e6414b34bee6de09d45a7284f25404235dc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655972"
---
# <a name="add-ip-address-dialog-box-sql-server-management-studio"></a><span data-ttu-id="b666e-102">Диалоговое окно «Добавление IP-адреса» (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b666e-102">Add IP Address Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b666e-103"> В этом разделе справки F1 описываются параметры диалогового окна **Добавление IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="b666e-103">This F1 help topic describes the options of the **Add IP Address** dialog box.</span></span> <span data-ttu-id="b666e-104">Это диалоговое окно открывается из диалогового окна **Создание прослушивателя группы доступности** и из вкладки **Прослушиватель** на странице **Выбор реплик** в [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] или [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)][!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b666e-104">This dialog box accessed from the **New Availability Group Listener** dialog box and the **Listener** tab of the **Specify Replicas** page of the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b666e-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="b666e-105">Prerequisites</span></span>  
 <span data-ttu-id="b666e-106">Прежде чем начинать добавлять подсети в прослушиватель группы доступности, убедитесь, что вы знаете IP-адрес для каждой подсети, а для IPv4-адреса — маску подсети.</span><span class="sxs-lookup"><span data-stu-id="b666e-106">Before you begin to add subnets to an availability group listener, ensure that know the IP address for each subnet and, for an IPv4 address, the subnet mask.</span></span>  
  
##  <a name="add-ip-address-options"></a><a name="PageOptions"></a> <span data-ttu-id="b666e-107">Варианты добавления IP-адреса</span><span class="sxs-lookup"><span data-stu-id="b666e-107">Add IP Address Options</span></span>  
 <span data-ttu-id="b666e-108">**Подсеть**</span><span class="sxs-lookup"><span data-stu-id="b666e-108">**Subnet**</span></span>  
 <span data-ttu-id="b666e-109">В раскрывающемся списке выберите адрес подсети, добавляемой в прослушиватель группы доступности.</span><span class="sxs-lookup"><span data-stu-id="b666e-109">Use the drop list to select an address for the subnet that you are adding to the availability group listener.</span></span> <span data-ttu-id="b666e-110">По умолчанию подсеть принимает адреса как IPv4, так и IPv6.</span><span class="sxs-lookup"><span data-stu-id="b666e-110">By default a subnet possesses both an IPv4 address and an IPv6 address.</span></span> <span data-ttu-id="b666e-111">При первом использовании диалогового окна **Добавление IP-адреса** в раскрывающемся списке **Подсеть** отображаются оба адреса подсетей для каждой подсети, в которой размещается реплика группы доступности.</span><span class="sxs-lookup"><span data-stu-id="b666e-111">The first time you use the **Add IP Address** dialog,  the **Subnet** drop list displays both subnet addresses for each subnet that hosts a replica for the availability group.</span></span> <span data-ttu-id="b666e-112">Чтобы добавить данную подсеть в прослушиватель, выберите один из адресов этой подсети.</span><span class="sxs-lookup"><span data-stu-id="b666e-112">To add a given subnet to the listener, select one of its subnet addresses.</span></span>  
  
 <span data-ttu-id="b666e-113">По завершении работы с диалоговым окном **Добавление IP-адреса** нажмите кнопку **OK** , чтобы добавить выбранный адрес подсети в прослушиватель, причем этот адрес исчезнет из раскрывающегося списка **Подсеть** .</span><span class="sxs-lookup"><span data-stu-id="b666e-113">After you complete the **Add IP Address** dialog box and click **OK** to add a selected subnet address to the listener, the **Subnet** drop list filters out that subnet address.</span></span> <span data-ttu-id="b666e-114">Все невыбранные адреса подсетей останутся в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="b666e-114">All unselected subnet addresses remain on the drop list.</span></span> <span data-ttu-id="b666e-115">Следует добавлять только один адрес каждой подсети в прослушиватель, иначе создание прослушивателя завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b666e-115">Be sure that you add one and only one subnet address per subnet to the listener, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="b666e-116">**Адреса**</span><span class="sxs-lookup"><span data-stu-id="b666e-116">**Addresses**</span></span>  
 <span data-ttu-id="b666e-117">Воспользуйтесь этим полем для ввода статического IP-адреса для выбранного адреса подсети.</span><span class="sxs-lookup"><span data-stu-id="b666e-117">Use this field to enter a static IP address for the selected subnet address.</span></span> <span data-ttu-id="b666e-118">Для получения этого IP-адреса обратитесь к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="b666e-118">Contact your network administrator for this IP address.</span></span> <span data-ttu-id="b666e-119">Проверьте правильность введенного адреса для выбранного адреса подсети, иначе создание прослушивателя завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b666e-119">Ensure that you enter a valid address for the selected subnet address, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="b666e-120">**IPv4-адрес**</span><span class="sxs-lookup"><span data-stu-id="b666e-120">**IPv4 Address**</span></span>  
 <span data-ttu-id="b666e-121">Если вы выбрали для подсети адрес IPv4, введите в этом поле допустимый статический адрес IPv4.</span><span class="sxs-lookup"><span data-stu-id="b666e-121">If you selected the IPv4 subnet address of a subnet, enter a valid IPv4 static address here.</span></span>  
  
 <span data-ttu-id="b666e-122">**Маска подсети**</span><span class="sxs-lookup"><span data-stu-id="b666e-122">**Subnet Mask**</span></span>  
 <span data-ttu-id="b666e-123">Для адреса IPv4 это доступное только для чтения поле отображает маску подсети для выбранной подсети.</span><span class="sxs-lookup"><span data-stu-id="b666e-123">For an IPv4 address, this read-only field displays the subnet mask of the selected subnet.</span></span>  
  
 <span data-ttu-id="b666e-124">**IPv6-адрес**</span><span class="sxs-lookup"><span data-stu-id="b666e-124">**IPv6 Address**</span></span>  
 <span data-ttu-id="b666e-125">Если вы выбрали для подсети адрес IPv6, введите в этом поле допустимый статический адрес IPv6.</span><span class="sxs-lookup"><span data-stu-id="b666e-125">If you selected the IPv6 subnet address of a subnet, enter a valid IPv6 static address here.</span></span>  
  
 <span data-ttu-id="b666e-126">**OK**</span><span class="sxs-lookup"><span data-stu-id="b666e-126">**OK**</span></span>  
 <span data-ttu-id="b666e-127">Щелкните, чтобы добавить подсеть с выбранным адресом, а также указанным статическим IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="b666e-127">Click to create add the subnet whose address you selected, along with the static IP address that you specified.</span></span> <span data-ttu-id="b666e-128">Строка с этими значениями будет добавлена в сетку подсети в диалоговом окне **Создание прослушивателя группы доступности** или **Выбор реплик** .</span><span class="sxs-lookup"><span data-stu-id="b666e-128">A row containing these values will be added to the subnet grid of the **New Availability Group Listener** or **Specify Replicas** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b666e-129">В диалоговом окне **Добавление IP-адреса** IP-адрес не проверяется.</span><span class="sxs-lookup"><span data-stu-id="b666e-129">The **Add IP Address** dialog does not verify the IP address.</span></span> <span data-ttu-id="b666e-130">Кроме того, диалоговое окно не мешает добавить второй адрес подсети для подсети, уже добавленной в прослушиватель группы доступности.</span><span class="sxs-lookup"><span data-stu-id="b666e-130">Also the dialog does not prevent you from adding the second subnet address for a subnet that you have already added to the availability group listener.</span></span>  
  
 <span data-ttu-id="b666e-131">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="b666e-131">**Cancel**</span></span>  
 <span data-ttu-id="b666e-132">Щелкните, чтобы отменить выбор и вернуться в диалоговое окно **Создание прослушивателя группы доступности** или на вкладку **Прослушиватель** без добавления статического IP-адреса для подсети.</span><span class="sxs-lookup"><span data-stu-id="b666e-132">Click to cancel your selections, and return to the **New Availability Group Listener** dialog box or **Listener** tab without adding a static IP address for any subnet.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b666e-133">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b666e-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b666e-134">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b666e-134">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="b666e-135">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b666e-135">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b666e-136">Использование мастера добавления реплики в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b666e-136">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="b666e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b666e-137">See Also</span></span>  
 <span data-ttu-id="b666e-138">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b666e-138">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="b666e-139">[Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="b666e-139">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="b666e-140">Подключение клиента AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b666e-140">AlwaysOn Client Connectivity (SQL Server)</span></span>](always-on-client-connectivity-sql-server.md)  
  
  
