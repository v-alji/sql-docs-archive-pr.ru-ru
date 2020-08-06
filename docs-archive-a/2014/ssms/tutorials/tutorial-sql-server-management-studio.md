---
title: 'Руководство: SQL Server Management Studio | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.tutorialstart.ssms.f1
helpviewer_keywords:
- projects [SQL Server Management Studio], tutorials
- templates [SQL Server], SQL Server Management Studio
- source controls [SQL Server Management Studio], tutorials
- Help [SQL Server], SQL Server Management Studio
- tutorials [SQL Server Management Studio]
- Transact-SQL tutorials
- solutions [SQL Server Management Studio], tutorials
- SQL Server Management Studio [SQL Server], tutorials
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d2bade70-07cf-4d94-b5d2-88aecb538ed1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8206fea828d6169975dc1d026a22e18e682f71e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668030"
---
# <a name="tutorial-sql-server-management-studio"></a><span data-ttu-id="460bf-102">Руководство: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="460bf-102">Tutorial: SQL Server Management Studio</span></span>
  <span data-ttu-id="460bf-103">В учебнике по среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] описывается интегрированная среда для управления инфраструктурой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="460bf-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutorial introduces you to the integrated environment for managing your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="460bf-104">представляет собой графический интерфейс для настройки экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], наблюдения за ними и управления ими.</span><span class="sxs-lookup"><span data-stu-id="460bf-104">presents a graphical interface for configuring, monitoring, and administering instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="460bf-105">Такая среда также позволяет развертывать, наблюдать и обновлять компоненты уровня данных, используемых приложениями, например базами и хранилищами данных.</span><span class="sxs-lookup"><span data-stu-id="460bf-105">It also allows you to deploy, monitor, and upgrade the data-tier components used by your applications, such as databases and data warehouses.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="460bf-106">также предоставляет редакторы [!INCLUDE[tsql](../../includes/tsql-md.md)], языка многомерных выражений, расширений интеллектуального анализа данных и XML для изменения и отладки скриптов.</span><span class="sxs-lookup"><span data-stu-id="460bf-106">also provides [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML language editors for editing and debugging scripts.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="460bf-107">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="460bf-107">What You Will Learn</span></span>  
 <span data-ttu-id="460bf-108">В этом учебнике разъясняется представление информации в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , а также способы использования ее возможностей.</span><span class="sxs-lookup"><span data-stu-id="460bf-108">This tutorial will help you understand the presentation of information in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to take advantage of the features.</span></span> <span data-ttu-id="460bf-109">Обратите внимание, что этот учебник относится к полной установке [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], которая входит в состав всех версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], кроме [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="460bf-109">Note that this tutorial applies to the complete installation of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] that is included with all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="460bf-110">Функциональные возможности для базовой установки среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и установок среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], которые поставляются с [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], немного отличаются от представленных в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="460bf-110">Functionality for basic installations of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] installations that ship with [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] is slightly different than what is presented in this tutorial.</span></span>  
  
 <span data-ttu-id="460bf-111">Лучший способ ознакомиться с возможностями среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] — самостоятельно выполнить практические задания.</span><span class="sxs-lookup"><span data-stu-id="460bf-111">The best way to get acquainted with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is through hands-on practice.</span></span> <span data-ttu-id="460bf-112">В этом учебнике объясняется, как управлять компонентами среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и найти возможности, которые будут использоваться регулярно.</span><span class="sxs-lookup"><span data-stu-id="460bf-112">This tutorial will teach you how to manage the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to find the features that you use regularly.</span></span>  
  
 <span data-ttu-id="460bf-113">Учебник разделен на три занятия.</span><span class="sxs-lookup"><span data-stu-id="460bf-113">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="460bf-114">Занятие 1. Основные возможности перемещения в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="460bf-114">Lesson 1: Basic Navigation in SQL Server Management Studio</span></span>](lesson-1-basic-navigation-in-sql-server-management-studio.md)  
 <span data-ttu-id="460bf-115">На этом занятии рассматривается, как использовать компоненты среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], как перенастроить макет среды и вернуться к макету, заданному по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="460bf-115">In this lesson you will learn how to use the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], how to reconfigure the environment layout, and how to restore the default layout.</span></span>  
  
 [<span data-ttu-id="460bf-116">Занятие 2. Создание инструкций на языке Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="460bf-116">Lesson 2: Writing Transact-SQL</span></span>](lesson-2-writing-transact-sql.md)  
 <span data-ttu-id="460bf-117">На этом занятии рассматривается, как открывать редактор запросов, управлять кодом и использовать другие новые функции редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="460bf-117">In this lesson, you will learn how to open Query Editor, how to manage code, and how to use the other new features of Query Editor.</span></span>  
  
 [<span data-ttu-id="460bf-118">Урок 3. Работа с шаблонами, решениями и проектами скриптов</span><span class="sxs-lookup"><span data-stu-id="460bf-118">Lesson 3: Working with Templates, Solutions, and Script Projects</span></span>](lesson-3-working-with-templates-solutions-and-script-projects.md)  
 <span data-ttu-id="460bf-119">На этом занятии мы рассмотрим, как использовать шаблоны и организовывать скрипты в решения и проекты.</span><span class="sxs-lookup"><span data-stu-id="460bf-119">In this lesson you will learn how to use templates, and organize scripts into solutions and projects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="460bf-120">Требования</span><span class="sxs-lookup"><span data-stu-id="460bf-120">Requirements</span></span>  
 <span data-ttu-id="460bf-121">Этот учебник предназначен для опытных администраторов и разработчиков баз данных, незнакомых с языком [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], но знакомых с основными понятиями баз данных и языком [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="460bf-121">This tutorial is intended for experienced database administrators and database developers who are not familiar with [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], but who are who are familiar with database concepts and the [!INCLUDE[tsql](../../includes/tsql-md.md)] language.</span></span>  
  
 <span data-ttu-id="460bf-122">Для работы с этим учебником в системе должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="460bf-122">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="460bf-123">или более поздняя версия с образцами баз данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="460bf-123">or a later version with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample databases.</span></span> <span data-ttu-id="460bf-124">В целях повышения безопасности образцы баз данных по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="460bf-124">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="460bf-125">Дополнительные сведения об установке образцов баз данных см. в статье [Установка образцов SQL Server и образцов баз данных](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="460bf-125">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
-   <span data-ttu-id="460bf-126">Internet Explorer 9.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="460bf-126">Internet Explorer 9.0 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460bf-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="460bf-127">See Also</span></span>  
 [<span data-ttu-id="460bf-128">Учебники по компоненту ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="460bf-128">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
