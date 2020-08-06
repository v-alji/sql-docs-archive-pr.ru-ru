---
title: Формат выходного XML-файла (ssbdiagnose) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 612b317f7220f502faf1adc82cf9c1dcc8bc20a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735701"
---
# <a name="xml-output-file-format-ssbdiagnose"></a><span data-ttu-id="05804-102">Формат выходного XML-файла (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="05804-102">XML Output File Format (ssbdiagnose)</span></span>
  <span data-ttu-id="05804-103">Если запустить программу **ssbdiagnose** с параметром **-XML** , то выходные данные будут выданы в виде XML-файла.</span><span class="sxs-lookup"><span data-stu-id="05804-103">The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch.</span></span> <span data-ttu-id="05804-104">В выходном XML-файле содержатся заголовок и ошибки, обнаруженные в результате анализа конфигурации компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] или диалога.</span><span class="sxs-lookup"><span data-stu-id="05804-104">The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed.</span></span> <span data-ttu-id="05804-105">Для анализа ошибок, перечисленных в файле, и создания отчета по ним можно написать пользовательское приложение.</span><span class="sxs-lookup"><span data-stu-id="05804-105">You can write an application to analyze or report on the errors listed in the file.</span></span> <span data-ttu-id="05804-106">Кроме того, XML-файл можно просмотреть в стандартном XML-редакторе, например в XML-блокноте.</span><span class="sxs-lookup"><span data-stu-id="05804-106">Or, you can view the XML file in a general XML editor, such as XML Notepad.</span></span>  
  
 <span data-ttu-id="05804-107">Выходной файл программы **ssbdiangose** содержит корневой элемент DiagnosticInformation с двумя дочерними типами:</span><span class="sxs-lookup"><span data-stu-id="05804-107">An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:</span></span>  
  
-   <span data-ttu-id="05804-108">элемент Banner с данными заголовка;</span><span class="sxs-lookup"><span data-stu-id="05804-108">A Banner element with header information.</span></span>  
  
-   <span data-ttu-id="05804-109">элемент Issue для каждой проблемы, обнаруженной программой **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="05804-109">An Issue element for each issue that is reported by **ssbdiagnose**.</span></span>  
  
## <a name="diagnosticinformation-root-element"></a><span data-ttu-id="05804-110">Корневой элемент DiagnosticInformation</span><span class="sxs-lookup"><span data-stu-id="05804-110">DiagnosticInformation Root Element</span></span>  
  
-   [<span data-ttu-id="05804-111">Элемент DiagnosticInformation (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="05804-111">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a><span data-ttu-id="05804-112">Элемент Banner</span><span class="sxs-lookup"><span data-stu-id="05804-112">Banner Element</span></span>  
  
-   [<span data-ttu-id="05804-113">Элемент Banner (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="05804-113">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a><span data-ttu-id="05804-114">Элемент Issue</span><span class="sxs-lookup"><span data-stu-id="05804-114">Issue Element</span></span>  
  
-   [<span data-ttu-id="05804-115">Элемент Issue (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="05804-115">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a><span data-ttu-id="05804-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="05804-116">See Also</span></span>  
 [<span data-ttu-id="05804-117">Программа ssbdiagnose (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="05804-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
