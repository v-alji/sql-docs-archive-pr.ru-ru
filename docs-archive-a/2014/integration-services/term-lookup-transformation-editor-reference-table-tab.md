---
title: Редактор преобразования "Уточняющий запрос термина" (вкладка "ссылочная таблица") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.referencetable.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 86ccec6d-615b-4f84-9226-ff80d8012f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f76f15d894896e70139ef80cb2ebad7004ef47ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668428"
---
# <a name="term-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="84a86-102">Редактор преобразования «Уточняющий запрос терминов» (вкладка «Ссылочная таблица»)</span><span class="sxs-lookup"><span data-stu-id="84a86-102">Term Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="84a86-103">Вкладка **Ссылочная таблица** диалогового окна **Редактор преобразования "Уточняющий запрос термина"** используется для установки соединения со ссылочной таблицей (таблицей уточняющих запросов).</span><span class="sxs-lookup"><span data-stu-id="84a86-103">Use the **Reference Table** tab of the **Term Lookup Transformation Editor** dialog box to specify the connection to the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="84a86-104">Дополнительные сведения о преобразовании «Уточняющий запрос термина» см. в разделе [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="84a86-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="84a86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84a86-105">Options</span></span>  
 <span data-ttu-id="84a86-106">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="84a86-106">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="84a86-107">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="84a86-107">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="84a86-108">**Создать**</span><span class="sxs-lookup"><span data-stu-id="84a86-108">**New**</span></span>  
 <span data-ttu-id="84a86-109">Создайте новое соединение с помощью диалогового окна **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="84a86-109">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="84a86-110">**Имя ссылочной таблицы**</span><span class="sxs-lookup"><span data-stu-id="84a86-110">**Reference table name**</span></span>  
 <span data-ttu-id="84a86-111">Позволяет выбрать таблицу или представление уточняющих запросов из базы данных путем выбора элемента из списка.</span><span class="sxs-lookup"><span data-stu-id="84a86-111">Select a lookup table or view from the database by selecting an item from the list.</span></span> <span data-ttu-id="84a86-112">Таблица или представление должны содержать столбец с существующим списком терминов, с которыми можно сравнивать текст исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="84a86-112">The table or view should contain a column with an existing list of terms that the text in the source column can be compared to.</span></span>  
  
 <span data-ttu-id="84a86-113">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="84a86-113">**Configure Error Output**</span></span>  
 <span data-ttu-id="84a86-114">Используйте диалоговое окно [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) для указания параметров обработки ошибок для строк, вызвавших ошибку.</span><span class="sxs-lookup"><span data-stu-id="84a86-114">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a86-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="84a86-115">See Also</span></span>  
 <span data-ttu-id="84a86-116">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="84a86-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="84a86-117">[Редактор преобразования "Уточняющий запрос термина" &#40;вкладка "Поиск терминов"&#41;](../../2014/integration-services/term-lookup-transformation-editor-term-lookup-tab.md) </span><span class="sxs-lookup"><span data-stu-id="84a86-117">[Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-term-lookup-tab.md) </span></span>  
 <span data-ttu-id="84a86-118">[Редактор преобразования "Уточняющий запрос термина" &#40;вкладка "Дополнительно"&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="84a86-118">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="84a86-119">Преобразование "Извлечение терминов"</span><span class="sxs-lookup"><span data-stu-id="84a86-119">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
