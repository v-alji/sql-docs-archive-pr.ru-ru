---
title: Использование управляемых классов SQLXML | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXML Managed Classes, sample applications
- examples [SQLXML], managed classes
- Managed Classes [SQLXML], samples
ms.assetid: 3f021290-00ee-44e1-af4b-33d3ba8c6302
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 634a0e4110b13931201edd026ee95028cb94e859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732993"
---
# <a name="using-the-sqlxml-managed-classes"></a><span data-ttu-id="b0eae-102">Использование управляемых классов SQLXML</span><span class="sxs-lookup"><span data-stu-id="b0eae-102">Using the SQLXML Managed Classes</span></span>
  <span data-ttu-id="b0eae-103">В этом разделе приводятся образцы приложений, которые демонстрируют способы использования управляемых классов [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML.</span><span class="sxs-lookup"><span data-stu-id="b0eae-103">This section provides sample applications that demonstrate how to use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML Managed Classes.</span></span>  
  
 <span data-ttu-id="b0eae-104">Сведения о доступе и изменении данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework и об использовании дельтами для обновления данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицах см. в разделе [доступ к функциям SQLXML в среде .NET](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b0eae-104">For information about accessing and modifying data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] within the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, and about using DiffGrams to update data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, see [Accessing SQLXML Functionality in the .NET Environment](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0eae-105">Можно также составить приложения [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio для массовой загрузки XML-документов с использованием массовой загрузки XML.</span><span class="sxs-lookup"><span data-stu-id="b0eae-105">You can also write [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio applications to bulk load XML documents by using XML Bulk Load.</span></span> <span data-ttu-id="b0eae-106">Дополнительные сведения см. в разделе [выполнение групповой загрузки XML-данных &#40;SQLXML 4,0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b0eae-106">For more information, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span> <span data-ttu-id="b0eae-107">Необходимо добавить в приложение ссылку на DLL-библиотеку массовой загрузки XML (Xblkld4.dll).</span><span class="sxs-lookup"><span data-stu-id="b0eae-107">You must add a reference to the XML Bulk Load DLL (Xblkld4.dll) in your application.</span></span> <span data-ttu-id="b0eae-108">Это DLL-библиотека COM, для которой Visual Studio .NET автоматически создает библиотеку-упаковщик.</span><span class="sxs-lookup"><span data-stu-id="b0eae-108">This is a COM DLL for which Visual Studio .NET automatically creates the wrapper library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0eae-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b0eae-109">In This Section</span></span>  
 [<span data-ttu-id="b0eae-110">Исполнение запросов SQL &#40;управляемых классов SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="b0eae-110">Executing SQL Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
  [<span data-ttu-id="b0eae-111">Выполнение SQL-запросов с использованием метода ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="b0eae-111">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md)  
  [<span data-ttu-id="b0eae-112">Обработка XML на стороне клиента &#40;управляемые классы SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="b0eae-112">Processing XML on the Client Side &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/processing-xml-on-the-client-side-sqlxml-managed-classes.md)  
  [<span data-ttu-id="b0eae-113">Запросы XPath, &#40;управляемые классы SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="b0eae-113">Executing XPath Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-sqlxml-managed-classes.md)  
  [<span data-ttu-id="b0eae-114">Выполнять запросы XPath с пространствами имен &#40;управляемых классов SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="b0eae-114">Executing XPath Queries with Namespaces &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-with-namespaces-sqlxml-managed-classes.md)  
  [<span data-ttu-id="b0eae-115">Выполнение файлов шаблонов с использованием свойства CommandText</span><span class="sxs-lookup"><span data-stu-id="b0eae-115">Executing Template Files by Using the CommandText Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md)  
  [<span data-ttu-id="b0eae-116">Выполнение файлов шаблонов через свойство CommandStream</span><span class="sxs-lookup"><span data-stu-id="b0eae-116">Executing Template Files by Using the CommandStream Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandstream-property.md)  
  [<span data-ttu-id="b0eae-117">Применение преобразования XSL &#40;управляемых классов SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="b0eae-117">Applying an XSL Transformation &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/applying-an-xsl-transformation-sqlxml-managed-classes.md)  
  
