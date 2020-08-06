---
title: Microsoft Connector 1,1 для SAP BW | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5281f080-53d5-4679-aa26-f4cd4ac7a2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ec5cfe83b201976be0512c54b77bc79f8aa824b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736542"
---
# <a name="microsoft-connector-11-for-sap-bw"></a><span data-ttu-id="b9805-102">Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="b9805-102">Microsoft Connector 1.1 for SAP BW</span></span>
  <span data-ttu-id="b9805-103">[!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 для SAP BW — это набор из трех компонентов, позволяющих извлекать или загружать данные в систему SAP NetWeaver BW версии 7.</span><span class="sxs-lookup"><span data-stu-id="b9805-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consists of a set of three components that let you extract data from, or load data into, an SAP Netweaver BW version 7 system.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b9805-104">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b9805-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="b9805-105">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="b9805-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b9805-106">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="b9805-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="b9805-107">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="b9805-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="components"></a><span data-ttu-id="b9805-108">Components</span><span class="sxs-lookup"><span data-stu-id="b9805-108">Components</span></span>  
 <span data-ttu-id="b9805-109">[!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 для SAP BW состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="b9805-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following components:</span></span>  
  
-   <span data-ttu-id="b9805-110">Источник **SAP BW**— источник SAP BW — это компонент источника потока данных, позволяющий извлекать данные из системы SAP NetWeaver BW версии 7.</span><span class="sxs-lookup"><span data-stu-id="b9805-110">**SAP BW Source**-The SAP BW source is a data flow source component that lets you extract data from an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="b9805-111">**Назначение SAP BW**. SAP BW назначение — это компонент назначения потока данных, который позволяет загружать данные в систему SAP NetWeaver BW версии 7.</span><span class="sxs-lookup"><span data-stu-id="b9805-111">**SAP BW Destination**-The SAP BW destination is a data flow destination component that lets you load data into an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="b9805-112">**Диспетчер соединений SAP BW**. диспетчер соединений SAP BW подключает либо источник SAP BW, либо SAP BW назначение к системе SAP NetWeaver BW версии 7.</span><span class="sxs-lookup"><span data-stu-id="b9805-112">**SAP BW Connection Manager**-The SAP BW connection manager connects either an SAP BW source or SAP BW destination to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="b9805-113">Пошаговое руководство, в котором показано, как настроить и использовать диспетчер соединений, источник и назначение SAP BW см. в техническом документе [Использование службы SQL Server Integration Services с SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span><span class="sxs-lookup"><span data-stu-id="b9805-113">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span></span> <span data-ttu-id="b9805-114">В этом техническом документе также показано, как настроить необходимые объекты в SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b9805-114">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
## <a name="documentation"></a><span data-ttu-id="b9805-115">Документация</span><span class="sxs-lookup"><span data-stu-id="b9805-115">Documentation</span></span>  
 <span data-ttu-id="b9805-116">Этот файл справки для [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 для SAP BW содержит следующие разделы и подразделы:</span><span class="sxs-lookup"><span data-stu-id="b9805-116">This Help file for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contains the following topics and sections:</span></span>  
  
 [<span data-ttu-id="b9805-117">Установка Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="b9805-117">Installing the Microsoft Connector for 1.1 SAP BW</span></span>](installing-the-microsoft-connector-for-sap-bw.md)  
 <span data-ttu-id="b9805-118">Описывает требования к установке [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b9805-118">Describes the installation requirements for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="b9805-119">Компоненты Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="b9805-119">Microsoft Connector 1.1 for SAP BW Components</span></span>](microsoft-connector-for-sap-bw-components.md)  
 <span data-ttu-id="b9805-120">Описывает каждый компонент [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b9805-120">Describes each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="b9805-121">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="b9805-121">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
 <span data-ttu-id="b9805-122">Описывает пользовательский интерфейс каждого компонента [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b9805-122">Describes the user interface of each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
  
