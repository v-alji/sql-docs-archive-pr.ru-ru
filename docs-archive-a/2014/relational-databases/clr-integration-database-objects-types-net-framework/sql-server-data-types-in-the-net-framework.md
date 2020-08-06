---
title: SQL Server типы данных в .NET Framework | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- System.Data library
- System.Data.SqlTypes namespace
- data types [CLR integration]
- SqlTypes library
- database objects [CLR integration], data types
- common language runtime [SQL Server], data types
- building database objects [CLR integration], data types
- mapping data types [CLR integration]
ms.assetid: c70d3ffe-2c32-45a5-849b-ef113dda09b9
author: rothja
ms.author: jroth
ms.openlocfilehash: fe0ed680e7050c58738301256575e4138f21276f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751168"
---
# <a name="sql-server-data-types-in-the-net-framework"></a><span data-ttu-id="da949-102">Типы данных SQL Server в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da949-102">SQL Server Data Types in the .NET Framework</span></span>
  <span data-ttu-id="da949-103">Библиотека `SqlTypes` представляет собой часть библиотеки базового класса платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da949-103">The `SqlTypes` library is part of the base class library of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="da949-104">Она предоставляет типы данных с той же семантикой и той же точностью, как те, что доступны в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da949-104">It is designed to provide data types with the same semantics and precision as those found in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="da949-105">Данный раздел предоставляет сведения о новой семантике для программистов, работающих на платформе .NET Framework, и описывает типы, реализованные в пространстве имен `System.Data.SqlTypes`, включенном в библиотеку `System.Data`.</span><span class="sxs-lookup"><span data-stu-id="da949-105">This topic describes the new semantics to .NET Framework programmers, and introduces the types implemented in the `System.Data.SqlTypes` namespace that is included in the `System.Data` library.</span></span>  
  
 <span data-ttu-id="da949-106">В следующей таблице перечислены подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="da949-106">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="da949-107">Допустимость значений NULL и трехзначная логика сравнения</span><span class="sxs-lookup"><span data-stu-id="da949-107">Nullability and Three-Value Logic Comparisons</span></span>](nullability-and-three-value-logic-comparisons.md)  
 <span data-ttu-id="da949-108">Описывает работу со значениями NULL в различных типах данных при интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="da949-108">Discusses how NULL values are handled with common language runtime (CLR) integration data types.</span></span>  
  
 [<span data-ttu-id="da949-109">Параметры сортировки и типы данных интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="da949-109">Collation and CLR Integration Data Types</span></span>](collation-and-clr-integration-data-types.md)  
 <span data-ttu-id="da949-110">Описывает обработку параметров сортировки при интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="da949-110">Describes how collations are handled with CLR integration.</span></span>  
  
 [<span data-ttu-id="da949-111">Обработка больших объектов &#40;бизнес-&#41; параметров в CLR</span><span class="sxs-lookup"><span data-stu-id="da949-111">Handling Large Object &#40;LOB&#41; Parameters in the CLR</span></span>](handling-large-object-lob-parameters-in-the-clr.md)  
 <span data-ttu-id="da949-112">Описывает передачу типов LOB между [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и средой CLR.</span><span class="sxs-lookup"><span data-stu-id="da949-112">Describes how to pass LOB types between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the CLR.</span></span>  
  
 [<span data-ttu-id="da949-113">Сопоставление данных о параметрах CLR</span><span class="sxs-lookup"><span data-stu-id="da949-113">Mapping CLR Parameter Data</span></span>](mapping-clr-parameter-data.md)  
 <span data-ttu-id="da949-114">Описывает сопоставления типов данных между [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], интеграцией со средой CLR и платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da949-114">Shows data type mappings between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], CLR integration, and the .NET Framework.</span></span>  
  
  
