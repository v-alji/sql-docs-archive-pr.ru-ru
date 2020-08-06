---
title: SQL Server ADO.NET в процессе конкретных расширений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
ms.openlocfilehash: 37d8aedc1d8f93739c2e9386665adfc67b43e312
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668388"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a><span data-ttu-id="31c35-102">Внутрипроцессные расширения SQL Server для ADO.NET</span><span class="sxs-lookup"><span data-stu-id="31c35-102">SQL Server In-Process Specific Extensions to ADO.NET</span></span>
  <span data-ttu-id="31c35-103">Существует четыре основных функциональных расширения для ADO.NET, которые специально предназначены для внутрипроцессного использования.</span><span class="sxs-lookup"><span data-stu-id="31c35-103">There are four main functional extensions to ADO.NET that are specifically for in-process use.</span></span> <span data-ttu-id="31c35-104">Эти расширения подробно рассматриваются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="31c35-104">The following topics will cover these extensions in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31c35-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="31c35-105">In This Section</span></span>  
 [<span data-ttu-id="31c35-106">Объект SqlContext</span><span class="sxs-lookup"><span data-stu-id="31c35-106">SqlContext Object</span></span>](sqlcontext-object.md)  
 <span data-ttu-id="31c35-107">Этот класс предоставляет доступ к другим расширениям, абстрагируя контекст вызывающего объекта процедуры SQL Server, которая выполняет управляемый внутрипроцессный код.</span><span class="sxs-lookup"><span data-stu-id="31c35-107">This class provides access to the other extensions by abstracting the context of a caller of a SQL Server routine that executes managed code in-process.</span></span>  
  
 [<span data-ttu-id="31c35-108">Объект SqlPipe</span><span class="sxs-lookup"><span data-stu-id="31c35-108">SqlPipe Object</span></span>](sqlpipe-object.md)  
 <span data-ttu-id="31c35-109">Этот класс содержит процедуры для отправки табличных результатов и сообщений клиенту.</span><span class="sxs-lookup"><span data-stu-id="31c35-109">This class contains routines to send tabular results and messages to the client.</span></span>  
  
 [<span data-ttu-id="31c35-110">SqlTriggerContext, объект</span><span class="sxs-lookup"><span data-stu-id="31c35-110">SqlTriggerContext Object</span></span>](sqltriggercontext-object.md)  
 <span data-ttu-id="31c35-111">Этот класс предоставляет сведения о контексте, в котором выполняется триггер.</span><span class="sxs-lookup"><span data-stu-id="31c35-111">This class provides information on the context in which a trigger is run.</span></span>  
  
 [<span data-ttu-id="31c35-112">Объект SqlDataRecord</span><span class="sxs-lookup"><span data-stu-id="31c35-112">SqlDataRecord Object</span></span>](sqldatarecord-object.md)  
 <span data-ttu-id="31c35-113">Класс SqlDataRecord представляет одну строку данных вместе со связанными с ней метаданными, позволяя хранимым процедурам возвращать клиенту пользовательские результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="31c35-113">The SqlDataRecord class represents a single row of data, along with its related metadata, and allows stored procedures to return custom result sets to the client.</span></span>  
  
  
