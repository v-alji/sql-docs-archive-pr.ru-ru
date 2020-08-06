---
title: Импорт отчетов из Microsoft Access (Reporting Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Access reports [Reporting Services]
- importing reports
ms.assetid: 4f29d5b8-b77d-4714-a84a-05523df55646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 862d8b90f3c91dffda35971677db7fdc231c1b63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666971"
---
# <a name="import-reports-from-microsoft-access-reporting-services"></a><span data-ttu-id="92320-102">Импорт отчетов из базы данных Microsoft Access (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="92320-102">Import Reports from Microsoft Access (Reporting Services)</span></span>
  <span data-ttu-id="92320-103">В конструктор отчетов можно импортировать отчеты из [!INCLUDE[msCoName](../includes/msconame-md.md)] базы данных или проекта Access.</span><span class="sxs-lookup"><span data-stu-id="92320-103">In Report Designer, you can import reports from a [!INCLUDE[msCoName](../includes/msconame-md.md)] Access database or project.</span></span> <span data-ttu-id="92320-104">СУБД Access 2002 или его более поздняя версия должен быть установлен на том же компьютере, что и конструктор отчетов.</span><span class="sxs-lookup"><span data-stu-id="92320-104">Access 2002 or a later version must be installed on the same computer on which Report Designer is installed.</span></span>  
  
 <span data-ttu-id="92320-105">При использовании этой функции выполняется импорт всех отчетов базы данных или проекта.</span><span class="sxs-lookup"><span data-stu-id="92320-105">When you use the import feature, all reports in the database or project file are imported.</span></span> <span data-ttu-id="92320-106">Если файл Access содержит много отчетов, можно создать отдельный проект отчета, в который будет выполняться импорт отчетов, а затем открывать каждый файл на языке определения отчетов в главном проекте отчета.</span><span class="sxs-lookup"><span data-stu-id="92320-106">If your Access file contains many reports, you may want to create a separate report project into which to import the reports, and then open the individual RDL files in your main report project.</span></span> <span data-ttu-id="92320-107">После импорта отчетов в конструктор отчетов их можно изменять.</span><span class="sxs-lookup"><span data-stu-id="92320-107">You can edit the reports after they are imported into Report Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92320-108">Службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] поддерживают не все объекты отчетов Access.</span><span class="sxs-lookup"><span data-stu-id="92320-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] does not support all Access report objects.</span></span> <span data-ttu-id="92320-109">Непреобразованные элементы отображаются в окне **список задач** .</span><span class="sxs-lookup"><span data-stu-id="92320-109">Items that are not converted are displayed in the **Task List** window.</span></span> <span data-ttu-id="92320-110">Дополнительные сведения см. в разделе [Поддерживаемые функции отчетов Access &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92320-110">For more information, see [Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span></span>  
  
### <a name="to-import-reports-from-microsoft-access"></a><span data-ttu-id="92320-111">Импорт отчетов из Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="92320-111">To import reports from Microsoft Access</span></span>  
  
1.  <span data-ttu-id="92320-112">Откройте или создайте проект, в который планируется импортировать отчеты.</span><span class="sxs-lookup"><span data-stu-id="92320-112">Open or create a project into which to import the reports.</span></span>  
  
2.  <span data-ttu-id="92320-113">В меню **проект** выберите команду **Импорт отчетов**, а затем выберите пункт **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="92320-113">On the **Project** menu, point to **Import Reports**, and then click **Microsoft Access**.</span></span> <span data-ttu-id="92320-114">Можно также щелкнуть правой кнопкой мыши проект в обозреватель решений, выбрать пункт **Импорт отчетов**, а затем выбрать пункт **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="92320-114">Alternatively, right-click the project in Solution Explorer, point to **Import Reports**, and then click **Microsoft Access**.</span></span>  
  
3.  <span data-ttu-id="92320-115">В диалоговом окне **Открыть** выберите базу данных Access (MDB, ACCDB) или проект (ADP), содержащий отчеты, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="92320-115">In the **Open** dialog box, select the Access database (.mdb, .accdb) or project (.adp) that contains the reports, and then click **Open**.</span></span> <span data-ttu-id="92320-116">Все отчеты в базе данных или файле проекта импортируются в папку «Отчеты» в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="92320-116">All the reports in the database or project file are imported and listed in the Reports folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="92320-117">Проверьте окно **список задач** на наличие ошибок сборки.</span><span class="sxs-lookup"><span data-stu-id="92320-117">Check the **Task List** window for build errors.</span></span> <span data-ttu-id="92320-118">Чтобы открыть окно **список задач** , откройте меню **вид** , наведите указатель на пункт **другие окна**, а затем щелкните **список задач**.</span><span class="sxs-lookup"><span data-stu-id="92320-118">To view the **Task List** window, open the **View** menu, point to **Other Windows**, and then click **Task List**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92320-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="92320-119">See Also</span></span>  
 [<span data-ttu-id="92320-120">Разработка отчетов с использованием конструктора отчетов (SSRS)</span><span class="sxs-lookup"><span data-stu-id="92320-120">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
