---
title: rrRenderingError — ошибка служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rrRenderingError
ms.assetid: 0751efc3-b81b-44ee-8aac-8560f86ca322
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b44b042c5f3c0cfdb9ffb99d3f45ed073beb972a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732301"
---
# <a name="rrrenderingerror---reporting-services-error"></a><span data-ttu-id="a8f8c-102">rrRenderingError - Ошибка службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a8f8c-102">rrRenderingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="a8f8c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a8f8c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8f8c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a8f8c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a8f8c-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a8f8c-105">Event ID</span></span>|<span data-ttu-id="a8f8c-106">rrRenderingError</span><span class="sxs-lookup"><span data-stu-id="a8f8c-106">rrRenderingError</span></span>|  
|<span data-ttu-id="a8f8c-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="a8f8c-107">Event Source</span></span>|<span data-ttu-id="a8f8c-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span><span class="sxs-lookup"><span data-stu-id="a8f8c-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span></span>|  
|<span data-ttu-id="a8f8c-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="a8f8c-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="a8f8c-110">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a8f8c-110">Message Text</span></span>|<span data-ttu-id="a8f8c-111">Во время подготовки отчета к просмотру произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-111">An error occurred during rendering of the report.</span></span> <span data-ttu-id="a8f8c-112">(rrRenderingError) %1</span><span class="sxs-lookup"><span data-stu-id="a8f8c-112">(rrRenderingError) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8f8c-113">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a8f8c-113">Explanation</span></span>  
 <span data-ttu-id="a8f8c-114">Это сообщение возвращается, когда службам [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не удается подготовить к просмотру или экспортировать отчет.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-114">This message is returned when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] cannot render or export the report.</span></span>  
  
 <span data-ttu-id="a8f8c-115">Сообщение о неподдерживаемом размере обычно возникает, если указан недопустимый размер страницы на языке определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-115">A message that indicates that the size is not supported is typically caused when the specified RDL page size is not valid.</span></span> <span data-ttu-id="a8f8c-116">Укажите допустимый в языке определения отчетов размер страницы и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-116">Specify a valid RDL page size and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-117">Сообщение о неподдерживаемой единице измерения размера в языке определения отчетов обычно возникает, если указан недопустимый тип единиц измерения.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-117">A message that indicates that an RDL size measurement is not supported is typically caused when an unsupported unit type is specified.</span></span> <span data-ttu-id="a8f8c-118">Допустимы следующие типы единиц измерения: см, дюйм, мм, пика и пункт.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-118">Valid unit types are cm, in, mm, pc, and pt.</span></span> <span data-ttu-id="a8f8c-119">Укажите допустимый тип единиц измерения и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-119">Specify a valid unit type and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-120">Сообщение о том, что отрицательный размер не поддерживается, обычно возникает при вводе отрицательного размера страницы, например -5 см.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-120">A message that indicates that a negative size is not supported is typically caused when a negative measurement for the page size, for example -5 cm, is specified.</span></span> <span data-ttu-id="a8f8c-121">Укажите положительное число для размера страницы и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-121">Specify a positive number for the page size and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-122">Сообщение о том, что размер в языке определения отчетов находится вне допустимого диапазона, обычно возникает, если размер страницы находится за пределами допустимого размера полей.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-122">A message that indicates that an RDL size is specified out of range is typically caused when a measurement for the page size is outside of the valid page margin size.</span></span> <span data-ttu-id="a8f8c-123">Введите размер страницы в пределах допустимых размеров полей.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-123">Specify a measurement for the page size that is within the valid page margin sizes.</span></span>  
  
 <span data-ttu-id="a8f8c-124">Сообщение о том, что цвет не поддерживается, обычно возникает, если на языке определения отчетов указан недопустимый.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-124">A message that indicates that a color specified is not supported is typically caused when a color specified in the RDL is not valid.</span></span> <span data-ttu-id="a8f8c-125">Выберите цвет, поддерживаемый языком определения отчетов, и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-125">Choose a color supported by RDL and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-126">Сообщение о том, что метка действия необязательна только при использовании единичного действия (а при добавлении нескольких действий для каждого из них необходима своя метка), обычно возникает, если метка действия указана и недопустима.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-126">A message that indicates that the action label is only optional when using a single action and that adding multiple actions requires labels for each action is typically caused when an action label is specified and it is not valid.</span></span> <span data-ttu-id="a8f8c-127">Укажите допустимую метку для каждого действия.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-127">Specify a valid action label for each action.</span></span>  
  
 <span data-ttu-id="a8f8c-128">Сообщение о том, что аргумент стиля должен иметь определенный тип, обычно возникает, если введено неверное значение стиля для типа данных.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-128">A message that indicates the style argument has to be of a specific type is typically caused when an incorrect style value for the data type is specified.</span></span> <span data-ttu-id="a8f8c-129">Спецификация языка определения отчетов определяет допустимые типы, которые можно использовать в качестве значений стиля различных элементов языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-129">The RDL specification identifies the valid types that you can use in the style values of different RDL elements.</span></span> <span data-ttu-id="a8f8c-130">Например, значение «2pt» является недопустимым для цвета фона, а значение «true» неверно для высоты.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-130">For example, an incorrect style value for background color is "2pt" and incorrect value for height is "true".</span></span> <span data-ttu-id="a8f8c-131">Укажите правильное значение и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-131">Specify a correct value and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-132">Сообщение о том, что стиль границ не поддерживается, обычно возникает, если указан недопустимый стиль границ.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-132">A message that indicates that the border style is not supported is typically caused when the border style specified is not valid.</span></span> <span data-ttu-id="a8f8c-133">Укажите поддерживаемый стиль границ и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-133">Specify a supported border style and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-134">Сообщение о том, что тип MIME для рисунка не поддерживается, обычно возникает, если введен недопустимый тип MIME для элемента-изображения отчета.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-134">A message that indicates that the image mimetype is not supported is typically caused when the specified mimetype for an image report item is not valid.</span></span> <span data-ttu-id="a8f8c-135">Укажите поддерживаемый тип MIME для элемента отчета и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-135">Specify a supported mimetype for the report item and then try again.</span></span>  
  
 <span data-ttu-id="a8f8c-136">Сообщение о том, что количество строк превышает допустимое максимальное количество строк на страницу, обычно возникает, если превышено количество строк на листе Excel.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-136">A message that indicates that the number of rows exceeds the maximum possible rows per sheet is typically caused when the number of rows in an Excel worksheet is exceeded.</span></span> <span data-ttu-id="a8f8c-137">Программа Excel поддерживает до 65 000 строк.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-137">Excel supports up to 65,000 rows.</span></span>  
  
 <span data-ttu-id="a8f8c-138">Сообщение о том, что количество столбцов превышает допустимое максимальное количество столбцов на страницу, обычно возникает, если превышено количество столбцов на листе Excel.</span><span class="sxs-lookup"><span data-stu-id="a8f8c-138">A message that indicates that the number of columns exceeds the maximum possible columns per sheet is typically caused when the number of columns in an Excel worksheet is exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8f8c-139">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a8f8c-139">User Action</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="a8f8c-140">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="a8f8c-140">Internal-Only</span></span>  
  
