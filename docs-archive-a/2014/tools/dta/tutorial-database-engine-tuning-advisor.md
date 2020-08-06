---
title: Учебник. Помощник по настройке ядра СУБД | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], tutorials
- tutorials [Database Engine Tuning Advisor]
ms.assetid: 3b54cbbe-d8c6-424d-92f1-aa58179f4da8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 68e026cb28b875b834f20c906232285ede8e217b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655504"
---
# <a name="tutorial-database-engine-tuning-advisor"></a><span data-ttu-id="40e15-102">Руководство по Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="40e15-102">Tutorial: Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="40e15-103">Добро пожаловать в учебник по помощнику по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="40e15-103">Welcome to the Database Engine Tuning Advisor tutorial.</span></span> <span data-ttu-id="40e15-104">Помощник по настройке ядра СУБД выявляет, каким образом запросы обрабатываются в указанных пользователем базах данных, а затем выдает рекомендации по повышению скорости обработки запросов путем изменения структур базы данных, таких как индексы, индексированные представления и секции.</span><span class="sxs-lookup"><span data-stu-id="40e15-104">Database Engine Tuning Advisor examines how queries are processed in the databases you specify, and then recommends how you can improve query processing performance by modifying database structures such as indexes, indexed views, and partitioning.</span></span>  
  
 <span data-ttu-id="40e15-105">Помощник по настройке ядра СУБД предоставляет два пользовательских интерфейса: графический интерфейс пользователя (GUI) и программу командной строки **dta** .</span><span class="sxs-lookup"><span data-stu-id="40e15-105">Database Engine Tuning Advisor provides two user interfaces: a graphical user interface (GUI) and the **dta** command prompt utility.</span></span> <span data-ttu-id="40e15-106">Графический пользовательский интерфейс позволяет быстро просматривать результаты сеансов настройки, а программа **dta** облегчает внедрение функциональных возможностей помощника по настройке ядра СУБД в скрипты для автоматической настройки.</span><span class="sxs-lookup"><span data-stu-id="40e15-106">The GUI makes it easy to quickly view the results of tuning sessions, and the **dta** utility makes it easy to incorporate Database Engine Tuning Advisor functionality into scripts for automated tuning.</span></span> <span data-ttu-id="40e15-107">Кроме того, помощник по настройке ядра СУБД может принимать входные данные на языке XML, что обеспечивает расширенный контроль процесса настройки.</span><span class="sxs-lookup"><span data-stu-id="40e15-107">In addition, Database Engine Tuning Advisor can take XML input, which offers more control over the tuning process.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="40e15-108">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="40e15-108">What You Will Learn</span></span>  
 <span data-ttu-id="40e15-109">В этом учебнике рассматривается навигация в графическом пользовательском интерфейсе помощника по настройке ядра СУБД, а также выполнение некоторых базовых задач с использованием GUI и программы **dta** .</span><span class="sxs-lookup"><span data-stu-id="40e15-109">This tutorial will teach you how to navigate the Database Engine Tuning Advisor GUI, and how to perform some basic tasks with both the GUI and the **dta** utility.</span></span> <span data-ttu-id="40e15-110">Учебник содержит следующие занятия:</span><span class="sxs-lookup"><span data-stu-id="40e15-110">It contains the following lessons:</span></span>  
  
 [<span data-ttu-id="40e15-111">Занятие 1. Основы перемещения в помощнике по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="40e15-111">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
 <span data-ttu-id="40e15-112">На этом занятии рассматривается графический интерфейс нового помощника по настройке ядра СУБД, а также установка параметров отображения и разметки.</span><span class="sxs-lookup"><span data-stu-id="40e15-112">In this lesson, you will familiarize yourself with the new Database Engine Tuning Advisor GUI and learn how to set display options and layout.</span></span>  
  
 [<span data-ttu-id="40e15-113">Занятие 2. Использование помощника по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="40e15-113">Lesson 2: Using Database Engine Tuning Advisor</span></span>](lesson-2-using-database-engine-tuning-advisor.md)  
 <span data-ttu-id="40e15-114">На этом занятии рассматривается выполнение базовых задач настройки графического интерфейса помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="40e15-114">In this lesson, you will learn how to perform basic tuning tasks with the Database Engine Tuning Advisor GUI.</span></span>  
  
 [<span data-ttu-id="40e15-115">Урок 3. Использование служебной программы командной строки dta</span><span class="sxs-lookup"><span data-stu-id="40e15-115">Lesson 3: Using the dta Command Prompt Utility</span></span>](lesson-3-using-the-dta-command-prompt-utility.md)  
 <span data-ttu-id="40e15-116">На этом занятии рассматриваются запуск программы командной строки **dta** и выполнение ряда простейших команд по настройке.</span><span class="sxs-lookup"><span data-stu-id="40e15-116">In this lesson, you learn how to start the **dta** command prompt utility and how to run some simple tuning commands.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e15-117">Требования</span><span class="sxs-lookup"><span data-stu-id="40e15-117">Requirements</span></span>  
 <span data-ttu-id="40e15-118">Этот учебник предназначен для администраторов баз данных, незнакомых с графическим пользовательским интерфейсом помощника по настройке ядра СУБД или программой командной строки **dta** , однако имеющих представление о концепциях и структурах баз данных, таких как индексы и индексированные представления.</span><span class="sxs-lookup"><span data-stu-id="40e15-118">This tutorial is intended for database administrators who are not familiar with the Database Engine Tuning Advisor GUI or the **dta** command prompt utility, but who are experienced with database concepts and structures, such as indexes and indexed views.</span></span>  
  
 <span data-ttu-id="40e15-119">Необходимо установить [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (или более позднюю версию) с образцом базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40e15-119">You must install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (or a later version) with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="40e15-120">В целях повышения безопасности образцы баз данных по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="40e15-120">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="40e15-121">Дополнительные сведения об установке образцов баз данных см. в статье [Установка образцов SQL Server и образцов баз данных](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="40e15-121">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="40e15-122">После завершения работы с этим учебником</span><span class="sxs-lookup"><span data-stu-id="40e15-122">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="40e15-123">Выполнив задания этого учебника, изучите следующие разделы, чтобы получить дополнительные сведения о помощнике по настройке ядра СУБД:</span><span class="sxs-lookup"><span data-stu-id="40e15-123">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="40e15-124">В статье[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) описывается выполнение задач с использованием этого средства.</span><span class="sxs-lookup"><span data-stu-id="40e15-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="40e15-125">[dta Utility](dta-utility.md) — справочный материал по программе командной строки и дополнительному XML-файлу, который вы можете использовать для управления ее работой.</span><span class="sxs-lookup"><span data-stu-id="40e15-125">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="40e15-126">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="40e15-126">Next Lesson</span></span>  
 [<span data-ttu-id="40e15-127">Занятие 1. Основы перемещения в помощнике по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="40e15-127">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
