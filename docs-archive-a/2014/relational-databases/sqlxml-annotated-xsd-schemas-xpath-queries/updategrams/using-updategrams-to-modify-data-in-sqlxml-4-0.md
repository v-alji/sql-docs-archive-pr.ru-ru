---
title: Использование диаграмм обновления для изменения данных в SQLXML 4,0 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- data insertions [SQLXML]
- data deletions [SQLXML]
- updating data [SQLXML]
- modifying data [SQLXML]
- OPENXML function
- updategrams [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- modifying databases
- data modifications [SQLXML]
- deleting data
- inserting data
ms.assetid: b8b3b892-cb73-41d0-b945-bce148d81d9b
author: rothja
ms.author: jroth
ms.openlocfilehash: a4a2397668ed08df91377cc35dea22fd52788580
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665950"
---
# <a name="using-updategrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="88029-102">Использование диаграмм обновления для изменения данных в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="88029-102">Using Updategrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="88029-103">Можно изменить (вставить, обновить или удалить) базу данных [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из существующего XML-документа с помощью функции диаграмма обновления или OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88029-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="88029-104">В этом разделе содержатся сведения о диаграммах обновления и примеры их использования.</span><span class="sxs-lookup"><span data-stu-id="88029-104">This section provides information about updategrams and examples of their usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88029-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="88029-105">In This Section</span></span>  
 [<span data-ttu-id="88029-106">Введение в диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-106">Introduction to Updategrams &#40;SQLXML 4.0&#41;</span></span>](introduction-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-107">Содержит основные сведения и примеры диаграмм обновления.</span><span class="sxs-lookup"><span data-stu-id="88029-107">Provides basic information and examples of updategrams.</span></span>  
  
 [<span data-ttu-id="88029-108">Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-108">Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;</span></span>](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)  
 <span data-ttu-id="88029-109">Содержит объяснение и примеры аннотированных схем сопоставления в диаграммах обновления.</span><span class="sxs-lookup"><span data-stu-id="88029-109">Explains and provides examples of annotated mapping schemas in updategrams.</span></span>  
  
 [<span data-ttu-id="88029-110">Обработка значений NULL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-110">NULL Handling &#40;SQLXML 4.0&#41;</span></span>](null-handling-sqlxml-4-0.md)  
 <span data-ttu-id="88029-111">Содержит описание задания значений NULL для значений элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="88029-111">Describes how to specify NULL for element and attribute values.</span></span>  
  
 [<span data-ttu-id="88029-112">Вставка данных с помощью XML диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-112">Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](inserting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-113">Содержит описание и примеры использования диаграмм обновления для добавления данных.</span><span class="sxs-lookup"><span data-stu-id="88029-113">Describes and provides examples of using updategrams to insert data.</span></span>  
  
 [<span data-ttu-id="88029-114">Удаление данных с помощью XML диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-114">Deleting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](deleting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-115">Содержит описание и примеры использования диаграмм обновления для удаления данных.</span><span class="sxs-lookup"><span data-stu-id="88029-115">Describes and provides examples of using updategrams to delete data.</span></span>  
  
 [<span data-ttu-id="88029-116">Обновление данных с помощью XML диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-116">Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](updating-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-117">Содержит описание и примеры использования диаграмм обновления для изменения существующих данных.</span><span class="sxs-lookup"><span data-stu-id="88029-117">Describes and provides examples of using updategrams to modify existing data.</span></span>  
  
 [<span data-ttu-id="88029-118">Передача параметров в диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-118">Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;</span></span>](passing-parameters-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-119">Содержит описание и примеры передачи параметров в диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="88029-119">Describes and provides examples of passing parameters to updategrams.</span></span>  
  
 [<span data-ttu-id="88029-120">Обработка проблем параллелизма базы данных в диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-120">Handling Database Concurrency Issues in Updategrams &#40;SQLXML 4.0&#41;</span></span>](handling-database-concurrency-issues-in-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-121">Содержит описание и примеры возможных уровней защиты для решения проблем параллелизма в диаграммах обновления.</span><span class="sxs-lookup"><span data-stu-id="88029-121">Describes the various levels of protection possible for handling concurrency issues in updategrams, and provides examples.</span></span>  
  
 [<span data-ttu-id="88029-122">Примеры приложений диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-122">Updategram Sample Applications &#40;SQLXML 4.0&#41;</span></span>](../../../database-engine/dev-guide/updategram-sample-applications-sqlxml-4-0.md)  
 <span data-ttu-id="88029-123">Содержит образцы приложений, использующих диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="88029-123">Provides sample applications that use updategrams.</span></span>  
  
 [<span data-ttu-id="88029-124">Рекомендации и ограничения для XML-диаграмм обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="88029-124">Guidelines and Limitations of XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="88029-125">Содержит перечень фактов, о которых необходимо помнить при работе с диаграммами обновления.</span><span class="sxs-lookup"><span data-stu-id="88029-125">Lists some things to remember when working with updategrams.</span></span>  
  
  
