---
title: Определение версии схемы определения отчета (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 413a270a3722ddda1f418c748fa5b7fba50dfeea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732397"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a><span data-ttu-id="9455c-102">Определение версии схемы определения отчета (SSRS)</span><span class="sxs-lookup"><span data-stu-id="9455c-102">Find the Report Definition Schema Version (SSRS)</span></span>
  <span data-ttu-id="9455c-103">В файле определения отчета указывается пространство имен языка определения отчетов для версии схемы определения отчета, использованной для проверки RDL-файла.</span><span class="sxs-lookup"><span data-stu-id="9455c-103">A report definition file specifies the RDL namespace for the version of the report definition schema that is used to validate the rdl file.</span></span> <span data-ttu-id="9455c-104">Если RDL-файл открывается в среде разработки отчетов, такой как конструктор в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , или построителе отчетов и если отчет был создан в предыдущем пространстве имен, автоматически создается файл резервной копии и отчет обновляется до текущего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9455c-104">When you open an .rdl file in a report authoring environment such as Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or Report Builder, if the report was created for a previous namespace, a backup file is automatically created, and the report is upgraded to the current namespace.</span></span> <span data-ttu-id="9455c-105">Если сохранить обновленное определение отчета, будет сохранен преобразованный RDL-файл.</span><span class="sxs-lookup"><span data-stu-id="9455c-105">If you save the upgraded report definition, you have saved the converted .rdl file.</span></span> <span data-ttu-id="9455c-106">Это единственный способ обновления определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="9455c-106">This is the only way to upgrade a report definition.</span></span> <span data-ttu-id="9455c-107">Само определение отчетов не обновляется на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="9455c-107">The report definition itself is not upgraded on a report server.</span></span> <span data-ttu-id="9455c-108">Скомпилированный отчет обновляется на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="9455c-108">The compiled report is upgraded on a report server.</span></span> <span data-ttu-id="9455c-109">Дополнительные сведения см. в разделе [Upgrade Reports](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="9455c-109">For more information, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a><span data-ttu-id="9455c-110">Инструкции. Определение версии RDL-схемы отчета</span><span class="sxs-lookup"><span data-stu-id="9455c-110">How to: Identify the RDL Schema Version of a Report</span></span>  
  
1.  <span data-ttu-id="9455c-111">Откройте файл отчета в формате RDL в приложении, таком как «Блокнот» или XML Notepad 2007, пригодном для просмотра XML-кода.</span><span class="sxs-lookup"><span data-stu-id="9455c-111">Open the report .rdl file in an application such as Notepad or XML Notepad 2007 in which you can view the xml.</span></span>  
  
     <span data-ttu-id="9455c-112">XML-элемент Report указывает пространство имен схемы.</span><span class="sxs-lookup"><span data-stu-id="9455c-112">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="9455c-113">Например, следующий элемент Report указывает пространство имен для конструктора отчетов и пространство имен для определения отчета.</span><span class="sxs-lookup"><span data-stu-id="9455c-113">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="9455c-114">Пространство имен определения отчета указано следующим URL-адресом: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span><span class="sxs-lookup"><span data-stu-id="9455c-114">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a><span data-ttu-id="9455c-115">Как определить версию RDL-схемы конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="9455c-115">How to: Identify the RDL Schema Version of Report Designer</span></span>  
  
1.  <span data-ttu-id="9455c-116">Открыть новый проект.</span><span class="sxs-lookup"><span data-stu-id="9455c-116">Open a new project.</span></span> <span data-ttu-id="9455c-117">Версия выбранного проекта определяет версию схемы языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="9455c-117">The version of the project that you choose determines the version of the RDL schema.</span></span> <span data-ttu-id="9455c-118">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]поддерживается использование нескольких версий схемы.</span><span class="sxs-lookup"><span data-stu-id="9455c-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], more than one schema version is supported.</span></span> <span data-ttu-id="9455c-119">Дополнительные сведения см. в разделе [Развертывание и поддержка версий в SQL Server Data Tools (службы SSRS)](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9455c-119">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="9455c-120">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="9455c-120">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="9455c-121">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="9455c-121">The **Add New Item** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="9455c-122">На панели **Шаблоны** нажмите кнопку **Отчет**.</span><span class="sxs-lookup"><span data-stu-id="9455c-122">In the **Templates** pane, click **Report**.</span></span>  
  
4.  <span data-ttu-id="9455c-123">В поле **Имя**введите имя отчета или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9455c-123">In **Name**, type a report name or accept the default.</span></span>  
  
5.  <span data-ttu-id="9455c-124">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9455c-124">Click **Add**.</span></span> <span data-ttu-id="9455c-125">Конструктор отчетов открывает новый пустой отчет в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="9455c-125">Report Designer opens a new blank report in Design view.</span></span>  
  
6.  <span data-ttu-id="9455c-126">В меню **Вид** выберите пункт **Код**.</span><span class="sxs-lookup"><span data-stu-id="9455c-126">On the **View** menu, click **Code**.</span></span> <span data-ttu-id="9455c-127">Определение отчета отображается в виде XML-файла.</span><span class="sxs-lookup"><span data-stu-id="9455c-127">The report definition is displayed as an XML file.</span></span>  
  
     <span data-ttu-id="9455c-128">XML-элемент Report указывает пространство имен схемы.</span><span class="sxs-lookup"><span data-stu-id="9455c-128">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="9455c-129">Например, следующий элемент Report указывает пространство имен для конструктора отчетов и пространство имен для определения отчета.</span><span class="sxs-lookup"><span data-stu-id="9455c-129">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="9455c-130">Пространство имен определения отчета указано следующим URL-адресом: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="9455c-130">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a><span data-ttu-id="9455c-131">Инструкции. Определение версии RDL-схемы отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="9455c-131">How to: Identify the RDL Schema Version on the Report Server</span></span>  
  
-   <span data-ttu-id="9455c-132">В диспетчере отчетов введите URL-адрес сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9455c-132">In Report Manager, type the URL for the report server.</span></span> <span data-ttu-id="9455c-133">Например, следующий URL-адрес указывает сервер отчетов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9455c-133">For example, the following URL specifies a report server on the local computer:</span></span>  
  
     `http://localhost/reportserver/reportdefinition.xsd`  
  
     <span data-ttu-id="9455c-134">XSD-файл открывается в браузере.</span><span class="sxs-lookup"><span data-stu-id="9455c-134">The .xsd file opens in the browser.</span></span>  
  
     <span data-ttu-id="9455c-135">Элемент XML-схемы указывает пространство имен схемы.</span><span class="sxs-lookup"><span data-stu-id="9455c-135">The XML schema element specifies the schema namespace.</span></span> <span data-ttu-id="9455c-136">Например, следующий элемент схемы указывает три пространства имен: ссылку targetNamespace, которая используется в среде [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], XSD-ссылку для самой схемы (XSD) и ссылку определения отчета.</span><span class="sxs-lookup"><span data-stu-id="9455c-136">For example, the following schema element specifies three namespaces: the targetNamespace reference that is used internally by [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the xsd reference for the schema itself (xsd), and the report definition reference.</span></span>  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     <span data-ttu-id="9455c-137">Пространство имен определения отчета указано следующим URL-адресом: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="9455c-137">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9455c-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="9455c-138">See Also</span></span>  
 <span data-ttu-id="9455c-139">[Обновление отчетов](../install-windows/upgrade-reports.md) </span><span class="sxs-lookup"><span data-stu-id="9455c-139">[Upgrade Reports](../install-windows/upgrade-reports.md) </span></span>  
 [<span data-ttu-id="9455c-140">Язык определения отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9455c-140">Report Definition Language &#40;SSRS&#41;</span></span>](report-definition-language-ssrs.md)  
  
  
