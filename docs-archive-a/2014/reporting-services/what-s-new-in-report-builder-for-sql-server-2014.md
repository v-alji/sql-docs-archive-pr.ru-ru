---
title: Новые&#39;построитель отчетов для SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ce72af225130bc3f081a53008a303c5213db636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665227"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a><span data-ttu-id="56e95-102">Новые&#39;в построитель отчетов для SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="56e95-102">What&#39;s New in Report Builder for SQL Server 2014</span></span>
  <span data-ttu-id="56e95-103">В [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] появилось несколько функций служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56e95-103">The [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] introduces a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span>  
  
 <span data-ttu-id="56e95-104">Сведения о функциях этого выпуска для других [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] продуктов и технологий см. [в статье новые возможности SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="56e95-104">For information about features in this release for other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="56e95-105">Последние сведения и ресурсы, относящиеся к новым функциям этого выпуска, см. в разделе Дополнительные сведения о новых возможностях [SQL Server Reporting Services (службы SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span><span class="sxs-lookup"><span data-stu-id="56e95-105">For the most recent information and resources regarding new features in this release, see [Additional information on what is new in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span></span>  
  
##  <a name="excel-renderer-for-microsoft-excel-2007-2010-and-microsoft-excel-2003"></a><a name="ExcelRenderer"></a><span data-ttu-id="56e95-106">Модуль подготовки отчетов Excel для Microsoft Excel 2007-2010 и Microsoft Excel 2003</span><span class="sxs-lookup"><span data-stu-id="56e95-106">Excel Renderer for Microsoft Excel 2007-2010 and Microsoft Excel 2003</span></span>  
 <span data-ttu-id="56e95-107">Модуль подготовки отчетов Excel для служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], который впервые появился в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], подготавливает к просмотру отчет как документ Excel, совместимый с [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007–2010, а также [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 с установленным пакетом совместимости Microsoft Office для Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="56e95-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Excel rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as an Excel document that is compatible with [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 as well as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="56e95-108">Это формат Office Open XML, а соответствующие файлы имеют расширение XLSX.</span><span class="sxs-lookup"><span data-stu-id="56e95-108">The format is Office Open XML and the file extension of files is .xlsx.</span></span>  
  
 <span data-ttu-id="56e95-109">Модуль подготовки отчетов в формате Excel устраняет ограничения прежней версии, совместимой с Excel 2003.</span><span class="sxs-lookup"><span data-stu-id="56e95-109">This Excel-rendering extension removes limitations of the earlier version, compatible with Excel 2003.</span></span> <span data-ttu-id="56e95-110">В следующих списках перечислены новые возможности модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="56e95-110">The following lists the improvement in the rendering extension:</span></span>  
  
-   <span data-ttu-id="56e95-111">Максимальное число строк на листе равно 1 048 576.</span><span class="sxs-lookup"><span data-stu-id="56e95-111">Maximum rows per worksheet is 1,048,576.</span></span>  
  
-   <span data-ttu-id="56e95-112">Максимальное число столбцов на листе равно 16 384.</span><span class="sxs-lookup"><span data-stu-id="56e95-112">Maximum columns per worksheet is 16,384.</span></span>  
  
-   <span data-ttu-id="56e95-113">Число цветов, которые можно использовать на листе, приблизительно равно 16 млн (24-разрядный цвет).</span><span class="sxs-lookup"><span data-stu-id="56e95-113">Number of colors allowed in a worksheet is approximately 16 million (24-bit color).</span></span>  
  
-   <span data-ttu-id="56e95-114">Сжатие данных в формате ZIP обеспечивает меньший размер файлов.</span><span class="sxs-lookup"><span data-stu-id="56e95-114">ZIP compression provides smaller files sizes.</span></span>  
  
 <span data-ttu-id="56e95-115">Дополнительные сведения см. в разделе [Экспорт в Microsoft Excel (построитель отчетов и службы SSRS)](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="56e95-115">For more information, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="word-renderer-for-microsoft-word-2007-2010-and-microsoft-word-2003"></a><a name="WordRenderer"></a><span data-ttu-id="56e95-116">Модуль подготовки отчетов Word для Microsoft Word 2007-2010 и Microsoft Word 2003</span><span class="sxs-lookup"><span data-stu-id="56e95-116">Word Renderer for Microsoft Word 2007-2010 and Microsoft Word 2003</span></span>  
 <span data-ttu-id="56e95-117">Модуль подготовки отчетов Word для служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], который впервые появился в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], подготавливает к просмотру отчет как документ Word, совместимый с [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007–2010, а также [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 с установленным пакетом совместимости [!INCLUDE[msCoName](../includes/msconame-md.md)] Office для Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="56e95-117">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Word rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as a Word document that is compatible with [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 as well as [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="56e95-118">Это формат Office Open XML, а также соответствующие файлы имеют расширение DOCX.</span><span class="sxs-lookup"><span data-stu-id="56e95-118">The format is Office Open XML and the file extension of files is docx.</span></span>  
  
 <span data-ttu-id="56e95-119">В дополнение к тому, что для экспортированных отчетов стали доступными новые средства Word 2007–2010, файлы экспортированных отчетов с расширением DOCX, как правило, имеют меньший размер.</span><span class="sxs-lookup"><span data-stu-id="56e95-119">In addition to making the features that are new in Word 2007-2010 available to exported reports, \*.docx files of exported reports tend to be smaller.</span></span> <span data-ttu-id="56e95-120">Отчеты, экспортированные с использованием модуля подготовки отчетов Word, обычно намного меньше, чем такие же отчеты, экспортированные с использованием модуля подготовки отчетов Word 2003.</span><span class="sxs-lookup"><span data-stu-id="56e95-120">Reports exported by using the Word renderer are typically significantly smaller than the same reports exported by using the Word 2003 renderer.</span></span>  
  
 <span data-ttu-id="56e95-121">Дополнительные сведения см. в разделе [Экспорт в Microsoft Word (построитель отчетов и службы SSRS)](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="56e95-121">For more information, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e95-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="56e95-122">See Also</span></span>  
 [<span data-ttu-id="56e95-123">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="56e95-123">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
