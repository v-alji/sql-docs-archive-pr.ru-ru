---
title: Роли и разрешения (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- access controls [Reporting Services]
- permissions [Reporting Services], about permissions
- security [Reporting Services], identity and access control
- authentication [Reporting Services]
- permissions [Reporting Services]
- security [Reporting Services], role-based
- identity [Reporting Services]
ms.assetid: eea655fe-43ed-418d-8233-b288a8f4daa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e6098a51afde04164e3ef0dfa5e5297457b4440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664697"
---
# <a name="roles-and-permissions-reporting-services"></a><span data-ttu-id="54436-102">Роли и разрешения (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="54436-102">Roles and Permissions (Reporting Services)</span></span>
  <span data-ttu-id="54436-103">В службах Reporting Services реализована подсистема проверки подлинности и основанная на ролях модель авторизации.</span><span class="sxs-lookup"><span data-stu-id="54436-103">Reporting Services provides an authentication subsystem and role-based authorization model.</span></span> <span data-ttu-id="54436-104">Модели авторизации и проверки подлинности зависят от режима работы сервера отчетов — собственный режим или режим SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54436-104">Authentication and authorization models vary depending on whether the report server runs in native mode or SharePoint mode.</span></span> <span data-ttu-id="54436-105">Если сервер отчетов является частью развертывания SharePoint, доступ к серверу отчетов определяется разрешениями SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54436-105">If the report server is part of a SharePoint deployment, SharePoint permissions determine who has access to the report server.</span></span>  
  
## <a name="identity-and-access-control-for-native-mode"></a><span data-ttu-id="54436-106">Управление доступом и удостоверениями в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="54436-106">Identity and Access Control for Native Mode</span></span>  
 <span data-ttu-id="54436-107">Применяемые по умолчанию средства проверки подлинности основаны на средствах проверки подлинности и встроенной безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="54436-107">Default authentication is based on Windows Authentication and integrated security.</span></span> <span data-ttu-id="54436-108">Настройки проверки подлинности можно изменить так, чтобы сервер отчетов отвечал на различные запросы по проверке подлинности, или даже заменить применяемые по умолчанию средства безопасности нестандартным модулем проверки подлинности, предоставленным пользователем.</span><span class="sxs-lookup"><span data-stu-id="54436-108">You can change the authentication settings to allow the report server to respond to different authentication requests, or even replace the default security features with a custom authentication extension that you provide.</span></span>  
  
 <span data-ttu-id="54436-109">Авторизация базируется на ролях, назначаемых участнику.</span><span class="sxs-lookup"><span data-stu-id="54436-109">Authorization is based on roles that you assign to a principle.</span></span> <span data-ttu-id="54436-110">Каждая роль состоит из набора взаимосвязанных задач, которые, в свою очередь, состоят из взаимосвязанных операций.</span><span class="sxs-lookup"><span data-stu-id="54436-110">Each role consists of a set of related tasks, which are in turn composed of related operations.</span></span> <span data-ttu-id="54436-111">Так, задание **Управление отчетами** предполагает предоставление доступа к следующим операциям сервера отчетов: просмотр отчетов, добавление отчета, обновление отчета, удаление отчета, планирование отчета и обновление свойств отчета.</span><span class="sxs-lookup"><span data-stu-id="54436-111">For example, the **Manage reports** task grants access to the following report server operations: view reports, add report, update report, delete report, schedule report, and update report properties.</span></span>  
  
## <a name="identity-and-access-control-for-sharepoint-mode"></a><span data-ttu-id="54436-112">Управление удостоверениями и доступом в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="54436-112">Identity and Access Control for SharePoint Mode</span></span>  
 <span data-ttu-id="54436-113">В режиме интеграции с SharePoint проверка подлинности и авторизация осуществляется на сайте SharePoint до того, как запросы попадают на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="54436-113">In SharePoint integrated mode, authentication and authorization are handled on the SharePoint site, before requests reach the report server.</span></span> <span data-ttu-id="54436-114">В зависимости от конфигурации средств проверки подлинности запросы с сайта SharePoint включают токен безопасности или имя доверенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="54436-114">Depending on how you configure authentication, requests from a SharePoint site include a security token or a trusted user name.</span></span> <span data-ttu-id="54436-115">Разрешения, предоставляемые пользователям и группам пользователей SharePoint, включают авторизованный доступ к элементам сервера отчетов, размещенным в библиотеках SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54436-115">Permissions that you set for SharePoint users and groups authorize access to report server items that are placed in SharePoint libraries.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54436-116">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="54436-116">In This Section</span></span>  
 [<span data-ttu-id="54436-117">Предоставление разрешений на сервер отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="54436-117">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
 <span data-ttu-id="54436-118">Описывает модель авторизации, основанную на ролях, которая предоставляет доступ к содержимому и операциям сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="54436-118">Describes the role-based authorization model that provides access to content and operations.</span></span>  
  
 [<span data-ttu-id="54436-119">Предоставление разрешений для элементов сервера отчетов на сайте SharePoint</span><span class="sxs-lookup"><span data-stu-id="54436-119">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
 <span data-ttu-id="54436-120">Объясняет, как использовать для управления доступом к серверу отчетов группы SharePoint, уровни разрешений и разрешения.</span><span class="sxs-lookup"><span data-stu-id="54436-120">Explains how SharePoint groups, permission levels, and permissions are used to control access to a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54436-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="54436-121">See Also</span></span>  
 <span data-ttu-id="54436-122">[Проверка подлинности с использованием сервера отчетов](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="54436-122">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 [<span data-ttu-id="54436-123">Предоставление разрешений на сервер отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="54436-123">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
