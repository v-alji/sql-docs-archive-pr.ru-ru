---
title: Добавление MSOLAP. 5 в качестве надежного поставщика данных в службах Excel | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 876ec613f18b2d91b5e06ab5fed4a7b258c30a36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667435"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a><span data-ttu-id="7b164-102">Добавление MSOLAP.5 в качестве надежного поставщика данных в службах Excel Services</span><span class="sxs-lookup"><span data-stu-id="7b164-102">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>
  <span data-ttu-id="7b164-103">MSOLAP.5 относится к поставщику OLE DB служб Analysis Services для SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="7b164-103">MSOLAP.5 refers to the Analysis Services OLE DB provider for SQL Server 2012.</span></span> <span data-ttu-id="7b164-104">Этот поставщик должен быть доверенным для служб Excel перед запросом на соединение, который обеспечивает доступность данных PowerPivot на сервере.</span><span class="sxs-lookup"><span data-stu-id="7b164-104">Excel Services must trust this provider before it will make the connection request that results in the availability of PowerPivot data on a server.</span></span>  
  
 <span data-ttu-id="7b164-105">Если PowerPivot для SharePoint настроено с помощью средства настройки PowerPivot, то MSOLAP.5 уже может быть доверенным поставщиком, поскольку это средство содержит действие, удовлетворяющее данному требованию.</span><span class="sxs-lookup"><span data-stu-id="7b164-105">If you configured PowerPivot for SharePoint using the PowerPivot Configuration Tool, MSOLAP.5 might already be a trusted provider because the tool includes an action that satisfies this requirement.</span></span> <span data-ttu-id="7b164-106">Однако если используется PowerShell или центр администрирования либо доверенный поставщик не включен в средство конфигурации, то поставщик может отсутствовать и его нужно добавить на этом этапе как часть настройки фермы для доступа к данным PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="7b164-106">However, if you are using PowerShell, Central Administration, or if you excluded the trusted provider action in the configuration tool, the provider might be missing, which case you should add it now as part of configuring the farm for PowerPivot data access.</span></span>  
  
 <span data-ttu-id="7b164-107">Этот шаг нужно выполнить только один раз для каждого приложения служб Excel Services.</span><span class="sxs-lookup"><span data-stu-id="7b164-107">You only need to perform this step once for each Excel Services service application.</span></span>  
  
 <span data-ttu-id="7b164-108">На каждом физическом сервере, обрабатывающем запросы к данным PowerPivot, например сервере PowerPivot для SharePoint или сервере служб Excel Services, должен быть установлен поставщик OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7b164-108">Each physical server that handles a PowerPivot data request, such as a PowerPivot for SharePoint server or an Excel Services server, must have the OLE DB provider installed on the computer.</span></span> <span data-ttu-id="7b164-109">Установка PowerPivot для SharePoint всегда включает поставщик OLE DB, однако если службы Excel работают на компьютере без PowerPivot для SharePoint, то поставщик следует установить вручную.</span><span class="sxs-lookup"><span data-stu-id="7b164-109">A PowerPivot for SharePoint installation always includes the OLE DB provider, but if Excel Services is running on a computer that does not have PowerPivot for SharePoint, you must install the provider manually.</span></span> <span data-ttu-id="7b164-110">Дополнительные сведения см. в статье [Установка поставщика OLE DB служб Analysis Services на серверах SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="7b164-110">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="add-a-trusted-provider-to-excel-services"></a><span data-ttu-id="7b164-111">Добавление надежного поставщика в службы Excel Services</span><span class="sxs-lookup"><span data-stu-id="7b164-111">Add a trusted provider to Excel Services</span></span>  
  
1.  <span data-ttu-id="7b164-112">В центре администрирования выберите **Управление приложениями служб**и щелкните приложение служб Excel Services.</span><span class="sxs-lookup"><span data-stu-id="7b164-112">In Central Administration, click **Manage service applications**, and then click the Excel Services service application.</span></span>  
  
2.  <span data-ttu-id="7b164-113">Щелкните **Надежные поставщики данных**.</span><span class="sxs-lookup"><span data-stu-id="7b164-113">Click **Trusted Data Providers**.</span></span>  
  
3.  <span data-ttu-id="7b164-114">Убедитесь, что в списке отображается MSOLAP.5.</span><span class="sxs-lookup"><span data-stu-id="7b164-114">Verify that MSOLAP.5 appears in the list.</span></span> <span data-ttu-id="7b164-115">MSOLAP.5 уже может быть надежным поставщиком, в зависимости от настройки PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b164-115">Depending on how you configured PowerPivot for SharePoint, MSOLAP.5 might already be trusted.</span></span>  
  
4.  <span data-ttu-id="7b164-116">Если его нет в списке, щелкните **Добавить надежный поставщик данных**.</span><span class="sxs-lookup"><span data-stu-id="7b164-116">If it is not listed, click **Add Trusted Data Provider**.</span></span>  
  
5.  <span data-ttu-id="7b164-117">В качестве идентификатора поставщика введите `MSOLAP.5`.</span><span class="sxs-lookup"><span data-stu-id="7b164-117">In Provider ID, type `MSOLAP.5`.</span></span>  
  
6.  <span data-ttu-id="7b164-118">В качестве типа поставщика необходимо указать OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7b164-118">For Provider Type, ensure that OLE DB is selected.</span></span>  
  
7.  <span data-ttu-id="7b164-119">В поле "Описание поставщика" введите **Поставщик Microsoft OLE DB для OLAP Services 11.0**.</span><span class="sxs-lookup"><span data-stu-id="7b164-119">In Provider Description, type **Microsoft OLE DB Provider for OLAP Services 11.0**.</span></span>  
  
  
