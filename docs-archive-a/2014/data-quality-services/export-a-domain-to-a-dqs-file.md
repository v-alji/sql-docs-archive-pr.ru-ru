---
title: Экспорт домена в файл DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eba10d3d-b5c4-447b-8a30-fa07996cb28e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5d23e9efa2b3224aab5623201a54d1af56e49e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656568"
---
# <a name="export-a-domain-to-a-dqs-file"></a><span data-ttu-id="a759a-102">Экспорт домена в файл .dqs</span><span class="sxs-lookup"><span data-stu-id="a759a-102">Export a Domain to a .dqs File</span></span>
  <span data-ttu-id="a759a-103">В этом разделе описывается экспорт домена в файл .dqs в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="a759a-103">This topic describes how to export a domain to a .dqs file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="a759a-104">Экспортировать в файл данных можно домен или всю базу знаний.</span><span class="sxs-lookup"><span data-stu-id="a759a-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="a759a-105">Сведения об экспорте базы знаний см. в разделе [Экспорт базы знаний в файл DQS](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="a759a-105">For information about exporting a knowledge base, see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="a759a-106">Экспорт домена из одной базы знаний в файл данных DQS и последующий импорт в другую базу знаний упрощает процесс создания знаний и экономит время.</span><span class="sxs-lookup"><span data-stu-id="a759a-106">Exporting a domain from one knowledge base to a .dqs data file, and then importing it to another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="a759a-107">Благодаря этому можно использовать домен и его набор знаний совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="a759a-107">It enables you to share a domain and its knowledge with others.</span></span>  
  
 <span data-ttu-id="a759a-108">Можно экспортировать один одиночный домен или один составной домен.</span><span class="sxs-lookup"><span data-stu-id="a759a-108">You can export either a single domain or composite domain.</span></span> <span data-ttu-id="a759a-109">Файл DQS содержащий один домен, включает все сведения о домене, включая свойства домена, значения и сведения о правилах, кроме сведений о добавленных ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="a759a-109">A .dqs file containing a single domain includes all domain data including domain properties, values, and rules except for the attached reference data information.</span></span> <span data-ttu-id="a759a-110">Файл DQS, содержащий составной домен, содержит все данные составного домена, в том числе все данные для доменов, которые входят в составной домен, а также свойства, связи и правила составного домена, кроме сведений о ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="a759a-110">A .dqs file containing a composite domain includes all composite domain data, including all domain data for the domains that are contained in the composite domain, and the composite domain properties, relations, and rules, except for the reference data information.</span></span> <span data-ttu-id="a759a-111">После импорта файла DQS следует повторно добавить домен или составной домен в соответствующие службы ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="a759a-111">You must attach the domain or the composite domain to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="a759a-112">Экспортируются как опубликованные, так и неопубликованные данные.</span><span class="sxs-lookup"><span data-stu-id="a759a-112">Both published and unpublished data is exported.</span></span>  
  
 <span data-ttu-id="a759a-113">Файл данных DQS, созданный в процессе экспорта, зашифровывается, его просмотр становится невозможным.</span><span class="sxs-lookup"><span data-stu-id="a759a-113">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a759a-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a759a-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a759a-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a759a-115">Prerequisites</span></span>  
 <span data-ttu-id="a759a-116">Чтобы экспортировать домен в файл данных .dqs, необходимо предварительно создать и выбрать одиночный домен или составной домен, содержащий несколько одиночных доменов.</span><span class="sxs-lookup"><span data-stu-id="a759a-116">To export a domain to a .dqs data file, you must have created and selected a single domain or a composite domain containing multiple single domains.</span></span> <span data-ttu-id="a759a-117">Файл DQS не требуется, он будет создан в процессе экспорта.</span><span class="sxs-lookup"><span data-stu-id="a759a-117">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a759a-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="a759a-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a759a-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="a759a-119">Permissions</span></span>  
 <span data-ttu-id="a759a-120">Для экспорта домена в файл данных .dqs необходимы роли dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a759a-120">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a domain to a .dqs data file.</span></span>  
  
##  <a name="export-a-domain-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="a759a-121">Экспорт домена в файл DQS</span><span class="sxs-lookup"><span data-stu-id="a759a-121">Export a domain to a .dqs file</span></span>  
 <span data-ttu-id="a759a-122">Можно выполнить экспорт с любой страницы «Управление доменами».</span><span class="sxs-lookup"><span data-stu-id="a759a-122">You can export from any Domain Management page.</span></span> <span data-ttu-id="a759a-123">Команда экспорта доступна как в виде элемента управления в пользовательском интерфейсе, так и в виде команды контекстного меню на панели «Список доменов».</span><span class="sxs-lookup"><span data-stu-id="a759a-123">The export command is available from both a control in the user interface and from a command in the context menu of the Domain List pane.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a759a-124">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a759a-124">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a759a-125">На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] откройте базу знаний в разделе управления доменами.</span><span class="sxs-lookup"><span data-stu-id="a759a-125">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="a759a-126">На странице **Управление доменами** (с любой выбранной вкладкой) выберите одиночный или составной домен в списке **Домен** .</span><span class="sxs-lookup"><span data-stu-id="a759a-126">In the **Domain Management page** (with any tab selected), select a single domain or a composite domain in the **Domain** list.</span></span>  
  
4.  <span data-ttu-id="a759a-127">Щелкните значок **Экспортировать данные базы знаний** над списком доменов, затем щелкните **Экспортировать домен**.</span><span class="sxs-lookup"><span data-stu-id="a759a-127">Click the **Export Knowledge Base data** icon above the domain list, and then click **Export Domain**.</span></span> <span data-ttu-id="a759a-128">Также можно щелкнуть правой кнопкой мыши домен в списке **Домен** , указать пункт **Экспорт**, а затем выбрать команду **Экспортировать домен**.</span><span class="sxs-lookup"><span data-stu-id="a759a-128">Alternatively, you can right-click the domain in the **Domain** list, point to **Export**, and then click **Export Domain**.</span></span>  
  
5.  <span data-ttu-id="a759a-129">В диалоговом окне **Экспорт в файл данных** перейдите в папку, где нужно сохранить файл, присвойте файлу имя или оставьте имя по умолчанию, оставьте **Файлы данных DQS (\*.dqs)** в качестве **Типа файла** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a759a-129">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the default name, keep **DQS Data Files (\*.dqs)** as the **Save as type**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="a759a-130">В диалоговом окне **Экспортировать домен** убедитесь, что в строке состояния диалогового окна отобразилось сообщение о завершении экспорта.</span><span class="sxs-lookup"><span data-stu-id="a759a-130">In the **Export Domain** dialog box, verify that the status line in the dialog box indicates that the export completed.</span></span> <span data-ttu-id="a759a-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a759a-131">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a><span data-ttu-id="a759a-132">Дальнейшие действия. После экспорта домена в файл DQS</span><span class="sxs-lookup"><span data-stu-id="a759a-132">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="a759a-133">После экспорта домена в файл DQS можно импортировать домен в другую базу знаний.</span><span class="sxs-lookup"><span data-stu-id="a759a-133">After you export a domain to a .dqs file, you can import the domain into another knowledge base.</span></span>  
  
  
