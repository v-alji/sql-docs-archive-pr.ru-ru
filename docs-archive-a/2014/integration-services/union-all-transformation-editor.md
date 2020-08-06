---
title: Редактор преобразования "объединить все" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656455"
---
# <a name="union-all-transformation-editor"></a><span data-ttu-id="a8d37-102">редактор преобразования «Объединить все»</span><span class="sxs-lookup"><span data-stu-id="a8d37-102">Union All Transformation Editor</span></span>
  <span data-ttu-id="a8d37-103">Для объединения нескольких входных наборов строк в один выходной набор строк используется диалоговое окно **Редактор преобразования «Объединить все»** .</span><span class="sxs-lookup"><span data-stu-id="a8d37-103">Use the **Union All Transformation Editor** dialog box to merge several input rowsets into a single output rowset.</span></span> <span data-ttu-id="a8d37-104">Включив преобразование «Объединить все» в поток данных, можно осуществлять слияние данных из нескольких потоков данных, создавать сложные наборы данных путем вложения преобразований «Объединить все» и повторно объединять строки после исправления ошибок данных.</span><span class="sxs-lookup"><span data-stu-id="a8d37-104">By including the Union All transformation in a data flow, you can merge data from multiple data flows, create complex datasets by nesting Union All transformations, and re-merge rows after you correct errors in the data.</span></span>  
  
 <span data-ttu-id="a8d37-105">Дополнительные сведения о преобразовании «Объединить все» см. в разделе [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a8d37-105">To learn more about the Union All transformation, see [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a8d37-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="a8d37-106">Options</span></span>  
 <span data-ttu-id="a8d37-107">**Имя выходного столбца**</span><span class="sxs-lookup"><span data-stu-id="a8d37-107">**Output Column Name**</span></span>  
 <span data-ttu-id="a8d37-108">Введите псевдоним для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="a8d37-108">Type an alias for each column.</span></span> <span data-ttu-id="a8d37-109">По умолчанию, устанавливается имя входного столбца из первого (ссылочного) входного параметра, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="a8d37-109">The default is the name of the input column from the first (reference) input; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="a8d37-110">**Вход 1 преобразования «Объединить все»**</span><span class="sxs-lookup"><span data-stu-id="a8d37-110">**Union All Input 1**</span></span>  
 <span data-ttu-id="a8d37-111">Выберите из списка доступных входных столбцов в первом (ссылочном) входном параметре.</span><span class="sxs-lookup"><span data-stu-id="a8d37-111">Select from the list of available input columns in the first (reference) input.</span></span> <span data-ttu-id="a8d37-112">Метаданные сопоставляемых столбцов должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="a8d37-112">The metadata of mapped columns must match.</span></span>  
  
 <span data-ttu-id="a8d37-113">**Вход n преобразования «Объединить все»**</span><span class="sxs-lookup"><span data-stu-id="a8d37-113">**Union All Input n**</span></span>  
 <span data-ttu-id="a8d37-114">Выберите из списка доступных входных столбцов во втором и дополнительных входных параметрах.</span><span class="sxs-lookup"><span data-stu-id="a8d37-114">Select from the list of available input columns in the second and additional inputs.</span></span> <span data-ttu-id="a8d37-115">Метаданные сопоставляемых столбцов должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="a8d37-115">The metadata of mapped columns must match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d37-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8d37-116">See Also</span></span>  
 <span data-ttu-id="a8d37-117">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a8d37-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a8d37-118">[Объединение данных с помощью преобразования «объединить все»](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a8d37-118">[Merge Data by Using the Union All Transformation](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span></span>  
 <span data-ttu-id="a8d37-119">[Преобразование «Слияние»](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a8d37-119">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="a8d37-120">Преобразование "Соединение слиянием"</span><span class="sxs-lookup"><span data-stu-id="a8d37-120">Merge Join Transformation</span></span>](data-flow/transformations/merge-join-transformation.md)  
  
  
