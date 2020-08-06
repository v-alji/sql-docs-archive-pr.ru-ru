---
title: Использование дельтами для изменения данных в SQLXML 4,0 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- data deletions [SQLXML]
- updating data [SQLXML]
- DiffGrams [SQLXML]
- modifying data [SQLXML]
- .NET Framework [SQLXML], DiffGrams
- XML [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- data modifications [SQLXML]
- record insertion [SQLXML]
- SQLXML, DiffGrams
- deleting data
- record updates [SQLXML]
- record deletions [SQLXML]
ms.assetid: 48b8a8f9-f3af-404f-8c84-f4c3703364d9
author: rothja
ms.author: jroth
ms.openlocfilehash: cc2e24304679a7648f18148eb45f33b9bf719a9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664806"
---
# <a name="using-diffgrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="9a794-102">Использование дельт для изменения данных в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="9a794-102">Using DiffGrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="9a794-103">Формат DiffGram появился в компоненте **набора данных** [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a794-103">The DiffGram format is introduced in the **DataSet** component of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="9a794-104">На платформе .NET Framework можно создать дельты и использовать их для изменения данных в таблицах в базах данных Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a794-104">Within the .NET Framework, you can create DiffGrams and use them to modify data in tables in a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a794-105">Этот раздел содержит краткие сведения о дельтах и примеры их использования.</span><span class="sxs-lookup"><span data-stu-id="9a794-105">This section provides a brief introduction to DiffGrams and examples of how to use them.</span></span> <span data-ttu-id="9a794-106">Предполагается знакомство с дельтами на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a794-106">It is assumed that you are familiar with DiffGrams in the .NET Framework.</span></span> <span data-ttu-id="9a794-107">В этой документации основное внимание уделяется проблемам формата дельт, специфичным для SQLXML.</span><span class="sxs-lookup"><span data-stu-id="9a794-107">In this documentation, the primary focus is on DiffGram issues that are specific to SQLXML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a794-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="9a794-108">In This Section</span></span>  
 [<span data-ttu-id="9a794-109">Введение в работу с дельтами в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="9a794-109">Introduction to DiffGrams in SQLXML 4.0</span></span>](introduction-to-diffgrams-in-sqlxml-4-0.md)  
 <span data-ttu-id="9a794-110">Предоставляет основные сведения о дельтах.</span><span class="sxs-lookup"><span data-stu-id="9a794-110">Provides basic information about Diffgrams.</span></span>  
  
 [<span data-ttu-id="9a794-111">Примеры DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9a794-111">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
 <span data-ttu-id="9a794-112">Предоставляет примеры использования дельт.</span><span class="sxs-lookup"><span data-stu-id="9a794-112">Provides examples of using Diffgrams.</span></span>  
  
 [<span data-ttu-id="9a794-113">Запуск DiffGram с помощью ADO &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9a794-113">Executing a DiffGram by Using ADO &#40;SQLXML 4.0&#41;</span></span>](executing-a-diffgram-by-using-ado-sqlxml-4-0.md)  
 <span data-ttu-id="9a794-114">Предоставляет пример выполнения дельты с объектами ADO.</span><span class="sxs-lookup"><span data-stu-id="9a794-114">Provides an example of executing a Diffgram with ActiveX Data Objects (ADO).</span></span>  
  
 [<span data-ttu-id="9a794-115">Выполнение дельты с использованием управляемых классов SQLXML</span><span class="sxs-lookup"><span data-stu-id="9a794-115">Executing a DiffGram by Using SQLXML Managed Classes</span></span>](../net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="9a794-116">Предоставляет пример выполнения дельты с управляемыми классами SQLXML.</span><span class="sxs-lookup"><span data-stu-id="9a794-116">Provides an example of executing a Diffgram with SQLXML Managed Classes.</span></span>  
  
  
