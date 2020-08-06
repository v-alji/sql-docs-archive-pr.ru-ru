---
title: Создание роли пользователей (среда Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newrole.f1
ms.assetid: 9f76a235-0b58-479c-8e5b-50588091b71c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 78201c5ebedd0cdb7f8108b9e6effcaa7fbe87b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732334"
---
# <a name="new-user-role-management-studio"></a><span data-ttu-id="f60f2-102">Создание пользовательской роли (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f60f2-102">New User Role (Management Studio)</span></span>
  <span data-ttu-id="f60f2-103">На этой странице можно создать определение роли на уровне элемента.</span><span class="sxs-lookup"><span data-stu-id="f60f2-103">Use this page to create an item-level role definition.</span></span> <span data-ttu-id="f60f2-104">Определение роли на уровне элемента — это именованная коллекция задач, которые пользователь может выполнять в отношении папок, отчетов, моделей, ресурсов и общих источников данных.</span><span class="sxs-lookup"><span data-stu-id="f60f2-104">An item-level role definition is a named collection of tasks that enumerate the tasks a user can perform in relation to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="f60f2-105">Примером определения роли на уровне элемента является заранее определенная роль «Браузер», определяющая типы действий, которые могут понадобиться конечным пользователям отчетов для перемещения по папкам и просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="f60f2-105">An example of an item-level role definition is the predefined Browser role that identifies the kinds of actions a report end user might require for navigating folders and viewing reports.</span></span>  
  
 <span data-ttu-id="f60f2-106">Предполагается, что определений ролей должно быть немного.</span><span class="sxs-lookup"><span data-stu-id="f60f2-106">Role definitions are intended to be few in number.</span></span> <span data-ttu-id="f60f2-107">В большинстве организаций необходимо задать небольшое число определений ролей.</span><span class="sxs-lookup"><span data-stu-id="f60f2-107">Most organizations only require a few role definitions.</span></span> <span data-ttu-id="f60f2-108">Однако если заранее заданных определений ролей недостаточно, их можно изменять или создавать новые.</span><span class="sxs-lookup"><span data-stu-id="f60f2-108">However, if the predefined role definitions are insufficient, you can vary them or create new ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f60f2-109">Определения ролей используются только на сервере отчетов, работающем в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="f60f2-109">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="f60f2-110">Если сервер отчетов настроен для интеграции с SharePoint, эта страница недоступна.</span><span class="sxs-lookup"><span data-stu-id="f60f2-110">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f60f2-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="f60f2-111">Options</span></span>  
 <span data-ttu-id="f60f2-112">**Название**</span><span class="sxs-lookup"><span data-stu-id="f60f2-112">**Name**</span></span>  
 <span data-ttu-id="f60f2-113">Имя определения роли.</span><span class="sxs-lookup"><span data-stu-id="f60f2-113">Type the name of the role definition.</span></span> <span data-ttu-id="f60f2-114">Имя определения роли должно быть уникальным в пределах пространства имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="f60f2-114">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="f60f2-115">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="f60f2-115">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="f60f2-116">В него могут также входить пробелы и другие символы.</span><span class="sxs-lookup"><span data-stu-id="f60f2-116">It can also include spaces and some symbols.</span></span> <span data-ttu-id="f60f2-117">При задании имени нельзя использовать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="f60f2-117">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="f60f2-118">; ?</span><span class="sxs-lookup"><span data-stu-id="f60f2-118">; ?</span></span> <span data-ttu-id="f60f2-119">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="f60f2-119">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="f60f2-120">" /</span><span class="sxs-lookup"><span data-stu-id="f60f2-120">" /</span></span>  
  
 <span data-ttu-id="f60f2-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f60f2-121">**Description**</span></span>  
 <span data-ttu-id="f60f2-122">Описание назначения роли с указанием функций, поддерживаемых ею.</span><span class="sxs-lookup"><span data-stu-id="f60f2-122">Type a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="f60f2-123">**Задача**</span><span class="sxs-lookup"><span data-stu-id="f60f2-123">**Task**</span></span>  
 <span data-ttu-id="f60f2-124">Выберите задачи, которые могут выполняться с помощью этой роли.</span><span class="sxs-lookup"><span data-stu-id="f60f2-124">Select the tasks that can be performed through this role.</span></span> <span data-ttu-id="f60f2-125">Нельзя создавать новые задачи или изменять существующие, если они поддерживаются службами [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f60f2-125">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f60f2-126">В определении роли на уровне элемента могут указываться только задачи уровня элемента.</span><span class="sxs-lookup"><span data-stu-id="f60f2-126">Only item-level tasks can be used in an item-level role definition.</span></span>  
  
 <span data-ttu-id="f60f2-127">**Описание задачи**</span><span class="sxs-lookup"><span data-stu-id="f60f2-127">**Task Description**</span></span>  
 <span data-ttu-id="f60f2-128">Описание задачи с указанием поддерживаемых ею операций и разрешений.</span><span class="sxs-lookup"><span data-stu-id="f60f2-128">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60f2-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="f60f2-129">See Also</span></span>  
 <span data-ttu-id="f60f2-130">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f60f2-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="f60f2-131">Определение ролей</span><span class="sxs-lookup"><span data-stu-id="f60f2-131">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
