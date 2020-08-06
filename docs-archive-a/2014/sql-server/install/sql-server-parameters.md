---
title: Параметры SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735846"
---
# <a name="sql-server-parameters"></a><span data-ttu-id="70902-102">Параметры SQL Server</span><span class="sxs-lookup"><span data-stu-id="70902-102">SQL Server Parameters</span></span>
  <span data-ttu-id="70902-103">На этой странице можно установить параметры, которые будут использованы для анализа компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70902-103">On this page, set parameters that the analyzer will use for [!INCLUDE[ssDE](../../includes/ssde-md.md)] analysis.</span></span> <span data-ttu-id="70902-104">Можно выполнить анализ одной, нескольких или всех баз данных, проанализировать файлы трассировки, созданные программой [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], и пакетные файлы SQL.</span><span class="sxs-lookup"><span data-stu-id="70902-104">You can analyze one, several, or all databases, analyze trace files that were created by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and analyze SQL batch files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70902-105">Некоторые проблемы обновления можно обнаружить только с помощью анализа файлов трассировки или пакетных файлов SQL.</span><span class="sxs-lookup"><span data-stu-id="70902-105">Some upgrade issues can be detected only if you submit trace files or SQL batch files to be analyzed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70902-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="70902-106">Options</span></span>  
 <span data-ttu-id="70902-107">**Базы данных для анализа**</span><span class="sxs-lookup"><span data-stu-id="70902-107">**Database(s) to analyze**</span></span>  
 <span data-ttu-id="70902-108">Чтобы проанализировать все базы данных, установите флажок **все базы данных** .</span><span class="sxs-lookup"><span data-stu-id="70902-108">To analyze all databases, select the **All databases** check box.</span></span> <span data-ttu-id="70902-109">Чтобы выполнить анализ выбранных баз данных, установите флажок рядом с каждой просматриваемой базой данной.</span><span class="sxs-lookup"><span data-stu-id="70902-109">To analyze a selection of databases, select the check box next to each database to include in the scan.</span></span>  
  
 <span data-ttu-id="70902-110">**Анализировать файлы трассировки**</span><span class="sxs-lookup"><span data-stu-id="70902-110">**Analyze trace file(s)**</span></span>  
 <span data-ttu-id="70902-111">Установите этот флажок, чтобы выполнить анализ файлов трассировки в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="70902-111">Select this check box to analyze trace files in the file system.</span></span>  
  
 <span data-ttu-id="70902-112">**Путь к файлам трассировки**</span><span class="sxs-lookup"><span data-stu-id="70902-112">**Path to trace file(s)**</span></span>  
 <span data-ttu-id="70902-113">Можно выполнить анализ одного или нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="70902-113">You can analyze one or more files.</span></span> <span data-ttu-id="70902-114">Можно выполнить обзор и выбрать несколько файлов или же задать несколько имен файлов.</span><span class="sxs-lookup"><span data-stu-id="70902-114">You can browse to a location and select multiple files, or you can provide multiple file names.</span></span> <span data-ttu-id="70902-115">Для каждого файла следует указывать полный путь, включая имя файла. Отдельные записи разделяются символом вертикальной черты (|).</span><span class="sxs-lookup"><span data-stu-id="70902-115">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="70902-116">Если включить **Анализ файлов трассировки**, **следующее** будет отключено до тех пор, пока не будет введен путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="70902-116">If you enable **Analyze trace file(s)**, **Next** is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="70902-117">**Анализ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пакетных файлов**</span><span class="sxs-lookup"><span data-stu-id="70902-117">**Analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="70902-118">Установите этот флажок, чтобы выполнить анализ пакетных файлов [!INCLUDE[tsql](../../includes/tsql-md.md)] в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="70902-118">Select this check box to analyze [!INCLUDE[tsql](../../includes/tsql-md.md)] batch files in the file system.</span></span>  
  
 <span data-ttu-id="70902-119">**Путь к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пакетным файлам**</span><span class="sxs-lookup"><span data-stu-id="70902-119">**Path to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="70902-120">Можно выполнить анализ одного или нескольких пакетных файлов.</span><span class="sxs-lookup"><span data-stu-id="70902-120">You can analyze one or more batch files.</span></span> <span data-ttu-id="70902-121">Можно выполнить обзор и выбрать несколько файлов или же задать несколько имен файлов.</span><span class="sxs-lookup"><span data-stu-id="70902-121">You can browse to a location and select multiple files, or you can type multiple file names.</span></span> <span data-ttu-id="70902-122">Для каждого файла следует указывать полный путь, включая имя файла. Отдельные записи разделяются символом вертикальной черты (|).</span><span class="sxs-lookup"><span data-stu-id="70902-122">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="70902-123">Если включить **анализ пакетных файлов SQL**, кнопка **Далее** будет неактивна, пока не будет введен путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="70902-123">If you enable **Analyze SQL batch file(s)**, the **Next** button is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="70902-124">**Разделитель пакетов SQL**</span><span class="sxs-lookup"><span data-stu-id="70902-124">**SQL Batch Separator**</span></span>  
 <span data-ttu-id="70902-125">Текст, используемый для разделения пакетов инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70902-125">The text that is used to separate batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="70902-126">Значение по умолчанию — **Go**.</span><span class="sxs-lookup"><span data-stu-id="70902-126">The default value is **GO**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70902-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="70902-127">See Also</span></span>  
 <span data-ttu-id="70902-128">[Работа с советником по переходу](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="70902-128">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="70902-129">Справочник по пользовательскому интерфейсу помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="70902-129">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
