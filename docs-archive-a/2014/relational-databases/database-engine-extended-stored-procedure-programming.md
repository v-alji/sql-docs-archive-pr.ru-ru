---
title: Программирование расширенных хранимых процедур ядра СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], programming
- stored procedures [SQL Server], extended
- Database Engine [SQL Server], stored procedures
- macros [SQL Server]
- Extended Stored Procedure API [SQL Server]
ms.assetid: 158a6765-0542-4e84-b5ab-f173d946ef5e
author: rothja
ms.author: jroth
ms.openlocfilehash: fecb8f996ddfcaede83cdb330e9c82bffdce5819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668381"
---
# <a name="database-engine-extended-stored-procedure-programming"></a><span data-ttu-id="9e0b6-102">Программирование расширенных хранимых процедур ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="9e0b6-102">Database Engine Extended Stored Procedure Programming</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9e0b6-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-103">Use CLR Integration instead.</span></span> <span data-ttu-id="9e0b6-104">Дополнительные сведения см. в статье [Основные понятия о программировании интеграции со средой CLR](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="9e0b6-104">For more information, see [Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span></span>  
  
 <span data-ttu-id="9e0b6-105">[!INCLUDE[msCoName](../includes/msconame-md.md)]API расширенных хранимых процедур предоставляет серверный интерфейс прикладного программирования (API) для расширения [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Extended Stored Procedure API provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="9e0b6-106">API-интерфейс состоит из функций на языках C и C++ и макросов, предназначенных для построения приложений следующих категорий: расширенные хранимые процедуры и шлюзовые приложения.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-106">The API consists of C and C++ functions and macros used to build applications in the following categories: extended stored procedures and gateway applications.</span></span>  
  
 <span data-ttu-id="9e0b6-107">Расширенные хранимые процедуры позволяют создавать собственные внешние подпрограммы на языках программирования, подобных C. Расширенные хранимые процедуры представляются пользователям как обычные хранимые процедуры и выполняются тем же способом.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-107">Extended stored procedures allow you to create your own external routines in a programming language such as C. The extended stored procedures appear to users as typical stored procedures and are executed in the same way.</span></span> <span data-ttu-id="9e0b6-108">Расширенным хранимым процедурам могут передаваться аргументы, и эти процедуры могут возвращать результаты и статус.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-108">Parameters can be passed to extended stored procedures, and they can return results and return status.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e0b6-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="9e0b6-109">In This Section</span></span>  
 [<span data-ttu-id="9e0b6-110">Программирование расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="9e0b6-110">Programming Extended Stored Procedures</span></span>](extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)  
 <span data-ttu-id="9e0b6-111">Содержит описание способов создания, управления и использования расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-111">Explains how to create, manage, and use extended stored procedures.</span></span>  
  
 [<span data-ttu-id="9e0b6-112">Справочник по программированию расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="9e0b6-112">Extended Stored Procedures Programmer's Reference</span></span>](extended-stored-procedures-reference/database-engine-extended-stored-procedures-reference.md)  
 <span data-ttu-id="9e0b6-113">Содержит разделы справки по API расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="9e0b6-113">Contains reference topics for the Extended Stored Procedure API.</span></span>  
  
  
