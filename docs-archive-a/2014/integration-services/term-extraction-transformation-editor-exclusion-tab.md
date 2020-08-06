---
title: Редактор преобразования "Извлечение терминов" (вкладка "исключение") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bc4b0401a1dd27111d0498e9e0d848c80da1742
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668432"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a><span data-ttu-id="8bd2c-102">Редактор преобразования «Извлечение терминов» (вкладка «Исключения»)</span><span class="sxs-lookup"><span data-stu-id="8bd2c-102">Term Extraction Transformation Editor (Exclusion Tab)</span></span>
  <span data-ttu-id="8bd2c-103">Используйте вкладку **Исключение** в диалоговом окне **Редактор преобразования «Извлечение терминов»** для установки соединения с таблицей исключений и указания столбцов, в которых содержатся исключаемые термины.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-103">Use the **Exclusion** tab of the **Term Extraction Transformation Editor** dialog box to set up a connection to an exclusion table and specify the columns that contain exclusion terms.</span></span>  
  
 <span data-ttu-id="8bd2c-104">Дополнительные сведения о преобразовании «Извлечения терминов» см. в разделе [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8bd2c-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8bd2c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bd2c-105">Options</span></span>  
 <span data-ttu-id="8bd2c-106">**Использовать исключаемые термины**</span><span class="sxs-lookup"><span data-stu-id="8bd2c-106">**Use exclusion terms**</span></span>  
 <span data-ttu-id="8bd2c-107">Укажите, необходимо ли исключать определенные термины в процессе извлечения терминов, определив столбцы, содержащие исключаемые термины.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-107">Indicate whether to exclude specific terms during term extraction by specifying a column that contains exclusion terms.</span></span> <span data-ttu-id="8bd2c-108">Необходимо указать следующие свойства источника, если принято решение исключать термины.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-108">You must specify the following source properties if you choose to exclude terms.</span></span>  
  
 <span data-ttu-id="8bd2c-109">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="8bd2c-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="8bd2c-110">Выберите существующий диспетчер соединений OLE DB или создайте новое соединение, выбрав **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-110">Select an existing OLE DB connection manager, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="8bd2c-111">**Создать**</span><span class="sxs-lookup"><span data-stu-id="8bd2c-111">**New**</span></span>  
 <span data-ttu-id="8bd2c-112">Создайте новое соединение с базой данных, используя диалоговое окно **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="8bd2c-112">Create a new connection to a database by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="8bd2c-113">**Таблица или представление**</span><span class="sxs-lookup"><span data-stu-id="8bd2c-113">**Table or view**</span></span>  
 <span data-ttu-id="8bd2c-114">Выберите таблицу или представление, которое содержит исключаемые термины.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-114">Select the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="8bd2c-115">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8bd2c-115">**Column**</span></span>  
 <span data-ttu-id="8bd2c-116">Выберите столбец в таблице или представлении, который содержит исключаемые термины.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-116">Select the column in the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="8bd2c-117">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="8bd2c-117">**Configure Error Output**</span></span>  
 <span data-ttu-id="8bd2c-118">Используйте диалоговое окно [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) для указания метода обработки ошибок для строк, вызвавших ошибку.</span><span class="sxs-lookup"><span data-stu-id="8bd2c-118">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd2c-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="8bd2c-119">See Also</span></span>  
 <span data-ttu-id="8bd2c-120">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8bd2c-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8bd2c-121">[Редактор преобразования "Извлечение терминов" &#40;вкладка "Извлечение терминов"&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="8bd2c-121">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="8bd2c-122">[Редактор преобразования "Извлечение терминов" &#40;вкладка "Дополнительно"&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="8bd2c-122">[Term Extraction Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="8bd2c-123">Преобразование "Уточняющий запрос термина"</span><span class="sxs-lookup"><span data-stu-id="8bd2c-123">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
