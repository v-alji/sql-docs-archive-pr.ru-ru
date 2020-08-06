---
title: Управление распространением отчета | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], report distribution
- subscriptions [Reporting Services], e-mail
- subscriptions [Reporting Services], file share delivery
- file share delivery [Reporting Services]
- e-mail [Reporting Services]
- subscriptions [Reporting Services], security
- mail [Reporting Services]
ms.assetid: 8f15e2c6-a647-4b05-a519-1743b5d8654c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de8a27801ef89f10bf303cee17d1c2d0e1081c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654064"
---
# <a name="control-report-distribution"></a><span data-ttu-id="16b9e-102">Управление распространением отчета</span><span class="sxs-lookup"><span data-stu-id="16b9e-102">Control Report Distribution</span></span>
  <span data-ttu-id="16b9e-103">Сервер отчетов можно определенным образом настроить для уменьшения рисков, связанных с электронной почтой и распространением в общей папке.</span><span class="sxs-lookup"><span data-stu-id="16b9e-103">You can configure a report server to reduce the security risks associated with e-mail and file share distribution.</span></span>  
  
## <a name="securing-reports"></a><span data-ttu-id="16b9e-104">Обеспечение безопасности отчетов</span><span class="sxs-lookup"><span data-stu-id="16b9e-104">Securing Reports</span></span>  
 <span data-ttu-id="16b9e-105">Первым шагом в контроле распространения отчетов является обеспечение защиты отчета от несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="16b9e-105">The first step in controlling report distribution is to secure the report against unauthorized access.</span></span> <span data-ttu-id="16b9e-106">Чтобы отчет попал в подписку, в нем должен применяться хранимый набор учетных данных, одинаковых для разных доставок.</span><span class="sxs-lookup"><span data-stu-id="16b9e-106">To be used in a subscription, a report must use a stored set of credentials that do not vary for individual deliveries.</span></span> <span data-ttu-id="16b9e-107">Его может запустить и распространить любой пользователь, обладающий доступом к отчету на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="16b9e-107">Any user who can access the report on the report server can run it and possibly distribute it.</span></span> <span data-ttu-id="16b9e-108">Для предотвращения такой ситуации следует ограничить доступ и предоставить его только тем пользователям, которым он необходим.</span><span class="sxs-lookup"><span data-stu-id="16b9e-108">To prevent this from occurring, you must limit report access to only those users who require it.</span></span> <span data-ttu-id="16b9e-109">Дополнительные сведения см. в разделе [Защита отчетов и ресурсов](security/secure-reports-and-resources.md) и [защита папок](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="16b9e-109">For more information, see [Secure Reports and Resources](security/secure-reports-and-resources.md) and [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="16b9e-110">Отчеты повышенной конфиденциальности, использующие для получения доступа безопасность базы данных, не могут распространяться через подписку.</span><span class="sxs-lookup"><span data-stu-id="16b9e-110">Highly confidential reports that use database security to authorize access cannot be distributed by way of subscription.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="16b9e-111">Отчеты переносятся в виде файлов.</span><span class="sxs-lookup"><span data-stu-id="16b9e-111">Reports are transported as files.</span></span> <span data-ttu-id="16b9e-112">Риски и защитные меры, которые относятся к файлам, относятся и к отчетам, которые сохраняются на диске или высылаются в виде вложений.</span><span class="sxs-lookup"><span data-stu-id="16b9e-112">The risks and safeguards that apply to files apply equally to reports that are saved to disk or sent as attachments.</span></span> <span data-ttu-id="16b9e-113">Любой пользователь, который имеет доступ к файлам, может распространять или использовать их по собственному усмотрению.</span><span class="sxs-lookup"><span data-stu-id="16b9e-113">Any user who has access to a file can distribute or use the file at his or her discretion.</span></span>  
  
## <a name="controlling-e-mail-delivery"></a><span data-ttu-id="16b9e-114">Контроль доставки электронной почты</span><span class="sxs-lookup"><span data-stu-id="16b9e-114">Controlling E-Mail Delivery</span></span>  
 <span data-ttu-id="16b9e-115">Сервер отчетов можно настроить таким образом, чтобы распространение по электронной почте ограничивалось только определенными доменами.</span><span class="sxs-lookup"><span data-stu-id="16b9e-115">You can configure a report server to limit e-mail distribution to specific host domains.</span></span> <span data-ttu-id="16b9e-116">Например, можно запретить серверу отчетов доставку отчета всем доменам, кроме указанных в списке файла конфигурации RSReportServer.</span><span class="sxs-lookup"><span data-stu-id="16b9e-116">For example, you can prevent a report server from delivering a report to all domains except those listed in the RSReportServer configuration file.</span></span>  
  
 <span data-ttu-id="16b9e-117">Кроме того, можно настроить конфигурацию таким образом, чтобы поле **Кому** в подписке было скрыто.</span><span class="sxs-lookup"><span data-stu-id="16b9e-117">You can also set configuration settings to hide the **To** field in a subscription.</span></span> <span data-ttu-id="16b9e-118">В этом случае отчеты будут доставляться только пользователю, который определяет подписку.</span><span class="sxs-lookup"><span data-stu-id="16b9e-118">In this case, reports are delivered only to the user defining the subscription.</span></span> <span data-ttu-id="16b9e-119">Однако после отправки отчета пользователю можно явно запретить его пересылку.</span><span class="sxs-lookup"><span data-stu-id="16b9e-119">However, after a report is sent to a user, you cannot explicitly prevent it from being forwarded.</span></span>  
  
 <span data-ttu-id="16b9e-120">Наиболее эффективный путь управления распространением отчетов — настроить сервер отчетов так, чтобы он отправлял только URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="16b9e-120">The most effective way to control report distribution is to configure a report server to send only a report server URL.</span></span> <span data-ttu-id="16b9e-121">Сервер отчетов управляет доступом к отчетам с помощью проверки подлинности Windows и модели авторизации на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="16b9e-121">The report server uses Windows Authentication and a role-based authorization model to control access to a report.</span></span> <span data-ttu-id="16b9e-122">Если пользователь случайно получит электронное письмо с отчетом, не предназначенным для этого пользователя, то сервер не отобразит этот отчет.</span><span class="sxs-lookup"><span data-stu-id="16b9e-122">If a user accidentally receives through e-mail a report that he or she is not authorized to view, the report server will not display the report.</span></span>  
  
## <a name="controlling-file-share-delivery"></a><span data-ttu-id="16b9e-123">Управление доставкой в общую папку</span><span class="sxs-lookup"><span data-stu-id="16b9e-123">Controlling File Share Delivery</span></span>  
 <span data-ttu-id="16b9e-124">Доставка в общую папку используется для записи отчета в файл на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="16b9e-124">File share delivery is used to send a report to a file on a hard disk.</span></span> <span data-ttu-id="16b9e-125">После сохранения файла на диске этот файл перестает быть субъектом модели безопасности на основе ролей, с помощью которой сервер отчетов управляет доступом пользователей.</span><span class="sxs-lookup"><span data-stu-id="16b9e-125">After the file has been saved to disk, it is no longer subject to the role-based security model that the report server uses to control user access.</span></span> <span data-ttu-id="16b9e-126">Для защиты отчета, сохраненного на диске, можно поместить списки управления доступом (ACLs) в сам файл или в папку, в которой он находится.</span><span class="sxs-lookup"><span data-stu-id="16b9e-126">To secure a report that has been delivered to disk, you can place Access Control Lists (ACLs) on the file itself or on the folder that contains it.</span></span> <span data-ttu-id="16b9e-127">Кроме того, в зависимости от операционной системы, могут быть доступны другие параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="16b9e-127">Additional security options might be available, depending on your operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b9e-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="16b9e-128">See Also</span></span>  
 <span data-ttu-id="16b9e-129">[Настройка сервера отчетов для доставки электронной почты &#40;Configuration Manager SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="16b9e-129">[Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="16b9e-130">[Подписки и доставка (службы Reporting Services)](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="16b9e-130">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="16b9e-131">Создание и администрирование подписок для серверов отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="16b9e-131">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../../2014/reporting-services/create-manage-subscriptions-native-mode-report-servers.md)  
  
  
