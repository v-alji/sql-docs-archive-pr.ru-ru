---
title: Свойство Detail | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Detail property
- SoapException class
ms.assetid: c1ddaeb6-c540-49fa-b06e-b6359d377ee8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 060fbaba2b8d4f5a5171e8aa7995432622ba2ba0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734998"
---
# <a name="detail-property"></a><span data-ttu-id="7984b-102">Свойство Detail</span><span class="sxs-lookup"><span data-stu-id="7984b-102">Detail Property</span></span>
  <span data-ttu-id="7984b-103">Свойство **Detail** класса [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** служб  имеет следующую структуру XML:</span><span class="sxs-lookup"><span data-stu-id="7984b-103">The **Detail** property of the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** class has the following XML structure:</span></span>  
  
## <a name="elements"></a><span data-ttu-id="7984b-104">Элементы</span><span class="sxs-lookup"><span data-stu-id="7984b-104">Elements</span></span>  
 <span data-ttu-id="7984b-105">**Подробный сведения**</span><span class="sxs-lookup"><span data-stu-id="7984b-105">**Detail**</span></span>  
 <span data-ttu-id="7984b-106">Элемент верхнего уровня, содержащий все остальные элементы данных об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7984b-106">The top-level element that contains all other error detail elements.</span></span>  
  
 <span data-ttu-id="7984b-107">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="7984b-107">**ErrorCode**</span></span>  
 <span data-ttu-id="7984b-108">Код ошибки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7984b-108">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-specific error code.</span></span>  
  
 <span data-ttu-id="7984b-109">**HttpStatus**</span><span class="sxs-lookup"><span data-stu-id="7984b-109">**HttpStatus**</span></span>  
 <span data-ttu-id="7984b-110">Код состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="7984b-110">The HTTP status code.</span></span>  
  
 <span data-ttu-id="7984b-111">**Message**</span><span class="sxs-lookup"><span data-stu-id="7984b-111">**Message**</span></span>  
 <span data-ttu-id="7984b-112">Сообщение об ошибке и код ошибки, присвоенный сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="7984b-112">The error message and the error code assigned by the report server.</span></span>  
  
 <span data-ttu-id="7984b-113">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="7984b-113">**HelpLink**</span></span>  
 <span data-ttu-id="7984b-114">URL-адрес справочной ссылки на веб-сайт, где находятся дополнительные сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7984b-114">The Help link URL to a Web site at which further information about the error can be found.</span></span> <span data-ttu-id="7984b-115">Дополнительные сведения см. в разделе [Элемент HelpLink](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="7984b-115">For more information, see [HelpLink Element](helplink-element.md).</span></span>  
  
 <span data-ttu-id="7984b-116">**LinkID**</span><span class="sxs-lookup"><span data-stu-id="7984b-116">**LinkID**</span></span>  
 <span data-ttu-id="7984b-117">Идентификатор, присвоенный ссылке.</span><span class="sxs-lookup"><span data-stu-id="7984b-117">The ID assigned to the link.</span></span>  
  
 <span data-ttu-id="7984b-118">**ProductName**</span><span class="sxs-lookup"><span data-stu-id="7984b-118">**ProductName**</span></span>  
 <span data-ttu-id="7984b-119">Имя продукта.</span><span class="sxs-lookup"><span data-stu-id="7984b-119">The name of the product.</span></span> <span data-ttu-id="7984b-120">Значение по умолчанию — **Microsoft SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="7984b-120">The default value is **Microsoft SQL Server Reporting Services**.</span></span>  
  
 <span data-ttu-id="7984b-121">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="7984b-121">**ProductVersion**</span></span>  
 <span data-ttu-id="7984b-122">Версия служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7984b-122">The version of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="7984b-123">Максимальная длина составляет 15 символов.</span><span class="sxs-lookup"><span data-stu-id="7984b-123">The maximum length is 15 characters.</span></span> <span data-ttu-id="7984b-124">Номер версии должен иметь следующий формат: 8.00.0xxx.00.</span><span class="sxs-lookup"><span data-stu-id="7984b-124">The format of the version number should be as follows: 8.00.0xxx.00.</span></span>  
  
 <span data-ttu-id="7984b-125">**ProductLocaleId**</span><span class="sxs-lookup"><span data-stu-id="7984b-125">**ProductLocaleId**</span></span>  
 <span data-ttu-id="7984b-126">Идентификатор локали или идентификатор языка библиотеки INTL приложения (например, 0x41A).</span><span class="sxs-lookup"><span data-stu-id="7984b-126">The locale ID or language ID of the application's INTL DLL (for example, 0x41A).</span></span>  
  
 <span data-ttu-id="7984b-127">**OperatingSystem**</span><span class="sxs-lookup"><span data-stu-id="7984b-127">**OperatingSystem**</span></span>  
 <span data-ttu-id="7984b-128">Операционная система, в которой установлены службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7984b-128">The operating system [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is installed on.</span></span> <span data-ttu-id="7984b-129">Допустимыми являются значение **0** (независимость от операционной системы), значение **1** ([!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)]) и значение **16** (Windows XP).</span><span class="sxs-lookup"><span data-stu-id="7984b-129">Valid values include **0** for operating system independent, **1** for [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)], and **16** for Windows XP.</span></span>  
  
 <span data-ttu-id="7984b-130">**CountryLocaleId**</span><span class="sxs-lookup"><span data-stu-id="7984b-130">**CountryLocaleId**</span></span>  
 <span data-ttu-id="7984b-131">Идентификатор локали или идентификатор языка операционной системы.</span><span class="sxs-lookup"><span data-stu-id="7984b-131">The locale ID or language ID of the operating system.</span></span> <span data-ttu-id="7984b-132">Например, для французской версии Windows используется значение 0x040c.</span><span class="sxs-lookup"><span data-stu-id="7984b-132">For example, the value for the French version of Windows is 0x040c.</span></span>  
  
 <span data-ttu-id="7984b-133">**MoreInformation**</span><span class="sxs-lookup"><span data-stu-id="7984b-133">**MoreInformation**</span></span>  
 <span data-ttu-id="7984b-134">XML-строка, содержащая вложенные исключения, сформированные во время выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="7984b-134">An XML string that contains nested exceptions that occurred while the method ran.</span></span>  
  
 <span data-ttu-id="7984b-135">**Source**</span><span class="sxs-lookup"><span data-stu-id="7984b-135">**Source**</span></span>  
 <span data-ttu-id="7984b-136">Дочерний элемент для элемента **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="7984b-136">A child element of **MoreInformation**.</span></span> <span data-ttu-id="7984b-137">Источник ошибки.</span><span class="sxs-lookup"><span data-stu-id="7984b-137">The source of the error.</span></span>  
  
 <span data-ttu-id="7984b-138">**Message**</span><span class="sxs-lookup"><span data-stu-id="7984b-138">**Message**</span></span>  
 <span data-ttu-id="7984b-139">Дочерний элемент для элемента **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="7984b-139">A child element of **MoreInformation**.</span></span> <span data-ttu-id="7984b-140">Сообщение ошибки для вложенного исключения.</span><span class="sxs-lookup"><span data-stu-id="7984b-140">The error message of a nested exception.</span></span> <span data-ttu-id="7984b-141">Этот элемент включает XML-атрибуты для элементов **ErrorCode** и **HelpLink**.</span><span class="sxs-lookup"><span data-stu-id="7984b-141">This element includes XML attributes for **ErrorCode** and **HelpLink**.</span></span>  
  
 <span data-ttu-id="7984b-142">**Предупреждения**</span><span class="sxs-lookup"><span data-stu-id="7984b-142">**Warnings**</span></span>  
 <span data-ttu-id="7984b-143">XML-строка, содержащая предупреждения, возвращенные при обработке отчета.</span><span class="sxs-lookup"><span data-stu-id="7984b-143">An XML string that contains the warnings returned from report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7984b-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="7984b-144">See Also</span></span>  
 <span data-ttu-id="7984b-145">[Введение в обработку исключений в Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7984b-145">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="7984b-146">[Reporting Services класс SoapException](reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="7984b-146">[Reporting Services SoapException Class](reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="7984b-147">Использование свойства Detail для обработки определенных ошибок</span><span class="sxs-lookup"><span data-stu-id="7984b-147">Using the Detail Property to Handle Specific Errors</span></span>](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
