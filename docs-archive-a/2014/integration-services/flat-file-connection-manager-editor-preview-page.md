---
title: Редактор диспетчера соединений с неструктурированными файлами (страница предварительного просмотра) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.preview.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: de47ea98-135e-4730-900e-dac629848798
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0f71b347bc943216a4b309cc58202ed8ab9183e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655870"
---
# <a name="flat-file-connection-manager-editor-preview-page"></a><span data-ttu-id="07597-102">Редактор диспетчера соединения с неструктурированными файлами (страница «Предварительный просмотр»)</span><span class="sxs-lookup"><span data-stu-id="07597-102">Flat File Connection Manager Editor (Preview Page)</span></span>
  <span data-ttu-id="07597-103">Узел **Предварительный просмотр** диалогового окна **Редактор диспетчера соединения с неструктурированными файлами** предназначен для просмотра содержимого исходного файла в табличном формате.</span><span class="sxs-lookup"><span data-stu-id="07597-103">Use the **Preview** node of the **Flat File Connection Manager Editor** dialog box to view the contents of the source file in a tabular format.</span></span>  
  
 <span data-ttu-id="07597-104">Дополнительные сведения о диспетчере соединений с неструктурированными файлами см. в разделе [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="07597-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="07597-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="07597-105">Options</span></span>  
 <span data-ttu-id="07597-106">**Имя диспетчера подключений**</span><span class="sxs-lookup"><span data-stu-id="07597-106">**Connection manager name**</span></span>  
 <span data-ttu-id="07597-107">Укажите уникальное имя для соединения с неструктурированным файлом в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="07597-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="07597-108">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07597-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="07597-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="07597-109">**Description**</span></span>  
 <span data-ttu-id="07597-110">Опишите соединение.</span><span class="sxs-lookup"><span data-stu-id="07597-110">Describe the connection.</span></span> <span data-ttu-id="07597-111">Рекомендуется описать цель соединения, чтобы пакеты самодокументировались и их проще было обслуживать.</span><span class="sxs-lookup"><span data-stu-id="07597-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="07597-112">**Количество пропускаемых строк данных**</span><span class="sxs-lookup"><span data-stu-id="07597-112">**Data rows to skip**</span></span>  
 <span data-ttu-id="07597-113">Укажите, сколько строк необходимо пропустить в начале неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="07597-113">Specify how many rows to skip at the beginning of the flat file.</span></span>  
  
 <span data-ttu-id="07597-114">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="07597-114">**Refresh**</span></span>  
 <span data-ttu-id="07597-115">Просмотрите эффект от изменения числа пропускаемых строк, нажав кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="07597-115">View the effect of changing the number of rows to skip by clicking **Refresh**.</span></span> <span data-ttu-id="07597-116">Эта кнопка становится видимой только после изменения других параметров соединения.</span><span class="sxs-lookup"><span data-stu-id="07597-116">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="07597-117">**Предварительный просмотр строк**</span><span class="sxs-lookup"><span data-stu-id="07597-117">**Preview rows**</span></span>  
 <span data-ttu-id="07597-118">Просмотр данных выборки в неструктурированном файле, разделенном на столбцы и строки согласно выбранным параметрам.</span><span class="sxs-lookup"><span data-stu-id="07597-118">View sample data in the flat file, divided into columns and rows according to the options you have selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07597-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="07597-119">See Also</span></span>  
 <span data-ttu-id="07597-120">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="07597-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="07597-121">[Редактор диспетчера соединений с неструктурированными файлами &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="07597-121">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="07597-122">[Редактор диспетчера соединений с неструктурированными файлами &#40;столбцы&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="07597-122">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="07597-123">Редактор диспетчера подключений к неструктурированным файлам (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="07597-123">Flat File Connection Manager Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)  
  
  
