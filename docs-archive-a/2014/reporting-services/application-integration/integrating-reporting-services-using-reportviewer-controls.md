---
title: Интеграция служб Reporting Services с помощью элементов управления ReportViewer | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
- integrating reports [Reporting Services]
ms.assetid: 3ba47fb4-73a9-4059-89fd-329adebe94a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 18e28dbf1557bf36106b454738d0c0bfc037f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654928"
---
# <a name="integrating-reporting-services-using-the-reportviewer-controls"></a><span data-ttu-id="1ce99-102">Интеграция служб Reporting Services с помощью элементов управления ReportViewer</span><span class="sxs-lookup"><span data-stu-id="1ce99-102">Integrating Reporting Services Using the ReportViewer Controls</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="1ce99-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)]предоставляет два элемента управления ReportViewer для интеграции функций просмотра отчетов в приложения.</span><span class="sxs-lookup"><span data-stu-id="1ce99-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] provides two ReportViewer controls for integrating report viewing functionality into your applications.</span></span> <span data-ttu-id="1ce99-104">К ним относятся версия для приложений на базе Windows Forms, а также версия для приложений Web Forms.</span><span class="sxs-lookup"><span data-stu-id="1ce99-104">There is a version for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="1ce99-105">Эти элементы управления предоставляют одинаковые функциональные возможности, однако каждый из них разработан с учетом особенностей соответствующей среды.</span><span class="sxs-lookup"><span data-stu-id="1ce99-105">Each control provides similar functionality but each is designed to target their individual environments.</span></span> <span data-ttu-id="1ce99-106">Оба элемента управления могут обрабатывать отчеты, развернутые на сервере отчетов (режим удаленной обработки) или скопированные на компьютер, где [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не установлен (режим локальной обработки).</span><span class="sxs-lookup"><span data-stu-id="1ce99-106">Both controls can process reports that have been deployed to a report server (remote processing mode) or have been copied to a computer where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has not been installed (local processing mode).</span></span>  
  
 <span data-ttu-id="1ce99-107">Элемент управления ReportViewer не включает встроенную поддержку динамической адаптации к разным устройствам с разным разрешением экрана.</span><span class="sxs-lookup"><span data-stu-id="1ce99-107">The ReportViewer control does not include built-in support for dynamically adapting to different devices with different screen resolutions.</span></span>  
  
## <a name="remote-processing-mode"></a><span data-ttu-id="1ce99-108">Удаленный режим обработки</span><span class="sxs-lookup"><span data-stu-id="1ce99-108">Remote Processing Mode</span></span>  
 <span data-ttu-id="1ce99-109">Режим удаленной обработки является предпочтительным методом просмотра отчетов, развернутых на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1ce99-109">Remote processing mode is the preferred method for viewing reports that have been deployed to a report server.</span></span> <span data-ttu-id="1ce99-110">Режим удаленной обработки предоставляет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="1ce99-110">Remote processing mode provides the following advantages:</span></span>  
  
-   <span data-ttu-id="1ce99-111">Удаленная обработка является оптимальным решением для выполнения отчетов, поскольку отчеты обрабатываются сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="1ce99-111">Remote processing provides an optimized solution for running reports because the report is processed by the report server.</span></span>  
  
-   <span data-ttu-id="1ce99-112">Таким образом, всю обработку выполняет сервер отчетов, поэтому запрос отчета может обрабатываться несколькими серверами отчетов в варианте с масштабированием по горизонтали или многопроцессорным сервером в варианте с масштабированием по вертикали.</span><span class="sxs-lookup"><span data-stu-id="1ce99-112">Because all processing is handled by the report server, a report request can be processed by multiple report servers in a scale-out deployment or a server that has multiple processors in a scale-up scenario.</span></span>  
  
 <span data-ttu-id="1ce99-113">Кроме того, эксплуатация отчетов в удаленном режиме позволяет воспользоваться полным набором функциональных возможностей сервера отчетов, в том числе всеми модулями подготовки к просмотру и обработки данных.</span><span class="sxs-lookup"><span data-stu-id="1ce99-113">In addition, reports run in remote mode can utilize the full functionality of the report server including all rendering and data extensions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ce99-114">Список модулей, доступных для элемента управления ReportViewer при работе в режиме удаленной обработки, зависит от выпуска служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], установленного на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1ce99-114">The list of extensions available to the ReportViewer control when it is running in remote processing mode depends on the edition of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is installed on the report server.</span></span>  
  
## <a name="local-processing-mode"></a><span data-ttu-id="1ce99-115">Локальной режим обработки</span><span class="sxs-lookup"><span data-stu-id="1ce99-115">Local Processing Mode</span></span>  
 <span data-ttu-id="1ce99-116">В режиме локальной обработки предусмотрен альтернативный метод просмотра и подготовки отчетов на тот случай, если службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не установлены.</span><span class="sxs-lookup"><span data-stu-id="1ce99-116">Local processing mode provides an alternative method for viewing and rendering reports when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not installed.</span></span> <span data-ttu-id="1ce99-117">В отличие от удаленной обработки, в данном режиме элементу управления доступно лишь подмножество функциональных возможностей, предоставляемых сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="1ce99-117">Unlike remote processing only a subset of the functionality provided by the report server is available in the control.</span></span> <span data-ttu-id="1ce99-118">В режиме локальной обработки обработка данных не выполняется элементом управления, а реализуется приложением, в котором размещается отчет.</span><span class="sxs-lookup"><span data-stu-id="1ce99-118">In local processing mode, data processing is not handled by the control but rather implemented by the hosting application.</span></span> <span data-ttu-id="1ce99-119">Но обработка отчета выполняется самим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="1ce99-119">However report processing is handled by the control itself.</span></span> <span data-ttu-id="1ce99-120">В режиме локальной обработки доступны только модули подготовки отчетов в форматах PDF, Excel, Word и в формате изображений.</span><span class="sxs-lookup"><span data-stu-id="1ce99-120">In local processing mode, only the PDF, Excel, Word, and Image rendering extensions are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce99-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ce99-121">See Also</span></span>  
 <span data-ttu-id="1ce99-122">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1ce99-122">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="1ce99-123">Создание отчетов SSRS с помощью Visual Studio (блог)</span><span class="sxs-lookup"><span data-stu-id="1ce99-123">Create SSRS Reports Using Visual Studio (Blog)</span></span>](https://jwcooney.com/2015/01/07/ssrs-basics-set-up-visual-studio-to-write-a-new-ssrs-report/)  
  
  
