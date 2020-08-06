---
title: Определяемые пользователем функции CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
author: rothja
ms.author: jroth
ms.openlocfilehash: ba7a4a983ec0cb36ef0fd79df44491f7f23f7648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666668"
---
# <a name="clr-user-defined-functions"></a><span data-ttu-id="cd355-102">Определяемые пользователем функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="cd355-102">CLR User-Defined Functions</span></span>
  <span data-ttu-id="cd355-103">Определяемые пользователем функции представляют собой подпрограммы, которые могут принимать параметры, выполнять вычисления или другие действия и возвращать результат.</span><span class="sxs-lookup"><span data-stu-id="cd355-103">User-defined functions are routines that can take parameters, perform calculations or other actions, and return a result.</span></span> <span data-ttu-id="cd355-104">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], определяемую пользователем функцию можно написать на любом языке программирования платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, например на [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET или [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="cd355-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can write user-defined functions in any [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework programming language, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="cd355-105">Существует два типа функций: скалярные, возвращающие одно значение, и табличные, возвращающие набор значений.</span><span class="sxs-lookup"><span data-stu-id="cd355-105">There are two types of functions: scalar, which returns a single value, and table-valued, which returns a set of rows.</span></span>  
  
 <span data-ttu-id="cd355-106">В следующей таблице приводится список подразделов данного раздела.</span><span class="sxs-lookup"><span data-stu-id="cd355-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="cd355-107">Скалярные функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="cd355-107">CLR Scalar-Valued Functions</span></span>](clr-scalar-valued-functions.md)  
 <span data-ttu-id="cd355-108">Приводит сведения о требованиях реализации и примеры скалярных функций.</span><span class="sxs-lookup"><span data-stu-id="cd355-108">Covers implementation requirements and examples of scalar-valued functions.</span></span>  
  
 [<span data-ttu-id="cd355-109">Функции среды CLR с табличным значением</span><span class="sxs-lookup"><span data-stu-id="cd355-109">CLR Table-Valued Functions</span></span>](clr-table-valued-functions.md)  
 <span data-ttu-id="cd355-110">Объясняет реализацию и использование функций с табличным значением (TVF), а также разницу между возвращающими табличные значения функциями в [!INCLUDE[tsql](../../includes/tsql-md.md)] и в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="cd355-110">Discusses how to implement and use table-valued functions (TVFs), as well as differences between [!INCLUDE[tsql](../../includes/tsql-md.md)] and common language runtime (CLR) TVFs.</span></span>  
  
 [<span data-ttu-id="cd355-111">Пользовательские агрегатные функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="cd355-111">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
 <span data-ttu-id="cd355-112">Объясняет реализацию и использование определяемых пользователем статистических функций.</span><span class="sxs-lookup"><span data-stu-id="cd355-112">Describes how to implement and use user-defined aggregates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd355-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd355-113">See Also</span></span>  
 [<span data-ttu-id="cd355-114">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="cd355-114">User-Defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)  
  
  
