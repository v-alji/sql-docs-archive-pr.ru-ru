---
title: Установка служб ADO.NET Data Services для поддержки экспорта каналов данных в списках SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f32527ae-f623-4e08-adfb-6d3262f5c2ac
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fb47804daee38427f48baefdf3997edda5fb90b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657485"
---
# <a name="install-adonet-data-services-to-support-data-feed-exports-of-sharepoint-lists"></a><span data-ttu-id="86d8b-102">Для поддержки экспорта списков SharePoint в виде веб-каналов данных установите службы ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="86d8b-102">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>
  <span data-ttu-id="86d8b-103">Для обеспечения возможности экспорта списков SharePoint в виде веб-каналов данных требуется служба ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="86d8b-103">ADO.NET Data Services is required for a data feed export of SharePoint lists.</span></span> <span data-ttu-id="86d8b-104">SharePoint 2010 не включает этот компонент в установщик компонентов, необходимых для SharePoint 2010, поэтому его необходимо устанавливать вручную.</span><span class="sxs-lookup"><span data-stu-id="86d8b-104">SharePoint 2010 does not include this component in the SharePoint Prerequisite Installer program, so you must install it manually.</span></span>  
  
 <span data-ttu-id="86d8b-105">Без этого предварительного требования при попытке использовать список SharePoint, экспортированный в виде потока данных, будет выдаваться следующая ошибка: "по соображениям безопасности DTD запрещен в этом XML-документе.</span><span class="sxs-lookup"><span data-stu-id="86d8b-105">Without this prerequisite, you will get the following error when you attempt to use a SharePoint list that was exported as a data feed: "For security reasons DTD is prohibited in this XML document.</span></span> <span data-ttu-id="86d8b-106">Для разрешения обработки DTD присвойте свойству ProhibitDtd в XmlReaderSettings значение false и передайте параметры в метод XmlReader.Create».</span><span class="sxs-lookup"><span data-stu-id="86d8b-106">To enable DTD processing set the ProhibitDtd property on XmlReaderSettings to false and pass the settings into XmlReader.Create method."</span></span>  
  
 <span data-ttu-id="86d8b-107">Используйте следующие инструкции для установки служб ADO.NET Data Services на каждом сервере SharePoint, для которого нужно разрешить экспорт списков как веб-каналов данных.</span><span class="sxs-lookup"><span data-stu-id="86d8b-107">Use the following instructions to install ADO.NET Data Services on every SharePoint server for which you want to allow lists to be exported as data feeds.</span></span>  
  
### <a name="download-and-install-adonet-data-services"></a><span data-ttu-id="86d8b-108">Загрузка и установка служб ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="86d8b-108">Download and install ADO.NET Data Services</span></span>  
  
1.  <span data-ttu-id="86d8b-109">Перейдите к документации по требованиям к оборудованию и программному обеспечению для SharePoint 2010, [требованиям к оборудованию и программному обеспечению (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span><span class="sxs-lookup"><span data-stu-id="86d8b-109">Go to the hardware and software requirements documentation for SharePoint 2010, [Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span></span>  
  
2.  <span data-ttu-id="86d8b-110">В окне **доступ к соответствующему программному обеспечению**найдите ссылку на ADO.NET Data Services 3,5, соответствующую используемой операционной системе (windows Server 2008 SP2 или windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="86d8b-110">In **Access to applicable software**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using (either Windows Server 2008 SP2 or Windows Server 2008 R2).</span></span>  
  
3.  <span data-ttu-id="86d8b-111">Щелкните ссылку и запустите программу установки службы.</span><span class="sxs-lookup"><span data-stu-id="86d8b-111">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d8b-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="86d8b-112">See Also</span></span>  
 [<span data-ttu-id="86d8b-113">Установка PowerPivot для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="86d8b-113">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
