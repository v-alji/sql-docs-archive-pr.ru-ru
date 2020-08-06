---
title: Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.columns.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: aaf45327-79e9-4760-9b4d-546ace91b5b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9294022b52536940916a381d7b811437eaa5814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729626"
---
# <a name="fuzzy-lookup-transformation-editor-columns-tab"></a><span data-ttu-id="c0558-102">Редактор преобразования «Нечеткий уточняющий запрос» (вкладка «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="c0558-102">Fuzzy Lookup Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="c0558-103">Вкладка **Столбцы** диалогового окна **Редактор преобразования «Нечеткий уточняющий запрос»** используется для установки свойств входных и выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="c0558-103">Use the **Columns** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set properties for input and output columns.</span></span>  
  
 <span data-ttu-id="c0558-104">Дополнительные сведения о преобразовании «Нечеткий уточняющий запрос» см. в разделе [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c0558-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0558-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0558-105">Options</span></span>  
 <span data-ttu-id="c0558-106">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="c0558-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="c0558-107">Перетащите входные столбцы для подсоединения к доступным уточняющим столбцам.</span><span class="sxs-lookup"><span data-stu-id="c0558-107">Drag input columns to connect them to available lookup columns.</span></span> <span data-ttu-id="c0558-108">Эти столбцы должны иметь совпадающие и поддерживаемые типы данных.</span><span class="sxs-lookup"><span data-stu-id="c0558-108">These columns must have matching, supported data types.</span></span> <span data-ttu-id="c0558-109">Выберите строку сопоставления и щелкните ее правой кнопкой мыши, чтобы изменить ее в диалоговом окне [Создание связей](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="c0558-109">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="c0558-110">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c0558-110">**Name**</span></span>  
 <span data-ttu-id="c0558-111">Просмотрите имена доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="c0558-111">View the names of the available input columns.</span></span>  
  
 <span data-ttu-id="c0558-112">**Передать**</span><span class="sxs-lookup"><span data-stu-id="c0558-112">**Pass Through**</span></span>  
 <span data-ttu-id="c0558-113">Укажите, нужно ли включать входные столбцы в вывод преобразования.</span><span class="sxs-lookup"><span data-stu-id="c0558-113">Specify whether to include the input columns in the output of the transformation.</span></span>  
  
 <span data-ttu-id="c0558-114">**Доступные уточняющие столбцы**</span><span class="sxs-lookup"><span data-stu-id="c0558-114">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="c0558-115">С помощью флажков выберите столбцы, по которым выполняется нечеткий уточняющий запрос.</span><span class="sxs-lookup"><span data-stu-id="c0558-115">Use the check boxes to select columns on which to perform fuzzy lookup operations.</span></span>  
  
 <span data-ttu-id="c0558-116">**Уточняющий столбец**</span><span class="sxs-lookup"><span data-stu-id="c0558-116">**Lookup Column**</span></span>  
 <span data-ttu-id="c0558-117">Выберите уточняющие столбцы из списка доступных столбцов в ссылочной таблице.</span><span class="sxs-lookup"><span data-stu-id="c0558-117">Select lookup columns from the list of available reference table columns.</span></span> <span data-ttu-id="c0558-118">Выбор отражается установкой флажков в таблице **Доступные столбцы подстановок** .</span><span class="sxs-lookup"><span data-stu-id="c0558-118">Your selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span> <span data-ttu-id="c0558-119">При выборе столбца в таблице **Доступные столбцы подстановок** создается выходной столбец, содержащий значение столбца ссылочной таблицы для каждой совпадающей возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="c0558-119">Selecting a column in the **Available Lookup Columns** table creates an output column that contains the reference table column value for each matching row returned.</span></span>  
  
 <span data-ttu-id="c0558-120">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="c0558-120">**Output Alias**</span></span>  
 <span data-ttu-id="c0558-121">Введите псевдоним выхода для каждого уточняющего столбца.</span><span class="sxs-lookup"><span data-stu-id="c0558-121">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="c0558-122">По умолчанию, это будет имя уточняющего столбца с присоединенным индексным значением; однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="c0558-122">The default is the name of the lookup column with a numeric index value appended; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0558-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0558-123">See Also</span></span>  
 <span data-ttu-id="c0558-124">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c0558-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c0558-125">[Редактор преобразования "Нечеткий уточняющий запрос" &#40;вкладка "ссылочная таблица"&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="c0558-125">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="c0558-126">Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="c0558-126">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
