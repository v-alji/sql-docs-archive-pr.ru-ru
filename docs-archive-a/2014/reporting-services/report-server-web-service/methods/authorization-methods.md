---
title: Методы авторизации | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], reports
- authorization [Reporting Services]
- reports [Reporting Services], security
- tasks [Reporting Services]
- roles [Reporting Services], methods
ms.assetid: 45e9cf2c-facf-4801-9482-c855403f42a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b04a21b5075e939a4732e2f8ec219e169f4ba440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736042"
---
# <a name="authorization-methods"></a><span data-ttu-id="a779a-102">Методы авторизации</span><span class="sxs-lookup"><span data-stu-id="a779a-102">Authorization Methods</span></span>
  <span data-ttu-id="a779a-103">С помощью этих методов можно управлять задачами, ролями и политиками на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="a779a-103">You can use these methods to manage tasks, roles, and policies on the report server.</span></span>  
  
|<span data-ttu-id="a779a-104">Метод</span><span class="sxs-lookup"><span data-stu-id="a779a-104">Method</span></span>|<span data-ttu-id="a779a-105">Действие</span><span class="sxs-lookup"><span data-stu-id="a779a-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateRole%2A>|<span data-ttu-id="a779a-106">Добавляет новую роль в базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a779a-106">Adds a new role to the report server database.</span></span> <span data-ttu-id="a779a-107">Этот метод применим только в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a779a-107">This method =applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteRole%2A>|<span data-ttu-id="a779a-108">Удаляет роль из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a779a-108">Deletes a role from the report server database.</span></span> <span data-ttu-id="a779a-109">Этот метод применим только в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a779a-109">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPermissions%2A>|<span data-ttu-id="a779a-110">Возвращает разрешения пользователя, связанные с данным элементом в базе данных сервера отчетов или библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a779a-110">Returns the user permissions that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPolicies%2A>|<span data-ttu-id="a779a-111">Возвращает политики, связанные с данным элементом в базе данных сервера отчетов или библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a779a-111">Returns the policies that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetRoleProperties%2A>|<span data-ttu-id="a779a-112">Возвращает свойства метаданных роли и набор связанных задач.</span><span class="sxs-lookup"><span data-stu-id="a779a-112">Returns role metadata properties and a collection of associated tasks.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPermissions%2A>|<span data-ttu-id="a779a-113">Возвращает системные разрешения пользователя.</span><span class="sxs-lookup"><span data-stu-id="a779a-113">Returns the user's system permissions.</span></span> <span data-ttu-id="a779a-114">Этот метод применим только в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a779a-114">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPolicies%2A>|<span data-ttu-id="a779a-115">Возвращает системные политики, в том числе группы и роли, с которыми они связаны.</span><span class="sxs-lookup"><span data-stu-id="a779a-115">Returns the system policies, including groups and roles with which they are associated.</span></span> <span data-ttu-id="a779a-116">Этот метод применим только в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a779a-116">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritParentSecurity%2A>|<span data-ttu-id="a779a-117">Удаляет политики, связанные с соответствующим элементом в базе данных сервера отчетов, и задает для элемента политики безопасности его родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="a779a-117">Deletes the policies that are associated with a particular item in the report server database and sets the security policies for the item to those of its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>|<span data-ttu-id="a779a-118">Возвращает логическое значение, которое определяет, необходим ли протокол SSL (Secure Socket Layer) для использования конечной точки <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="a779a-118">Returns a Boolean value that indicates whether the Secure Socket Layer (SSL) protocol is required to use the <xref:ReportService2010> end point.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListRoles%2A>|<span data-ttu-id="a779a-119">Возвращает имена и описания ролей, управляемые сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="a779a-119">Returns the names and descriptions of roles that are managed by the report server.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>|<span data-ttu-id="a779a-120">Возвращает список методов SOAP в конечной точке <xref:ReportExecution2005>, требующих при вызове безопасное соединение.</span><span class="sxs-lookup"><span data-stu-id="a779a-120">Returns a list of Simple Object Access Protocol (SOAP) methods in the <xref:ReportExecution2005> endpoint that require a secure connection when invoked.</span></span> <span data-ttu-id="a779a-121">Возвращаемые методы определяются с помощью параметра `SecureConnectionLevel` сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a779a-121">The `SecureConnectionLevel` setting of the report server is used to determine which methods are returned.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListTasks%2A>|<span data-ttu-id="a779a-122">Возвращает задания, управляемые сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="a779a-122">Returns the tasks that are managed by the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetPolicies%2A>|<span data-ttu-id="a779a-123">Задает политики, связанные с указанным элементом.</span><span class="sxs-lookup"><span data-stu-id="a779a-123">Sets the policies that are associated with a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetRoleProperties%2A>|<span data-ttu-id="a779a-124">Задает свойства метаданных роли и связывает набор задач с этой ролью.</span><span class="sxs-lookup"><span data-stu-id="a779a-124">Sets role metadata properties and associates a set of tasks with a role.</span></span> <span data-ttu-id="a779a-125">Этот метод применим только в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a779a-125">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>|<span data-ttu-id="a779a-126">Задает системную политику, которая определяет группы и связанные с ними роли.</span><span class="sxs-lookup"><span data-stu-id="a779a-126">Sets the system policy that defines groups and their associated roles.</span></span> <span data-ttu-id="a779a-127">Этот метод применим только в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="a779a-127">This method applies to native mode only.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a779a-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="a779a-128">See Also</span></span>  
 <span data-ttu-id="a779a-129">[Создание приложений с помощью веб-службы и .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="a779a-129">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="a779a-130">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="a779a-130">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="a779a-131">[Методы веб-службы сервера отчетов](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="a779a-131">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="a779a-132">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a779a-132">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
