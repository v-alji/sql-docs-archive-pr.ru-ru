---
title: Как запустить мастер анализа помощника по обновлению | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Analysis Wizard
ms.assetid: d7d2a1e2-1179-4c05-9b0f-555b04dd1199
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7c3e5e8a52c3b166b076aedb122e68f860037edf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668061"
---
# <a name="how-to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="a8502-102">Как запустить мастер анализа помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="a8502-102">How to: Run the Upgrade Advisor Analysis Wizard</span></span>
  <span data-ttu-id="a8502-103">Мастер анализа помощника по обновлению запускается с начальной страницы помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="a8502-103">You start the Upgrade Advisor Analysis Wizard from the Upgrade Advisor start page.</span></span> <span data-ttu-id="a8502-104">В этом разделе описывается запуск мастера анализа помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="a8502-104">This topic describes how to run the Upgrade Advisor Analysis Wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8502-105">При работе мастера анализа помощника по обновлению помощник по обновлению сохраняет отчеты в папку отчетов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8502-105">When you run the Upgrade Advisor Analysis Wizard, Upgrade Advisor saves the reports in the default report folder.</span></span> <span data-ttu-id="a8502-106">Однако средство просмотра отчетов отображает только пять последних сохраненных отчетов.</span><span class="sxs-lookup"><span data-stu-id="a8502-106">However, the report viewer displays only the five latest saved reports.</span></span> <span data-ttu-id="a8502-107">По умолчанию для отчетов задано расположение "Мои документы": \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Обновление Advisor\110\Reports.</span><span class="sxs-lookup"><span data-stu-id="a8502-107">The default location for the reports is My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span></span>  
  
### <a name="to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="a8502-108">Запуск мастера анализа помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="a8502-108">To run the Upgrade Advisor Analysis Wizard</span></span>  
  
1.  <span data-ttu-id="a8502-109">На начальной странице помощника по обновлению щелкните ссылку **Запустить мастер анализа помощника по обновлению**.</span><span class="sxs-lookup"><span data-stu-id="a8502-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Analysis Wizard**.</span></span>  
  
2.  <span data-ttu-id="a8502-110">На странице \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] компоненты\*\* введите имя сервера для проверки в поле **имя сервера** и нажмите кнопку **обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="a8502-110">On the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components** page, enter the name of the server to scan in the **Server name** box, and then click **Detect**.</span></span> <span data-ttu-id="a8502-111">Учитывайте следующие рекомендации при выборе имени сервера.</span><span class="sxs-lookup"><span data-stu-id="a8502-111">Use the following guidelines for the server name:</span></span>  
  
    -   <span data-ttu-id="a8502-112">Чтобы проверить некластеризованные экземпляры, введите имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="a8502-112">To scan nonclustered instances, enter the computer name.</span></span>  
  
    -   <span data-ttu-id="a8502-113">Для просмотра кластеризованных экземпляров введите виртуальное имя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8502-113">To scan clustered instances, enter the virtual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name.</span></span>  
  
    -   <span data-ttu-id="a8502-114">Чтобы проверить некластеризованные компоненты, установленные на узле кластера, введите имя узла.</span><span class="sxs-lookup"><span data-stu-id="a8502-114">To scan nonclustered components that are installed on a node of a cluster, enter the node name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="a8502-115">Помощник по обновлению не поддерживает соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который не настроен на использование стандартного порта (1433) для соединений с клиентами.</span><span class="sxs-lookup"><span data-stu-id="a8502-115">Upgrade Advisor does not support connecting to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is not set to use the standard port (1433) for client connections.</span></span> <span data-ttu-id="a8502-116">Если требуется установить соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который не использует стандартный порт (1433), создайте псевдоним с помощью IP-адреса и порта.</span><span class="sxs-lookup"><span data-stu-id="a8502-116">If you want to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that does not use the standard port (1433), create an alias using the IP address and the port.</span></span> <span data-ttu-id="a8502-117">Дополнительные сведения о настройке клиентских протоколов и создании псевдонима для экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="a8502-117">For more information about configuring client protocols and creating an alias for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
    >   
    >  <span data-ttu-id="a8502-118">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на компьютере, на котором запущен помощник по обновлению, не установлен, нажмите кнопку **Пуск**и запустите `cliconfg` .</span><span class="sxs-lookup"><span data-stu-id="a8502-118">If you do not have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer on which you are running Upgrade Advisor, click **Start**, and then run  `cliconfg`.</span></span> <span data-ttu-id="a8502-119">Откроется диалоговое окно \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Клиентская сетевая программа\*\* .</span><span class="sxs-lookup"><span data-stu-id="a8502-119">This opens the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility** dialog box.</span></span> <span data-ttu-id="a8502-120">Для создания псевдонима перейдите на вкладку **Псевдоним** .</span><span class="sxs-lookup"><span data-stu-id="a8502-120">Use the **Alias** tab to create the alias.</span></span>  
  
3.  <span data-ttu-id="a8502-121">Просмотрите список обнаруженных компонентов, при необходимости измените выбор и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8502-121">Review the list of components detected, modify the selections as necessary, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a8502-122">На странице **Параметры соединения** выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который необходимо просмотреть, укажите метод проверки подлинности и при необходимости введите имя и пароль, после чего нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a8502-122">On the **Connection Parameters** page, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you want to scan, select the authentication method and, if necessary, enter user name and password information, and then click **Next**.</span></span>  
  
     <span data-ttu-id="a8502-123">Имя экземпляра по умолчанию — MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="a8502-123">The default instance name is MSSQLSERVER.</span></span>  
  
5.  <span data-ttu-id="a8502-124">Введите запрошенную информацию по выбранным компонентам.</span><span class="sxs-lookup"><span data-stu-id="a8502-124">For selected components, enter the requested information.</span></span> <span data-ttu-id="a8502-125">Дополнительные сведения об отдельных диалоговых окнах см. в разделе [Справочник по пользовательскому интерфейсу помощника по обновлению](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a8502-125">For more information about individual dialog boxes, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
6.  <span data-ttu-id="a8502-126">На странице **Подтверждение настроек помощника по обновлению** просмотрите введенную информацию.</span><span class="sxs-lookup"><span data-stu-id="a8502-126">On the **Confirm Upgrade Advisor Setting** page, review the information that you entered.</span></span> <span data-ttu-id="a8502-127">Если вы хотите отправить отчет об обновлении, можно выбрать пункт \*\*Отправить отчеты [!INCLUDE[msCoName](../../includes/msconame-md.md)] \*\* .</span><span class="sxs-lookup"><span data-stu-id="a8502-127">You can select **Send reports to [!INCLUDE[msCoName](../../includes/msconame-md.md)]** if you want to submit your upgrade report.</span></span> <span data-ttu-id="a8502-128">Здесь же можно просмотреть сведения о политике конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="a8502-128">You can also review the privacy policy.</span></span>  
  
7.  <span data-ttu-id="a8502-129">Щелкните **Запуск** , чтобы проанализировать выбранный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8502-129">Click **Run** to analyze the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
8.  <span data-ttu-id="a8502-130">После завершения анализа щелкните **Запустить отчет** , чтобы просмотреть обнаруженные проблемы, связанные с обновлением.</span><span class="sxs-lookup"><span data-stu-id="a8502-130">When the analysis is finished, click **Launch Report** to view the detected upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8502-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8502-131">See Also</span></span>  
 <span data-ttu-id="a8502-132">[Руководство. Запуск помощника по обновлению](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="a8502-132">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="a8502-133">[Запуск помощника по обновлению &#40;пользовательского интерфейса&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="a8502-133">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 [<span data-ttu-id="a8502-134">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="a8502-134">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
