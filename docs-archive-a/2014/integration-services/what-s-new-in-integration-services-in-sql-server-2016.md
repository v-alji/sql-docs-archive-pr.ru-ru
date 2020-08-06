---
title: Новые&#39;(Integration Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, what's new
- what's new [Integration Services]
ms.assetid: da6999c7-e5e3-4a59-a284-1da635995af1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84f0b668407c89e1d6acc3c8cfbda73f129ca19a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667780"
---
# <a name="what39s-new-integration-services"></a><span data-ttu-id="4bb2c-102">Новые&#39;(Integration Services)</span><span class="sxs-lookup"><span data-stu-id="4bb2c-102">What&#39;s New (Integration Services)</span></span>
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4bb2c-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]не изменяется из предыдущего выпуска.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is unchanged from the previous release.</span></span>  
  
 <span data-ttu-id="4bb2c-104">Сведения о других [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] продуктах и технологиях см. [в статье новые возможности SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="4bb2c-104">For information about other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="4bb2c-105">Дополнительные сведения об изменениях, связанных с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] бизнес-аналитикой, см. [в разделе новые возможности Analysis Services и бизнес-аналитики](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="4bb2c-105">For more information about changes related to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, see [What's New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span></span>  
  
##  <a name="rich-xml-validation-output-in-the-xml-task"></a><a name="ValidateXML"></a> <span data-ttu-id="4bb2c-106">Подробные данные о проверке XML в задачах XML</span><span class="sxs-lookup"><span data-stu-id="4bb2c-106">Rich XML validation output in the XML Task</span></span>  
 <span data-ttu-id="4bb2c-107">Активировав в задаче XML свойство `ValidationDetails`, вы сможете получить подробные результаты проверки XML-документа.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-107">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span> <span data-ttu-id="4bb2c-108">До появления свойства `ValidationDetails` проверка XML в задачах XML возвращала информацию только о том, есть ошибка в документе или нет. Сведения о самих ошибках и их расположении были недоступны.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-108">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="4bb2c-109">Теперь, если для свойства `ValidationDetails` задать значение True, выходной файл будет содержать подробные сведения обо всех ошибках, включая номера строк и позиции.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-109">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="4bb2c-110">Эти сведения можно использовать для анализа, поиска и исправления ошибок в XML-документах.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-110">You can use this information to understand, locate, and fix errors in XML documents.</span></span> <span data-ttu-id="4bb2c-111">Дополнительные сведения см. в разделе [Validate XML with the XML Task](control-flow/xml-task.md).</span><span class="sxs-lookup"><span data-stu-id="4bb2c-111">For more info, see [Validate XML with the XML Task](control-flow/xml-task.md).</span></span>  
  
 <span data-ttu-id="4bb2c-112">В [!INCLUDE[ssIS](../includes/ssis-md.md)] свойство `ValidationDetails` появилось с выходом пакета обновления 2 для [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bb2c-112">[!INCLUDE[ssIS](../includes/ssis-md.md)] introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="4bb2c-113">В то время о новом свойстве не было никакой информации.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-113">This new property was not announced or documented at that time.</span></span> <span data-ttu-id="4bb2c-114">Свойство `ValidationDetails` доступно также в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] и SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="4bb2c-114">The `ValidationDetails` property is also available in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb2c-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bb2c-115">See Also</span></span>  
 [<span data-ttu-id="4bb2c-116">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4bb2c-116">Features Supported by the Editions of SQL Server 2014</span></span>](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
