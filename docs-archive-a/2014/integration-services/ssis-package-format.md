---
title: Формат пакета служб SSIS | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cfe0e5dc-5be3-4222-b721-fe83665edd94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 524c65ac5682b8efe8c4191697eb540f9acca82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731881"
---
# <a name="ssis-package-format"></a><span data-ttu-id="7b0f5-102">Формат пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="7b0f5-102">SSIS Package Format</span></span>
  <span data-ttu-id="7b0f5-103">В текущем выпуске служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]внесены серьезные изменения в формат пакетов (файл DTSX), чтобы упростить чтение формата и сравнение пакетов.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-103">In the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], significant changes were made to the package format (.dtsx file) to make it easier to read the format and to compare packages.</span></span> <span data-ttu-id="7b0f5-104">Кроме того, можно более надежно выполнять слияние пакетов, которые не содержат конфликтующих изменений или изменений, хранящихся в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-104">You can also more reliably merge packages that don't contain conflicting changes or changes stored in binary format.</span></span>  
  
 <span data-ttu-id="7b0f5-105">Чтобы просмотреть текущий формат файла пакета DTSX, см. статью [ \[ MS-dtsx \] : спецификация формата XML-файла пакета служб DTS](https://go.microsoft.com/fwlink/?LinkId=233251).</span><span class="sxs-lookup"><span data-stu-id="7b0f5-105">To view the current DTSX package file format, see [\[MS-DTSX\]: Data Transformation Services Package XML File Format Specification](https://go.microsoft.com/fwlink/?LinkId=233251).</span></span>  
  
 <span data-ttu-id="7b0f5-106">В следующем списке перечислены изменения формата файла.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-106">The following list outlines the file format changes.</span></span> <span data-ttu-id="7b0f5-107">Чтобы просмотреть примеры кода этих изменений, см. раздел [Изменения формата пакета в SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span><span class="sxs-lookup"><span data-stu-id="7b0f5-107">To view code examples of these changes, see [Package Format Changes in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span></span>  
  
-   <span data-ttu-id="7b0f5-108">Правила форматирования применяются с целью упростить чтение и понимание DTSX-файла.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-108">Formatting conventions have been applied to make it easier to read and understand the .dtsx file.</span></span>  
  
-   <span data-ttu-id="7b0f5-109">Формат является более кратким.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-109">The format is more concise.</span></span> <span data-ttu-id="7b0f5-110">Отдельные элементы для каждого свойства были сохранены как атрибуты, за исключением PackageFormatVersion.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-110">Separate elements for each property have been persisted as attributes, with the exception of the PackageFormatVersion.</span></span> <span data-ttu-id="7b0f5-111">Атрибуты перечислены в алфавитном порядке, а свойства, имеющие значения по умолчанию, более не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-111">Attributes are listed alphabetically, and properties that have default values are no longer persisted.</span></span> <span data-ttu-id="7b0f5-112">И наконец, элементы, которые могут появиться несколько раз, теперь содержатся в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-112">Finally, elements that can appear multiple times, are now contained within a parent element.</span></span>  
  
-   <span data-ttu-id="7b0f5-113">Большинство элементов в пакете, на которые могут ссылаться другие объекты, теперь имеют атрибут `refId`, определенный в пакете XML.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-113">Most objects within a package that can be referred to by other objects now have a `refId` attribute defined in the package XML.</span></span> <span data-ttu-id="7b0f5-114">Вместо сохранения идентификаторов журнала обращений и преобразований теперь сохраняется `refID`.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-114">Instead of persisting lineage IDs, the `refID` is now persisted.</span></span> <span data-ttu-id="7b0f5-115">Идентификаторы журнала обращений и преобразований по-прежнему используются в среде выполнения и формируются заново при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-115">Lineage IDs are still used within the runtime and regenerated when the package is loaded.</span></span>  
  
     <span data-ttu-id="7b0f5-116">Значением `refId` является уникальная строка, удобная для чтения и понятная, по сравнению с идентификаторами GUID или целочисленными значениями.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-116">The `refId` value is a unique string that is readable and understandable, compared to GUIDs or integer values.</span></span> <span data-ttu-id="7b0f5-117">Строка похожа на значения пути, используемые для конфигураций пакетов в предыдущих выпусках [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b0f5-117">The string is similar to path values used for package configurations in previous releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="7b0f5-118">При объединении изменений между двумя версиями пакета `refId` может использоваться в операциях поиска/замены, чтобы обеспечить корректное обновление всех ссылок на объект.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-118">If you are merging changes between two versions of a package, the `refId` can be used in find/replace operations to ensure that all references to that object have been correctly updated.</span></span>  
  
-   <span data-ttu-id="7b0f5-119">Сведения о макете содержатся в разделе CData.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-119">The layout information is contained in a CData section.</span></span>  
  
-   <span data-ttu-id="7b0f5-120">Заметки сохраняются в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-120">Annotations are persisted in cleartext.</span></span> <span data-ttu-id="7b0f5-121">Это упрощает извлечение сведений для автоматического создания документации.</span><span class="sxs-lookup"><span data-stu-id="7b0f5-121">This makes it easier to extract the information for automated generation of documentation.</span></span>  
  
  
