---
title: Диалоговое окно "Свойства набора данных" — "поля" | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656249"
---
# <a name="dataset-properties-dialog-box-fields"></a><span data-ttu-id="c4ea6-102">Диалоговое окно «Свойства набора данных» — «Поля»</span><span class="sxs-lookup"><span data-stu-id="c4ea6-102">Dataset Properties Dialog Box, Fields</span></span>
  <span data-ttu-id="c4ea6-103">Чтобы изменить коллекцию полей для набора данных отчета, перейдите на вкладку **Поля** в диалоговом окне **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="c4ea6-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="c4ea6-104">Список полей формируется автоматически, но с помощью вкладки **Поля** можно добавлять, изменять и удалять поля запросов и вычисляемые поля.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c4ea6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4ea6-105">Options</span></span>  
 <span data-ttu-id="c4ea6-106">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="c4ea6-106">**Add**</span></span>  
 <span data-ttu-id="c4ea6-107">Добавляет в набор данных новое поле запроса или вычисляемое поле.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-107">Add a new query field or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="c4ea6-108">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="c4ea6-108">**Delete**</span></span>  
 <span data-ttu-id="c4ea6-109">Удалить выбранное поле из набора данных.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-109">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="c4ea6-110">**Имя поля**</span><span class="sxs-lookup"><span data-stu-id="c4ea6-110">**Field Name**</span></span>  
 <span data-ttu-id="c4ea6-111">Введите имя для поля.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-111">Type a name for the field.</span></span> <span data-ttu-id="c4ea6-112">Имя поля должно быть уникально в пределах набора данных.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-112">The field must be unique within the dataset.</span></span> <span data-ttu-id="c4ea6-113">Имя каждого существующего поля в запросе набора данных заполняется заранее.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-113">For each existing field in the dataset query, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="c4ea6-114">**Источник поля**</span><span class="sxs-lookup"><span data-stu-id="c4ea6-114">**Field Source**</span></span>  
 <span data-ttu-id="c4ea6-115">Введите значение для поля.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-115">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="c4ea6-116">Для вычисляемого поля источник должен иметь имя существующего поля, возвращаемого запросом набора данных, или имя выражения, создаваемого пользователем.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-116">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="c4ea6-117">Например, чтобы создать поле, представляющее удесятеренное значение поля Sales в запросе, используйте выражение `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-117">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="c4ea6-118">Для поля запроса источник должен иметь имя существующего поля, возвращаемого запросом набора данных.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-118">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="c4ea6-119">**Выражение (fx)**</span><span class="sxs-lookup"><span data-stu-id="c4ea6-119">**Expression (fx)**</span></span>  
 <span data-ttu-id="c4ea6-120">Добавляет или изменяет выражение для вычисляемого поля.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-120">Add or change an expression for the calculated field.</span></span> <span data-ttu-id="c4ea6-121">Эта кнопка появляется, только если нажать кнопку **Добавить** и выбрать пункт **Вычисляемое поле**.</span><span class="sxs-lookup"><span data-stu-id="c4ea6-121">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ea6-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4ea6-122">See Also</span></span>  
 <span data-ttu-id="c4ea6-123">[Коллекция полей набора данных (построитель отчетов и службы SSRS)](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4ea6-123">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4ea6-124">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4ea6-124">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="c4ea6-125">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c4ea6-125">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
