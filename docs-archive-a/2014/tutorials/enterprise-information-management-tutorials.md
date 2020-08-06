---
title: Учебники по управлению информацией на предприятии | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8745dc80-193d-4de0-9f17-ba648ab1e81c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b8cde162479645ab13a6ae000cc46e42e3c10e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666301"
---
# <a name="enterprise-information-management-tutorials"></a><span data-ttu-id="5d6e9-102">Учебники по информационному менеджменту предприятия</span><span class="sxs-lookup"><span data-stu-id="5d6e9-102">Enterprise Information Management Tutorials</span></span>
  <span data-ttu-id="5d6e9-103">В этом разделе содержатся учебники по управлению данными на предприятии с помощью технологий управления данными на предприятии (EIM), включенных в службы [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d6e9-103">This section contains tutorials for managing information in an enterprise by using Enterprise Information Management (EIM) technologies that are included in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span> <span data-ttu-id="5d6e9-104">Технологии управления данными на предприятии (EIM) предоставляют портфель корпоративных решений, которые позволяют организациям обеспечивать надежность и согласованность своих данных, для принятия на их основе важных бизнес-решений.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-104">Enterprise Integration Management (EIM) provides a portfolio of solutions that enable organizations to trust the credibility and consistency of their data so they can make critical business decisions.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="5d6e9-105">содержит следующие технологии, помогающие в реализации решений EIM на предприятии.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-105">has the following technologies that help you implement EIM solutions in your enterprise.</span></span>  
  
-   <span data-ttu-id="5d6e9-106">Службы SQL Server Integration Services (SSIS).</span><span class="sxs-lookup"><span data-stu-id="5d6e9-106">SQL Server Integration Services (SSIS).</span></span> <span data-ttu-id="5d6e9-107">Службы SSIS предоставляют мощную, расширяемую платформу для интеграции данных из различных источников в комплексное решение по извлечению, преобразованию и загрузке (ETL), которое будет поддерживать рабочие процессы компании, хранилище данных и управление основными данными.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-107">SSIS provides a powerful, extensible platform for integrating data from various sources in a comprehensive extract, transform, and load (ETL) solution that supports business workflows, a data warehouse, or master data management.</span></span>  
  
-   <span data-ttu-id="5d6e9-108">Службы SQL Server Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="5d6e9-108">SQL Server Data Quality Services (DQS).</span></span> <span data-ttu-id="5d6e9-109">DQS позволяет очищать, сопоставлять, стандартизировать и обогащать данные, что позволяет предоставлять доверенные данные для бизнес-аналитики, хранилища данных и рабочих нагрузок обработки транзакций.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-109">DQS enables you to cleanse, match, standardize, and enrich data, so you can deliver trusted information for business intelligence, a data warehouse, and transaction processing workloads.</span></span>  
  
-   <span data-ttu-id="5d6e9-110">Службы SQL Server Master Data Services (MDS).</span><span class="sxs-lookup"><span data-stu-id="5d6e9-110">SQL Server Master Data Services (MDS).</span></span> <span data-ttu-id="5d6e9-111">Службы MDS предоставляют центральный концентратор для данных, что обеспечивает целостность и согласованность данных в различных приложениях.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-111">MDS provides a central data hub that ensures that the integrity of information and consistency of data is constant across different applications.</span></span>  
  
 [<span data-ttu-id="5d6e9-112">Руководство по управлению информацией на предприятии с помощью служб SSIS, MDS и DQS &#91;учебнике&#93;</span><span class="sxs-lookup"><span data-stu-id="5d6e9-112">Enterprise Information Management using SSIS, MDS, and DQS Together &#91;Tutorial&#93;</span></span>](../../2014/tutorials/enterprise-information-management-using-ssis-mds-and-dqs-together-[tutorial].md)  
 <span data-ttu-id="5d6e9-113">В этом учебнике вы научитесь совместно использовать службы SSIS, MDS и DQS для внедрения примера решения по управлению данными предприятия (EIM).</span><span class="sxs-lookup"><span data-stu-id="5d6e9-113">In this tutorial, you learn how to use SSIS, MDS, and DQS together to implement a sample Enterprise Information Management (EIM) solution.</span></span> <span data-ttu-id="5d6e9-114">Сначала службы DQS будут использованы для создания базы знаний с набором знаний о данных поставщика (метаданные), очистки данных в файле Excel путем их сравнения с базой знаний и сопоставления данных для обнаружения и удаления повторений в данных.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-114">First, you use DQS to create a knowledgebase with the knowledge about the supplier data (metadata), cleanse the data in an Excel file against the knowledge base, and match the data to identify and remove duplicates in the data.</span></span> <span data-ttu-id="5d6e9-115">Затем надстройка MDS для Excel будет использована для передачи очищенных и сопоставленных данных в MDS.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-115">Next, you use the MDS Add-in for Excel to upload the cleansed and matched data to MDS.</span></span> <span data-ttu-id="5d6e9-116">Затем весь процесс будет автоматизирован с помощью решения служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="5d6e9-116">Then, you automate the whole process by using an SSIS solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6e9-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d6e9-117">See Also</span></span>  
 [<span data-ttu-id="5d6e9-118">Управление информацией на предприятии — Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d6e9-118">Enterprise Information Management - Microsoft SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=270871)  
  
  
