---
title: Обозреватель шаблонов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.wb.templates.f1
- sql12.swb.templates.explorer.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7ee1e6261c759580df3a836f9cc4b500a77ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665728"
---
# <a name="template-explorer"></a><span data-ttu-id="d5628-102">Template Explorer</span><span class="sxs-lookup"><span data-stu-id="d5628-102">Template Explorer</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d5628-103">предоставляет целый ряд шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d5628-103">provides a variety of templates.</span></span> <span data-ttu-id="d5628-104">Шаблоны — это файлы со стандартным текстом, содержащие скрипты SQL, которые помогают создавать объекты в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d5628-104">Templates are boilerplate files containing SQL scripts that help you create objects in a database.</span></span> <span data-ttu-id="d5628-105">При первом открытии обозревателя шаблонов копия шаблонов помещается в папку пользователя в C:\Users в разделе AppData\Roaming\Microsoft\SQL Server Management Studio\120\templates»</span><span class="sxs-lookup"><span data-stu-id="d5628-105">The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span></span>  
  
 <span data-ttu-id="d5628-106">Предусмотрена возможность просматривать доступные шаблоны в обозревателе шаблонов, затем открывать шаблон для включения его кода в окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="d5628-106">You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window.</span></span> <span data-ttu-id="d5628-107">Можно также создавать пользовательские шаблоны.</span><span class="sxs-lookup"><span data-stu-id="d5628-107">You can also create custom templates.</span></span>  
  
## <a name="benefits-of-templates"></a><span data-ttu-id="d5628-108">Преимущества шаблонов</span><span class="sxs-lookup"><span data-stu-id="d5628-108">Benefits of Templates</span></span>  
 <span data-ttu-id="d5628-109">Шаблоны доступны для решений, проектов и различных типов редакторов кода.</span><span class="sxs-lookup"><span data-stu-id="d5628-109">Templates are available for solutions, projects, and various types of code editors.</span></span> <span data-ttu-id="d5628-110">Имеются шаблоны создания таких объектов, как базы данных, таблицы, представления, индексы, хранимые процедуры, триггеры, статистические данные и функции.</span><span class="sxs-lookup"><span data-stu-id="d5628-110">Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions.</span></span> <span data-ttu-id="d5628-111">Кроме того, есть такие шаблоны, которые помогают управлять сервером путем создания расширенных свойств, связанных серверов, имен входа, ролей, пользователей и шаблонов для [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5628-111">In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d5628-112">Шаблоны, поставляемые со среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , содержат параметры для облегчения настройки кода.</span><span class="sxs-lookup"><span data-stu-id="d5628-112">The template scripts provided with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contain parameters to help you customize the code.</span></span> <span data-ttu-id="d5628-113">После открытия шаблона используйте диалоговое окно **Замена параметров шаблона** для вставки значений в скрипт.</span><span class="sxs-lookup"><span data-stu-id="d5628-113">When you open a template, Use the **Replace Template Parameters** dialog box to insert values into the script.</span></span>  
  
 <span data-ttu-id="d5628-114">Для часто выполняемых задач можно создать пользовательские шаблоны.</span><span class="sxs-lookup"><span data-stu-id="d5628-114">Create custom templates for tasks you perform frequently.</span></span> <span data-ttu-id="d5628-115">Организуйте свои скрипты в существующих папках или создайте новую структуру файлов.</span><span class="sxs-lookup"><span data-stu-id="d5628-115">Organize your custom scripts into the existing folders or create a new folder structure.</span></span>  
  
 <span data-ttu-id="d5628-116">Кроме того, редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] позволяет вставить фрагменты кода в скрипт, для чего достаточно щелкнуть правой кнопкой мыши в нужном месте скрипта.</span><span class="sxs-lookup"><span data-stu-id="d5628-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d5628-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d5628-117">Related Tasks</span></span>  
 <span data-ttu-id="d5628-118">Используйте следующие разделы, чтобы приступить к работе с шаблонами</span><span class="sxs-lookup"><span data-stu-id="d5628-118">Use the following topics to get started with templates</span></span>  
  
|<span data-ttu-id="d5628-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d5628-119">**Description**</span></span>|<span data-ttu-id="d5628-120">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="d5628-120">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="d5628-121">Описано, как включить код из шаблона в окно редактора кода.</span><span class="sxs-lookup"><span data-stu-id="d5628-121">Describes how to incorporate the code from a template into a code editor window.</span></span>|[<span data-ttu-id="d5628-122">Открытие шаблона</span><span class="sxs-lookup"><span data-stu-id="d5628-122">Open a Template</span></span>](open-a-template.md)|  
|<span data-ttu-id="d5628-123">Описано, как заменить значения параметров шаблона после открытия шаблона в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="d5628-123">Describes how to replace template parameter values after opening a template in a code editor.</span></span>|[<span data-ttu-id="d5628-124">Замена параметров шаблона</span><span class="sxs-lookup"><span data-stu-id="d5628-124">Replace Template Parameters</span></span>](replace-template-parameters.md)|  
  
  
