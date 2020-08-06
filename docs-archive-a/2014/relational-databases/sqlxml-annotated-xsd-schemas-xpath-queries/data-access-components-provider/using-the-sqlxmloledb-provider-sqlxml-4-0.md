---
title: Использование поставщика SQLXMLOLEDB (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXMLOLEDB Provider, samples
- ClientSideXML property
ms.assetid: fbcefac5-29c9-478b-b0e0-d510b593f446
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e3c53eecd657d610c2fe90e108e0290e9b05b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664822"
---
# <a name="using-the-sqlxmloledb-provider-sqlxml-40"></a><span data-ttu-id="7ebcc-102">Использование поставщика SQLXMLOLEDB (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7ebcc-102">Using the SQLXMLOLEDB Provider (SQLXML 4.0)</span></span>
  <span data-ttu-id="7ebcc-103">Подразделы этого раздела содержат образцы приложений ADO, иллюстрирующих использование зависящих от поставщика SQLXMLOLEDB свойств.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-103">The topics in this section provide ADO sample applications that illustrate the use of SQLXMLOLEDB Provider-specific properties.</span></span>  
  
## <a name="application-requirements-for-sqlxmloledb-40-provider"></a><span data-ttu-id="7ebcc-104">Требования приложения для поставщика SQLXMLOLEDB версии 4.0</span><span class="sxs-lookup"><span data-stu-id="7ebcc-104">Application Requirements for SQLXMLOLEDB 4.0 Provider</span></span>  
 <span data-ttu-id="7ebcc-105">Чтобы создать рабочие образцы, использующие SQLXMLOLEDB версии 4.0, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-105">To create working samples that use SQLXMLOLEDB 4.0, you must do the following:</span></span>  
  
1.  <span data-ttu-id="7ebcc-106">Создать приложение Microsoft Visual Basic и добавить одну из следующих ссылок.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-106">Create a Microsoft Visual Basic .exe application and add one of the following references:</span></span>  
  
    -   <span data-ttu-id="7ebcc-107">Библиотека Microsoft объекты данных ActiveX 2,6</span><span class="sxs-lookup"><span data-stu-id="7ebcc-107">Microsoft ActiveX Data Objects 2.6 Library</span></span>  
  
    -   <span data-ttu-id="7ebcc-108">Библиотека Microsoft объекты данных ActiveX 2,7</span><span class="sxs-lookup"><span data-stu-id="7ebcc-108">Microsoft ActiveX Data Objects 2.7 Library</span></span>  
  
    -   <span data-ttu-id="7ebcc-109">Библиотека объектов Microsoft ADO 2.8</span><span class="sxs-lookup"><span data-stu-id="7ebcc-109">Microsoft ActiveX Data Objects 2.8 Library</span></span>  
  
2.  <span data-ttu-id="7ebcc-110">Развернуть и установить SQLXML версии 4.0 и собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ebcc-110">Deploy and install SQLXML 4.0 and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
     <span data-ttu-id="7ebcc-111">Дополнительные сведения см. в статье [Основные понятия программирования SQLXML 4,0](../../sqlxml/sqlxml-4-0-programming-concepts.md) и [Установка SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="7ebcc-111">For more information, see on [SQLXML 4.0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ebcc-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7ebcc-112">In This Section</span></span>  
 [<span data-ttu-id="7ebcc-113">Запуск запросов SQL &#40;поставщика SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcc-113">Executing SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="7ebcc-114">Демонстрирует использование свойств Клиентсидексмл и корня XML для выполнения SQL-запросов.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-114">Illustrates the use of the ClientSideXML and xml root properties to execute SQL queries.</span></span>  
  
 [<span data-ttu-id="7ebcc-115">Запуск шаблонов, содержащих запросы SQL &#40;поставщика SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcc-115">Executing Templates That Contain SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="7ebcc-116">Иллюстрирует использование свойства Клиентсидексмл.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-116">Illustrates the use of the ClientSideXML property.</span></span>  
  
 [<span data-ttu-id="7ebcc-117">Выполняются запросы XPath &#40;поставщика SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcc-117">Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="7ebcc-118">Демонстрирует использование свойств Клиентсидексмл, базового пути и схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-118">Illustrates the use of the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="7ebcc-119">Выполнять запросы XPath с пространствами имен &#40;поставщик SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcc-119">Executing XPath Queries with Namespaces &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-with-namespaces-sqlxmloledb-provider.md)  
 <span data-ttu-id="7ebcc-120">Иллюстрирует выполнение запроса к схемам пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-120">Illustrates how to query against namespace-qualified schemas.</span></span>  
  
 [<span data-ttu-id="7ebcc-121">Запуск шаблонов, содержащих запросы XPath &#40;поставщика SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcc-121">Executing Templates That Contain XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="7ebcc-122">Показывает, как выполнять шаблоны с запросами SQL с помощью Клиентсидексмл, базового пути и свойств схемы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-122">Illustrates how to execute templates with SQL queries using the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="7ebcc-123">Применение преобразования XSL &#40;поставщика SQLXMLOLEDB&#41;</span><span class="sxs-lookup"><span data-stu-id="7ebcc-123">Applying an XSL Transformation &#40;SQLXMLOLEDB Provider&#41;</span></span>](applying-an-xsl-transformation-sqlxmloledb-provider.md)  
 <span data-ttu-id="7ebcc-124">Демонстрирует использование свойств Клиентсидексмл и XSL в применении преобразования XSL.</span><span class="sxs-lookup"><span data-stu-id="7ebcc-124">Illustrates the use of the ClientSideXML and xsl properties in applying an XSL transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebcc-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ebcc-125">See Also</span></span>  
 [<span data-ttu-id="7ebcc-126">Системные требования для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ebcc-126">System Requirements for SQL Server Native Client</span></span>](../../native-client/system-requirements-for-sql-server-native-client.md)  
  
  
