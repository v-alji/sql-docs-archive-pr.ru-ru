---
title: Сохранение отчета в библиотеке SharePoint (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49878a0d7115a11e804382cb5139aa0ec7b3d254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663994"
---
# <a name="save-a-report-to-a-sharepoint-library-report-builder"></a><span data-ttu-id="e0895-102">Сохранение отчета в библиотеке SharePoint (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="e0895-102">Save a Report to a SharePoint Library (Report Builder)</span></span>
  <span data-ttu-id="e0895-103">Чтобы сохранить отчет на сервере отчетов, настроенном для режима интеграции с SharePoint, необходимо перейти на сервер SharePoint и установить соединение с сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="e0895-103">To save a report to a report server configured for SharePoint integration, you must browse to the SharePoint server and establish a connection to the report server.</span></span> <span data-ttu-id="e0895-104">В определении отчета все ссылки на элементы, связанные с отчетом, должны использовать переменные, относящиеся к серверу отчетов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0895-104">In the report definition, all references to items related to the report must use values that are specific to a SharePoint report server.</span></span> <span data-ttu-id="e0895-105">Связанные элементы включают вложенные отчеты, детализированные отчеты и ресурсы (например, изображения, хранящиеся в Интернете).</span><span class="sxs-lookup"><span data-stu-id="e0895-105">Related items include subreports, drillthrough reports, and resources such as Web-based images.</span></span> <span data-ttu-id="e0895-106">Дополнительные сведения см. в разделе [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e0895-106">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="e0895-107">Необходимо обладать разрешением **Член** или **Владелец** на сайте SharePoint для задания свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="e0895-107">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span>  
  
### <a name="to-save-a-report-to-a-sharepoint-site"></a><span data-ttu-id="e0895-108">Сохранение отчета на сайте SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0895-108">To save a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="e0895-109">В построителе отчетов нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e0895-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="e0895-110">**Save As** _\<Report Item>_ Откроется диалоговое окно Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="e0895-110">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0895-111">Во время повторного сохранения отчет автоматически сохраняется в предыдущем расположении.</span><span class="sxs-lookup"><span data-stu-id="e0895-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="e0895-112">Чтобы изменить расположение, используйте параметр **Сохранить как** .</span><span class="sxs-lookup"><span data-stu-id="e0895-112">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="e0895-113">Также можно щелкнуть ссылку **Последние сайты и серверы** , чтобы вывести список недавно использовавшихся серверов отчета и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0895-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="e0895-114">Выберите сайт SharePoint и щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e0895-114">Browse to the SharePoint site, and then click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0895-115">Если не сохранять измененный отчет в течение более 10 часов, он отключается от сервера без сохранения.</span><span class="sxs-lookup"><span data-stu-id="e0895-115">If you leave a changed report for more than 10 hours without saving it, it is disconnected from the server without being saved.</span></span> <span data-ttu-id="e0895-116">Если это произойдет, в правой нижней строке состояния щелкните **Отключение**, затем щелкните **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="e0895-116">If that happens, in the lower-right status bar, click **Disconnect**, and then click **Connect**.</span></span> <span data-ttu-id="e0895-117">Последний сервер будет в списке доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="e0895-117">The most recent server will be in the list of available servers.</span></span> <span data-ttu-id="e0895-118">Выберите его, и отчет вновь подключится.</span><span class="sxs-lookup"><span data-stu-id="e0895-118">Select it and the report will reconnect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0895-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0895-119">See Also</span></span>  
 [<span data-ttu-id="e0895-120">Поиск, просмотр отчетов и управление ими (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="e0895-120">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
