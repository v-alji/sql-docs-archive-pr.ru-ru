---
title: Использование базы знаний DQS по умолчанию | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b36af13b-9fcc-4168-bb92-214d600b1c93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3261c7af28bb5710ede203d1fe27c6540286e9f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656559"
---
# <a name="using-the-dqs-default-knowledge-base"></a><span data-ttu-id="1af02-102">Использование базы знаний DQS по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1af02-102">Using the DQS Default Knowledge Base</span></span>
  <span data-ttu-id="1af02-103">В этом разделе описывается база знаний **DQS Data**, которая используется по умолчанию и устанавливается со службами [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="1af02-103">This topic describes the default knowledge base, **DQS Data**, which is installed with [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="1af02-104">Эта готовая база данных содержит следующие домены.</span><span class="sxs-lookup"><span data-stu-id="1af02-104">This is a pre-built default knowledge base that contains the following domains:</span></span>  
  
-   <span data-ttu-id="1af02-105">**Страна/регион**. Содержит длинное (официальное) название страны или региона, общепринятое короткое название (используемое в списках, на картах и т. п.), двухбуквенное или трехбуквенное обозначение, а также трехзначный цифровой код каждого расположения.</span><span class="sxs-lookup"><span data-stu-id="1af02-105">**Country/Region**: Contains the conventional long (official name as designated by the country/region ) and short names (common name used in lists, on maps, etc. ), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="1af02-106">В качестве первого значения указывается длинное название страны.</span><span class="sxs-lookup"><span data-stu-id="1af02-106">Leading value is set to the long country name.</span></span>  
  
-   <span data-ttu-id="1af02-107">**Страна/регион (трехбуквенное первое значение)**. Содержит длинное (официальное) название страны или региона, общепринятое короткое название (используемое в списках, на картах и т. п.), двухбуквенное или трехбуквенное обозначение, а также трехзначный цифровой код каждого расположения.</span><span class="sxs-lookup"><span data-stu-id="1af02-107">**Country/Region (three-letter leading)**: Contains the conventional long (official name as designated by the country/region) and short names (common name used in lists, on maps, and so on), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="1af02-108">В качестве первого значения указывается трехбуквенное обозначение округа.</span><span class="sxs-lookup"><span data-stu-id="1af02-108">Leading values is set to County three-letter abbreviation.</span></span>  
  
-   <span data-ttu-id="1af02-109">**Страна/регион (двухбуквенное первое значение)**. Содержит длинное (официальное) название страны или региона, общепринятое короткое название (используемое в списках, на картах и т. п.), двухбуквенное или трехбуквенное обозначение, а также трехзначный цифровой код каждого расположения.</span><span class="sxs-lookup"><span data-stu-id="1af02-109">**Country/Region (two-letter leading)**: Contains the conventional long (official name as designated by the country/region ) and short names (common name used in lists, on maps, etc. ), two-letter abbreviation, three-letter abbreviation and three-digit code for each location.</span></span>  <span data-ttu-id="1af02-110">В качестве первого значения указывается двухбуквенное обозначение страны.</span><span class="sxs-lookup"><span data-stu-id="1af02-110">Leading value is set to the Country two-letter abbreviation.</span></span>  
  
-   <span data-ttu-id="1af02-111">**США — округа**. Содержит список округов США.</span><span class="sxs-lookup"><span data-stu-id="1af02-111">**US - Counties**: Contains a list of US counties.</span></span>  
  
-   <span data-ttu-id="1af02-112">**США — фамилии**. Содержит список фамилий, встречающихся 100 или более раз в отчете о переписи населения Census 2000.</span><span class="sxs-lookup"><span data-stu-id="1af02-112">**US - Last Name**: Contains a list of last names (surnames) occurring 100 or more times in the Census 2000.</span></span>  
  
-   <span data-ttu-id="1af02-113">**США — географические пункты**. Содержит список географических пунктов для 50 штатов, округа Колумбия и Пуэрто-Рико из переписи Census 2010.</span><span class="sxs-lookup"><span data-stu-id="1af02-113">**US - Places**: Contains a list of places for the 50 states, the District of Columbia, and Puerto Rico extracted from the Census 2010.</span></span>  
  
-   <span data-ttu-id="1af02-114">**США — штаты**. Содержит условное длинное (официальное) название и двухбуквенное обозначение каждого штата США.</span><span class="sxs-lookup"><span data-stu-id="1af02-114">**US - State**: Contains the conventional long (official) name and two-letter abbreviation for each state in US.</span></span> <span data-ttu-id="1af02-115">В качестве первого значения указывается длинное (официальное) название штата.</span><span class="sxs-lookup"><span data-stu-id="1af02-115">Leading value is set to the conventional state name.</span></span>  
  
-   <span data-ttu-id="1af02-116">**США — штат (двухбуквенный заголовок)**. Содержит условное длинное (официальное) название и двухбуквенное обозначение каждого штата США.</span><span class="sxs-lookup"><span data-stu-id="1af02-116">**US - State (2-letter heading)**: Contains the conventional long (official) name and two-letter abbreviation for each state in US.</span></span> <span data-ttu-id="1af02-117">В качестве первого значения указывается двухбуквенное обозначение штата.</span><span class="sxs-lookup"><span data-stu-id="1af02-117">Leading value is set to the two-letter abbreviation state name.</span></span>  
  
## <a name="using-the-default-knowledge-base"></a><span data-ttu-id="1af02-118">Использование базы знаний по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1af02-118">Using the Default Knowledge Base</span></span>  
 <span data-ttu-id="1af02-119">База знаний по умолчанию DQS Data служб DQS позволяет сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="1af02-119">You can use the default DQS knowledge base, DQS Data, in the following ways:</span></span>  
  
-   <span data-ttu-id="1af02-120">Быстро запустить и внедрить проект по качеству данных с помощью базы знаний по умолчанию, не создавая новую базу знаний служб DQS.</span><span class="sxs-lookup"><span data-stu-id="1af02-120">Quickly start and run a cleansing data quality project using the default knowledge base without first having to create a new knowledge base in DQS.</span></span>  
  
-   <span data-ttu-id="1af02-121">Выполнять действия по управлению доменами и обнаружению знаний, а также действия, связанные с политикой сопоставления, в базе данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1af02-121">Run the Domain Management, Knowledge Discovery, or Matching Policy activities on the default knowledge base.</span></span> <span data-ttu-id="1af02-122">Для этого нажмите кнопку **Открыть базу знаний** на экране [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md), выберите базу знаний **DQS Data** на экране **Открыть базу знаний** и выберите нужное действие в области **Выбрать действие** .</span><span class="sxs-lookup"><span data-stu-id="1af02-122">To do so, click **Open Knowledge Base** in the [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md), select the **DQS Data** knowledge base in the **Open Knowledge Base** screen, and then select the required activity in the **Select Activity** area.</span></span> <span data-ttu-id="1af02-123">Чтобы продолжить, нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="1af02-123">Click **Next** to proceed.</span></span>  
  
-   <span data-ttu-id="1af02-124">Создать новую базу знаний с помощью базы знаний по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1af02-124">Create a new knowledge base using the default knowledge base.</span></span> <span data-ttu-id="1af02-125">Сведения о создании базы знаний на основе существующей базы знаний см. в разделе [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="1af02-125">To create a knowledge base from an existing knowledge base, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md).</span></span>  
  
-   <span data-ttu-id="1af02-126">Использовать базу знаний по умолчанию можно в [компоненте DQS Cleansing  в службах Integration Services](https://go.microsoft.com/fwlink/?LinkId=238830) , а также в [надстройке Master Data Services для Excel](../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="1af02-126">Use it in the [DQS Cleansing component in Integration Services](https://go.microsoft.com/fwlink/?LinkId=238830) and [Master Data Services Add-in for Excel](../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af02-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="1af02-127">See Also</span></span>  
 [<span data-ttu-id="1af02-128">Базы знаний и домены DQS</span><span class="sxs-lookup"><span data-stu-id="1af02-128">DQS Knowledge Bases and Domains</span></span>](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md)  
  
  
