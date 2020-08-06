---
title: Экспорт базы знаний в файл DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 81dfc8e7f20fae9dacd521595d101be3117a6794
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656563"
---
# <a name="export-a-knowledge-base-to-a-dqs-file"></a><span data-ttu-id="220ac-102">Экспорт базы знаний в файл .dqs</span><span class="sxs-lookup"><span data-stu-id="220ac-102">Export a Knowledge Base to a .dqs File</span></span>
  <span data-ttu-id="220ac-103">В этом разделе описывается экспорт всей базы знаний в файл данных DQS в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="220ac-103">This topic describes how to export an entire knowledge base to a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="220ac-104">Экспортировать в файл данных можно домен или всю базу знаний.</span><span class="sxs-lookup"><span data-stu-id="220ac-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="220ac-105">Сведения об экспорте домена см. в разделе [Экспорт домена в файл DQS](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="220ac-105">For information about exporting a domain, see [Export a Domain to a .dqs File](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="220ac-106">Экспорт базы знаний в файл DQS и последующий импорт в качестве другой базы знаний упрощает процесс создания знаний и экономит время.</span><span class="sxs-lookup"><span data-stu-id="220ac-106">Exporting a knowledge base to a .dqs file, and then importing it as another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="220ac-107">Благодаря этому можно использовать базу знаний и ее знания совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="220ac-107">It enables you to share a knowledge base and its knowledge with others.</span></span> <span data-ttu-id="220ac-108">Файл DQS будет содержать все сведения базы знаний, включая домены и политику сопоставления, кроме присоединенных ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="220ac-108">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="220ac-109">После импорта файла DQS следует повторно добавить необходимые домены в соответствующие службы ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="220ac-109">You must attach the required domains to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="220ac-110">Экспортируются как опубликованные, так и неопубликованные данные базы знаний.</span><span class="sxs-lookup"><span data-stu-id="220ac-110">Both published and unpublished data in a knowledge base is exported.</span></span>  
  
 <span data-ttu-id="220ac-111">Файл данных DQS, созданный в процессе экспорта, зашифровывается, его просмотр становится невозможным.</span><span class="sxs-lookup"><span data-stu-id="220ac-111">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="220ac-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="220ac-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="220ac-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="220ac-113">Prerequisites</span></span>  
 <span data-ttu-id="220ac-114">Чтобы экспортировать базу знаний в файл данных DQS, необходимо создать и открыть базу знаний.</span><span class="sxs-lookup"><span data-stu-id="220ac-114">To export a knowledge base to a .dqs data file, you must have created and opened a knowledge base.</span></span> <span data-ttu-id="220ac-115">Файл DQS не требуется, он будет создан в процессе экспорта.</span><span class="sxs-lookup"><span data-stu-id="220ac-115">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="220ac-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="220ac-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="220ac-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="220ac-117">Permissions</span></span>  
 <span data-ttu-id="220ac-118">Для экспорта базы знаний в файл данных DQS необходимо быть членом роли dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="220ac-118">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a knowledge base to a .dqs data file.</span></span>  
  
##  <a name="export-a-knowledge-base-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="220ac-119">Экспорт базы знаний в файл DQS</span><span class="sxs-lookup"><span data-stu-id="220ac-119">Export a knowledge base to a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="220ac-120">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="220ac-120">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="220ac-121">На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] откройте базу знаний в разделе управления доменами.</span><span class="sxs-lookup"><span data-stu-id="220ac-121">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="220ac-122">На странице «Управление доменами» (при любой выбранной вкладке) щелкните значок **Экспортировать данные базы знаний** над списком «Домен» и выберите **Экспортировать базу знаний**.</span><span class="sxs-lookup"><span data-stu-id="220ac-122">In the Domain Management page (with any tab selected), click the **Export Knowledge Base data** icon above the Domain list, and then click **Export Knowledge Base**.</span></span> <span data-ttu-id="220ac-123">Кроме того, вы можете щелкнуть правой кнопкой мыши список **Домен** , указать пункт **Экспорт**, а затем **Экспортировать базу знаний**.</span><span class="sxs-lookup"><span data-stu-id="220ac-123">Alternatively, you can also right-click in the **Domain** list, hover over **Export**, and then click **Export Knowledge Base**.</span></span>  
  
4.  <span data-ttu-id="220ac-124">В диалоговом окне **Экспорт в файл данных** перейдите в папку, где планируется сохранить файл, присвойте файлу имя или оставьте имя базы знаний, оставьте **Файлы данных DQS (\*.dqs)** в качестве **Типа файла** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="220ac-124">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the knowledge base name, keep **DQS Data Files (\*.dqs)** as the **Save as** type, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="220ac-125">В диалоговом окне **Экспортировать базу знаний** убедитесь, что в строке состояния сообщается о завершении экспорта.</span><span class="sxs-lookup"><span data-stu-id="220ac-125">In the **Export Knowledge Base** dialog box, verify that the status line indicates that the export completed.</span></span> <span data-ttu-id="220ac-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="220ac-126">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a><span data-ttu-id="220ac-127">Дальнейшие действия. После экспорта домена в файл DQS</span><span class="sxs-lookup"><span data-stu-id="220ac-127">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="220ac-128">После экспорта базы знаний в файл DQS можно импортировать базу знаний на тот же сервер [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (с новым именем) или на другой сервер [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="220ac-128">After you export a knowledge base to a .dqs file, you can import the knowledge base into the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (with a new name) or into a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
  
