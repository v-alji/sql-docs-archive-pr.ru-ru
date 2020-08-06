---
title: Редактор задачи «основная вставка» (страница «Параметры») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738642"
---
# <a name="bulk-insert-task-editor-options-page"></a><span data-ttu-id="3af81-102">Редактор задачи «Массовая вставка» (страница «Параметры»)</span><span class="sxs-lookup"><span data-stu-id="3af81-102">Bulk Insert Task Editor (Options Page)</span></span>
  <span data-ttu-id="3af81-103">Страница **Параметры** диалогового окна **Редактор задачи «Массовая вставка»** используется для установки свойств операции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="3af81-103">Use the **Options** page of the **Bulk Insert Task Editor** dialog box to set properties for the bulk insert operation.</span></span> <span data-ttu-id="3af81-104">С помощью задачи "Массовая вставка" большой объем данных копируется в таблицу или представление [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3af81-104">The Bulk Insert task copies large amounts of data into a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 <span data-ttu-id="3af81-105">Сведения о работе с массовой вставкой см. в разделах [Задача "Массовая вставка"](control-flow/bulk-insert-task.md) и [BULK INSERT(Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3af81-105">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3af81-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3af81-106">Options</span></span>  
 <span data-ttu-id="3af81-107">**CodePage**</span><span class="sxs-lookup"><span data-stu-id="3af81-107">**CodePage**</span></span>  
 <span data-ttu-id="3af81-108">Задает кодовую страницу данных в файле данных.</span><span class="sxs-lookup"><span data-stu-id="3af81-108">Specify the code page of the data in the data file.</span></span>  
  
 <span data-ttu-id="3af81-109">**DataFileType**</span><span class="sxs-lookup"><span data-stu-id="3af81-109">**DataFileType**</span></span>  
 <span data-ttu-id="3af81-110">Задает значение типа данных, используемых в операции загрузки.</span><span class="sxs-lookup"><span data-stu-id="3af81-110">Specify the data-type value to use in the load operation.</span></span>  
  
 <span data-ttu-id="3af81-111">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="3af81-111">**BatchSize**</span></span>  
 <span data-ttu-id="3af81-112">Задает количество строк в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="3af81-112">Specify the number of rows in a batch.</span></span> <span data-ttu-id="3af81-113">Значение по умолчанию равно количеству строк во всем файле данных.</span><span class="sxs-lookup"><span data-stu-id="3af81-113">The default is the entire data file.</span></span> <span data-ttu-id="3af81-114">Если параметр **BatchSize** имеет значение ноль, данные загружаются в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="3af81-114">If you set **BatchSize** to zero, the data is loaded in a single batch.</span></span>  
  
 <span data-ttu-id="3af81-115">**LastRow**</span><span class="sxs-lookup"><span data-stu-id="3af81-115">**LastRow**</span></span>  
 <span data-ttu-id="3af81-116">Задает последнюю строку для копирования.</span><span class="sxs-lookup"><span data-stu-id="3af81-116">Specify the last row to copy.</span></span>  
  
 <span data-ttu-id="3af81-117">**FirstRow**</span><span class="sxs-lookup"><span data-stu-id="3af81-117">**FirstRow**</span></span>  
 <span data-ttu-id="3af81-118">Задает первую строку, с которой должно начинаться копирование.</span><span class="sxs-lookup"><span data-stu-id="3af81-118">Specify the first row from which to start copying.</span></span>  
  
 <span data-ttu-id="3af81-119">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="3af81-119">**Options**</span></span>  
 |<span data-ttu-id="3af81-120">Термин</span><span class="sxs-lookup"><span data-stu-id="3af81-120">Term</span></span>|<span data-ttu-id="3af81-121">Определение</span><span class="sxs-lookup"><span data-stu-id="3af81-121">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="3af81-122">**Проверочные ограничения**</span><span class="sxs-lookup"><span data-stu-id="3af81-122">**Check constraints**</span></span>|<span data-ttu-id="3af81-123">Выберите для проверки ограничений таблицы и столбца.</span><span class="sxs-lookup"><span data-stu-id="3af81-123">Select to check the table and column constraints.</span></span>|  
|<span data-ttu-id="3af81-124">**Сохранять значения NULL**</span><span class="sxs-lookup"><span data-stu-id="3af81-124">**Keep nulls**</span></span>|<span data-ttu-id="3af81-125">Выберите для сохранения значений NULL во время операции массовой вставки вместо вставки значений по умолчанию для пустых столбцов.</span><span class="sxs-lookup"><span data-stu-id="3af81-125">Select to retain null values during the bulk insert operation, instead of inserting any default values for empty columns.</span></span>|  
|<span data-ttu-id="3af81-126">**Разрешить вставку в столбец идентификаторов**</span><span class="sxs-lookup"><span data-stu-id="3af81-126">**Enable identity insert**</span></span>|<span data-ttu-id="3af81-127">Выберите, чтобы вставлять существующие значения в столбец идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="3af81-127">Select to insert existing values into an identity column.</span></span>|  
|<span data-ttu-id="3af81-128">**Блокировка таблицы**</span><span class="sxs-lookup"><span data-stu-id="3af81-128">**Table lock**</span></span>|<span data-ttu-id="3af81-129">Выберите для блокировки таблицы во время операции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="3af81-129">Select to lock the table during the bulk insert.</span></span>|  
|<span data-ttu-id="3af81-130">**Запускать триггеры**</span><span class="sxs-lookup"><span data-stu-id="3af81-130">**Fire triggers**</span></span>|<span data-ttu-id="3af81-131">Выберите для срабатывания триггеров при вставке, обновлении или удалении в таблице.</span><span class="sxs-lookup"><span data-stu-id="3af81-131">Select to fire any insert, update, or delete triggers on the table.</span></span>|  
  
 <span data-ttu-id="3af81-132">**SortedData**</span><span class="sxs-lookup"><span data-stu-id="3af81-132">**SortedData**</span></span>  
 <span data-ttu-id="3af81-133">Определяет предложение ORDER BY в инструкции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="3af81-133">Specify the ORDER BY clause in the bulk insert statement.</span></span> <span data-ttu-id="3af81-134">Указываемое имя столбца должно быть действительным столбцом в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="3af81-134">The column name that you supply must be a valid column in the destination table.</span></span> <span data-ttu-id="3af81-135">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="3af81-135">The default is `false`.</span></span> <span data-ttu-id="3af81-136">Это означает, что данные не отсортированы с помощью предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="3af81-136">This means that the data is not sorted by an ORDER BY clause.</span></span>  
  
 <span data-ttu-id="3af81-137">**MaxErrors**</span><span class="sxs-lookup"><span data-stu-id="3af81-137">**MaxErrors**</span></span>  
 <span data-ttu-id="3af81-138">Определяет максимальное количество ошибок, которое может произойти перед отменой операции массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="3af81-138">Specify the maximum number of errors that can occur before the bulk insert operation is canceled.</span></span> <span data-ttu-id="3af81-139">Значение «0» указывает на то, что допускается бесконечное количество ошибок.</span><span class="sxs-lookup"><span data-stu-id="3af81-139">A value of 0 indicates that an infinite number of errors are allowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3af81-140">Каждая строка, которая не может быть импортирована операцией массовой загрузки, считается за одну ошибку.</span><span class="sxs-lookup"><span data-stu-id="3af81-140">Each row that cannot be imported by the bulk load operation is counted as one error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af81-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="3af81-141">See Also</span></span>  
 <span data-ttu-id="3af81-142">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3af81-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="3af81-143">[Редактор задачи "групповые вставки" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="3af81-143">[Bulk Insert Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="3af81-144">[Редактор задачи "Вставка в &#40;"&#41;страницу "соединение"](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="3af81-144">[Bulk Insert Task Editor &#40;Connection Page&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span></span>  
 <span data-ttu-id="3af81-145">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="3af81-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="3af81-146">Поток управления</span><span class="sxs-lookup"><span data-stu-id="3af81-146">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
