---
title: Справочник по пользовательскому интерфейсу диалогового окна "роли пакетов" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.packageroles.f1
helpviewer_keywords:
- Package Roles dialog box
ms.assetid: 63f13416-c0aa-4480-a336-ef1e6e31a860
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 389b29ddee5674af7ecd106f4f82d61bbb3a0f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734346"
---
# <a name="package-roles-dialog-box-ui-reference"></a><span data-ttu-id="d5e2a-102">Диалоговое окно «Роли пакета» справочника по пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="d5e2a-102">Package Roles Dialog Box UI Reference</span></span>
  <span data-ttu-id="d5e2a-103">Используйте диалоговое окно **Роли пакетов** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], чтобы указать роли на уровне базы данных, которые обладают правами на считывание пакета, и роли на уровне базы данных, которые имеют права на запись пакета.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-103">Use the **Package Roles** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to specify the database-level roles that have read access to the package and the database-level roles that have write access to the package.</span></span> <span data-ttu-id="d5e2a-104">Роли на уровне баз данных определяют права только для пакетов, хранящихся в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb**.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-104">Database-level roles apply only to packages that are stored in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span></span>  
  
 <span data-ttu-id="d5e2a-105">Дополнительные сведения о ролях уровня базы данных [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и их разрешениях см. в разделе [Роли служб Integration Services (службы SSIS)](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="d5e2a-105">To learn more about the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] database-level roles and their permissions, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>  
  
 <span data-ttu-id="d5e2a-106">Роли, список которых приведен в диалоговом окне, являются существующими в данный момент ролями системной базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="d5e2a-106">The roles listed in the dialog box are the current database roles of the **msdb** system database.</span></span> <span data-ttu-id="d5e2a-107">Если роли не выбраны, то применяются роли служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-107">If no roles are selected, the default [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] roles apply.</span></span> <span data-ttu-id="d5e2a-108">По умолчанию в роль чтения включаются **db_ssisadmin**, **db_ssisoperator**и пользователь, создавший пакет.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-108">By default, the reader role includes **db_ssisadmin**, **db_ssisoperator**, and the user who created the package.</span></span> <span data-ttu-id="d5e2a-109">Пользователь, который является членом одной из этих ролей или является создателем пакета, может перечислять, просматривать, выполнять экспорт и запускать пакеты.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-109">A user who is a member of one of these roles or created the packages can enumerate, view, export, and run packages.</span></span> <span data-ttu-id="d5e2a-110">По умолчанию в роль записи включается роль **db_ssisadmin** и пользователь, который создал пакет.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-110">By default, the writer role includes **db_ssisadmin** and the user who created the package.</span></span> <span data-ttu-id="d5e2a-111">Пользователь, который является членом этой роли, может выполнять импорт, удалять и изменять пакеты.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-111">A user who is a member of this role and the user who created the packages can import, delete, and change packages.</span></span>  
  
 <span data-ttu-id="d5e2a-112">В столбце **ownersid** таблицы **sysssispackages** указан уникальный идентификатор безопасности пользователя, создавшего пакет.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-112">The **ownersid** column in the **sysssispackages** table lists the unique security identifier of the user who created the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5e2a-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="d5e2a-113">Options</span></span>  
 <span data-ttu-id="d5e2a-114">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="d5e2a-114">**Package Name**</span></span>  
 <span data-ttu-id="d5e2a-115">Укажите имя пакета.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-115">Specify the name of the package.</span></span>  
  
 <span data-ttu-id="d5e2a-116">**Роль читателя**</span><span class="sxs-lookup"><span data-stu-id="d5e2a-116">**Reader Role**</span></span>  
 <span data-ttu-id="d5e2a-117">Выберите роль из списка.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-117">Select a role in the list.</span></span>  
  
 <span data-ttu-id="d5e2a-118">**Роль записи**</span><span class="sxs-lookup"><span data-stu-id="d5e2a-118">**Writer Role**</span></span>  
 <span data-ttu-id="d5e2a-119">Выберите роль из списка.</span><span class="sxs-lookup"><span data-stu-id="d5e2a-119">Select a role in the list</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e2a-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5e2a-120">See Also</span></span>  
 <span data-ttu-id="d5e2a-121">[Роли уровня базы данных](../relational-databases/security/authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="d5e2a-121">[Database-Level Roles](../relational-databases/security/authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="d5e2a-122">Общие сведения о безопасности (службы Integration Services)</span><span class="sxs-lookup"><span data-stu-id="d5e2a-122">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
