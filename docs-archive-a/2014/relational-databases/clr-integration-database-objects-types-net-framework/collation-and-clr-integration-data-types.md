---
title: Параметры сортировки и типы данных интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data types [CLR integration]
- parameter collation [CLR integration]
- collations [CLR integration]
ms.assetid: 6ebaed8e-2e2b-4f6d-bf4b-bc25452de441
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a5b0367487aeb80355b8c5c976818e1b6c1ac04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751184"
---
# <a name="collation-and-clr-integration-data-types"></a><span data-ttu-id="c0ffd-102">Параметры сортировки и типы данных интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="c0ffd-102">Collation and CLR Integration Data Types</span></span>
  <span data-ttu-id="c0ffd-103">В [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] объект `CompareInfo` обрабатывает параметры сортировки.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-103">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], the `CompareInfo` object handles collations.</span></span> <span data-ttu-id="c0ffd-104">Строковые API-интерфейсы платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] используют свойство `CompareInfo`, связанное с объектом `CultureInfo` текущего потока, для сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-104">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] string application programming interfaces (APIs) use the `CompareInfo` property associated with the `CultureInfo` object of the current thread to perform string comparisons.</span></span> <span data-ttu-id="c0ffd-105">Значение по умолчанию для `CultureInfo` объекта основано на [!INCLUDE[msCoName](../../includes/msconame-md.md)] параметрах локали Windows для компьютера, на котором [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-105">The default setting of the `CultureInfo` object is based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows locale setting for the computer on which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="c0ffd-106">Она определяет семантику сравнения по умолчанию для сравнения значений типа `CultureInfo`, если свойство `System.String` не задано явно.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-106">This determines the default comparison semantics, if no explicit `CultureInfo` is specified, for comparisons of `System.String` values.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0ffd-107">не изменяет явно свойство `CompareInfo` на параметры сортировки базы данных или сервера.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-107">does not explicitly change the `CompareInfo` property to the database or server collation.</span></span> <span data-ttu-id="c0ffd-108">При необходимости пользователи должны самостоятельно устанавливать свойство `CompareInfo` в своих программах.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-108">If required, users must set the appropriate `CompareInfo` property in their routines.</span></span>  
  
## <a name="parameter-collation"></a><span data-ttu-id="c0ffd-109">Параметр с параметрами сортировки</span><span class="sxs-lookup"><span data-stu-id="c0ffd-109">Parameter Collation</span></span>  
 <span data-ttu-id="c0ffd-110">При создании программы CLR, если параметр метода CLR, связанного с программой, имеет тип `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создает экземпляр параметра с параметрами сортировки по умолчанию базы данных, содержащей вызывающую программу.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-110">When you create a common language runtime (CLR) routine, and a parameter of a CLR method bound to the routine is of type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an instance of the parameter with the default collation of the database containing the calling routine.</span></span> <span data-ttu-id="c0ffd-111">Если параметр имеет тип, отличный от `SqlType` (например, `String`, а не `SQLString`), сведения о параметрах сортировки из базы данных с этим параметром не связываются.</span><span class="sxs-lookup"><span data-stu-id="c0ffd-111">If a parameter is not a `SqlType` (for example, `String` rather than `SQLString`), the collation information from the database is not associated with the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ffd-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0ffd-112">See Also</span></span>  
 [<span data-ttu-id="c0ffd-113">Типы данных SQL Server в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0ffd-113">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
