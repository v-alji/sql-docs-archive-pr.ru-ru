---
title: Создание системной роли (среда Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732337"
---
# <a name="new-system-role-management-studio"></a><span data-ttu-id="bf754-102">Создание системной роли (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bf754-102">New System Role (Management Studio)</span></span>
  <span data-ttu-id="bf754-103">Используйте эту страницу, чтобы создать определение роли на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="bf754-103">Use this page to create a system-level role definition.</span></span> <span data-ttu-id="bf754-104">Определение системной роли указывает набор задач на системном уровне, применимых к серверу отчетов в целом.</span><span class="sxs-lookup"><span data-stu-id="bf754-104">A system role definition specifies a set of system-level tasks that apply to a report server as whole.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf754-105">Определения ролей используются только на сервере отчетов, работающем в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="bf754-105">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="bf754-106">Если сервер отчетов настроен для интеграции с SharePoint, эта страница недоступна.</span><span class="sxs-lookup"><span data-stu-id="bf754-106">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf754-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf754-107">Options</span></span>  
 <span data-ttu-id="bf754-108">**Название**</span><span class="sxs-lookup"><span data-stu-id="bf754-108">**Name**</span></span>  
 <span data-ttu-id="bf754-109">Имя определения роли.</span><span class="sxs-lookup"><span data-stu-id="bf754-109">Type the name of the role definition.</span></span> <span data-ttu-id="bf754-110">Имя определения роли должно быть уникальным в пределах пространства имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="bf754-110">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="bf754-111">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="bf754-111">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="bf754-112">В него могут также входить пробелы и другие символы.</span><span class="sxs-lookup"><span data-stu-id="bf754-112">It can also include spaces and some symbols.</span></span> <span data-ttu-id="bf754-113">При задании имени нельзя использовать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="bf754-113">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="bf754-114">; ?</span><span class="sxs-lookup"><span data-stu-id="bf754-114">; ?</span></span> <span data-ttu-id="bf754-115">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="bf754-115">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="bf754-116">" /</span><span class="sxs-lookup"><span data-stu-id="bf754-116">" /</span></span>  
  
 <span data-ttu-id="bf754-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bf754-117">**Description**</span></span>  
 <span data-ttu-id="bf754-118">Введите описание, объясняющее, как использовать роль, и перечисляющее функции, которые поддерживаются ролью.</span><span class="sxs-lookup"><span data-stu-id="bf754-118">Provide a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="bf754-119">**Задача**</span><span class="sxs-lookup"><span data-stu-id="bf754-119">**Task**</span></span>  
 <span data-ttu-id="bf754-120">Выберите задачи на уровне системы, которые могут выполняться посредством этой роли.</span><span class="sxs-lookup"><span data-stu-id="bf754-120">Select the system-level tasks that can be performed through this role.</span></span> <span data-ttu-id="bf754-121">Нельзя создавать новые задачи или изменять существующие, если они поддерживаются службами [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf754-121">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="bf754-122">Нельзя выбирать задачи на уровне элемента для определения системной роли.</span><span class="sxs-lookup"><span data-stu-id="bf754-122">You cannot choose item-level tasks for a system role definition.</span></span>  
  
 <span data-ttu-id="bf754-123">**Описание задачи**</span><span class="sxs-lookup"><span data-stu-id="bf754-123">**Task Description**</span></span>  
 <span data-ttu-id="bf754-124">Описание задачи с указанием поддерживаемых ею операций и разрешений.</span><span class="sxs-lookup"><span data-stu-id="bf754-124">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf754-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf754-125">See Also</span></span>  
 <span data-ttu-id="bf754-126">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bf754-126">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="bf754-127">Определение ролей</span><span class="sxs-lookup"><span data-stu-id="bf754-127">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
