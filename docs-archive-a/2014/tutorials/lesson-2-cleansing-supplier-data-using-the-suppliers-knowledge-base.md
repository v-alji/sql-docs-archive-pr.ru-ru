---
title: Занятие 2. Очистка данных поставщика с помощью базы знаний поставщиков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ebc0231cd0f28fcad23656cf22abd8d68eca7dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654676"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a><span data-ttu-id="fcd1b-102">Урок 2. Очистка данных в базе знаний о поставщиках</span><span class="sxs-lookup"><span data-stu-id="fcd1b-102">Lesson 2: Cleansing Supplier Data using the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="fcd1b-103">На этом занятии данные поставщика будут очищены в файле Excel с помощью базы знаний **поставщики** , созданной на первом занятии.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-103">In this lesson, you cleanse the supplier data in an Excel file by using the **Suppliers** knowledge base you have created in the first lesson.</span></span> <span data-ttu-id="fcd1b-104">Очистка данных в DQS включает в себя программный **процесс** , который анализирует соответствие данных набору знаний в базе знаний, а также **интерактивный процесс** , позволяющий просматривать и изменять результаты процесса, помогающего компьютерным процессам.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-104">Data cleansing in DQS includes a **computer-assisted process** that analyzes how data conforms to the knowledge in a knowledge base, and an **interactive process** that enables you to review and modify results from the computer-assisted process.</span></span> <span data-ttu-id="fcd1b-105">Функция очистки данных опознает неверные данные в источнике данных, а затем исправляет или предлагает поправки для неверных данных.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-105">The data cleansing feature identifies incorrect data in your data source and then corrects or suggests corrections for the incorrect data.</span></span> <span data-ttu-id="fcd1b-106">Она также стандартизирует и дополняет данные клиента с помощью значений домена, начальных значений для синонимов, правил домена, связей на основе терминов, а также ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-106">It also standardizes and enriches customer data by using domain values, leading values for synonyms, domain rules, term-based relations, and reference data.</span></span> <span data-ttu-id="fcd1b-107">Можно в интерактивном режиме утверждать или отклонять изменения, предлагаемые автоматизированным процессом.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-107">You can interactively approve or reject changes proposed by the computer-assisted process.</span></span> <span data-ttu-id="fcd1b-108">Дополнительные сведения см. в разделе [Очистка данных](https://msdn.microsoft.com/library/gg524800.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fcd1b-108">See [Data Cleansing](https://msdn.microsoft.com/library/gg524800.aspx) for more details.</span></span>  
  
 <span data-ttu-id="fcd1b-109">Автоматизированный процесс использует следующие пороговые значения, которые можно настроить с помощью параметра конфигурации на главной странице клиентского приложения служб DQS.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-109">The computer-assisted process uses the following threshold values that you can configure using the Configuration option on the DQS Client main page.</span></span>  
  
-   <span data-ttu-id="fcd1b-110">**Минимальный показатель для предложений:** Минимальный показатель или уровень достоверности, используемый службами DQS для предложения замены значения.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-110">**Min score for suggestions:** The minimum score or confidence level that is used by DQS for suggesting replacement for a value.</span></span>  
  
-   <span data-ttu-id="fcd1b-111">**Минимальная оценка для автоматической корректировки:** Минимальный показатель или уровень достоверности, используемый службами DQS для автоматического исправления значения.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-111">**Min score for auto corrections:** The minimum score or confidence level that is used by DQS for automatically correcting a value.</span></span>  
  
 <span data-ttu-id="fcd1b-112">Дополнительные сведения о настройке этих параметров см. в разделе [Настройка пороговых значений для очистки и сопоставления](https://msdn.microsoft.com/library/hh510415.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fcd1b-112">See [Configure Threshold Values for Cleansing and Matching](https://msdn.microsoft.com/library/hh510415.aspx) for details on how to configure these settings.</span></span>  
  
 <span data-ttu-id="fcd1b-113">На этом занятии будут выполнены следующие задачи для очистки входных данных с помощью базы знаний Suppliers.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-113">In this lesson, you perform the following tasks to cleanse the input data by using the Suppliers knowledge base.</span></span>  
  
1.  <span data-ttu-id="fcd1b-114">Создайте проект служб DQS для очистки, выберите базу знаний Suppliers в качестве базы знаний для использования при анализе и очистке исходных данных в файле Excel, а затем выберите действие «Очистка».</span><span class="sxs-lookup"><span data-stu-id="fcd1b-114">Create a Data Quality Project for Cleansing, select the Suppliers knowledge base as the knowledge base to use to analyze and cleanse the source data in an Excel file, and select the Cleansing activity.</span></span>  
  
2.  <span data-ttu-id="fcd1b-115">Сопоставьте столбцы Excel, которые необходимо очистить с соответствующими доменами или составными доменами служб DQS в базе знаний.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-115">Map the Excel columns that you want to cleanse to appropriate DQS domains/composite domains in the knowledge base.</span></span>  
  
3.  <span data-ttu-id="fcd1b-116">Запустите автоматизированное действие очистки.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-116">Run the computer-assisted cleansing activity.</span></span> <span data-ttu-id="fcd1b-117">Автоматизированный процесс отображает сведения о качестве данных в клиенте DQS, которые можно использовать для очистки данных в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-117">The computer-assisted process displays data quality information in the Data Quality Client that you can use to cleanse the data interactively.</span></span>  
  
4.  <span data-ttu-id="fcd1b-118">Просмотр результатов действия очистки и управление ими.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-118">View and manage the results of the cleansing activity.</span></span> <span data-ttu-id="fcd1b-119">Можно просматривать значения, которые автоматизированный процесс признал правильными, неверными, которые затем были исправлены, неверными с предложенным исправлением или недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-119">You can review the values that the computer-assisted process finds to be correct, incorrect but corrected, incorrect with a suggested change, or invalid.</span></span> <span data-ttu-id="fcd1b-120">Можно в интерактивном режиме утверждать или отклонять изменения, исправлять или переопределять предложения автоматизированного процесса с помощью поля «Исправить на».</span><span class="sxs-lookup"><span data-stu-id="fcd1b-120">You can interactively approve or reject changes, correcting or overriding the suggestion from the computer-assisted process by using the Correct To field.</span></span>  
  
5.  <span data-ttu-id="fcd1b-121">Экспортируйте результаты процесса очистки в файл Excel.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-121">Export the results from the cleansing process to an Excel file.</span></span>  
  
6.  <span data-ttu-id="fcd1b-122">Импортируйте значения из проекта очистки в домены, чтобы расширить знания в базе знаний с помощью новых правил, значений, исправлений и т. д.</span><span class="sxs-lookup"><span data-stu-id="fcd1b-122">Import the values from the cleansing project into domains to augment the knowledge in the knowledge base with new rules, values, corrections etc...</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="fcd1b-123">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fcd1b-123">Next Step</span></span>  
 [<span data-ttu-id="fcd1b-124">Задача 1. Создание проекта качества данных</span><span class="sxs-lookup"><span data-stu-id="fcd1b-124">Task 1: Creating a Data Quality Project</span></span>](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  
