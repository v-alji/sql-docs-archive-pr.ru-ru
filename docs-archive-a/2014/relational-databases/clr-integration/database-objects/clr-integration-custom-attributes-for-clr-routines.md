---
title: Пользовательские атрибуты подпрограмм среды CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- SqlFacet attribute
- SqlTrigger attribute
- SqlProcedure attribute
- custom attributes [CLR integration]
- SqlUserDefinedAggregate attribute
- attributes [CLR integration]
- SqlMethod attribute
- SqlFunction attribute
- common language runtime [SQL Server], attributes
- SqlUserDefinedTypeAttribute attribute
ms.assetid: 95069d22-b05d-4670-b053-15ee2a664e33
author: rothja
ms.author: jroth
ms.openlocfilehash: 058bbec7f0f1f63fbd96258a0abe7a6c3d543d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654349"
---
# <a name="custom-attributes-for-clr-routines"></a><span data-ttu-id="63b3c-102">Пользовательские атрибуты для процедур CLR</span><span class="sxs-lookup"><span data-stu-id="63b3c-102">Custom Attributes for CLR Routines</span></span>
  <span data-ttu-id="63b3c-103">Перечисленные атрибуты можно применять к подсредам среды CLR, определяемым пользователем типам и определяемым пользователем статистическим функциям, зарегистрированным в [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63b3c-103">The attributes listed can be applied to common language runtime (CLR) routines, user-defined types, and user-defined aggregates that are registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="63b3c-104">Если атрибут не применен, то [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предполагает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="63b3c-104">If the attribute is not applied, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumes the default value.</span></span> <span data-ttu-id="63b3c-105">Перечисленные атрибуты определены в пространстве имен `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="63b3c-105">The attributes listed are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="the-sqluserdefinedaggregate-attribute"></a><span data-ttu-id="63b3c-106">Атрибут SqlUserDefinedAggregate</span><span class="sxs-lookup"><span data-stu-id="63b3c-106">The SqlUserDefinedAggregate Attribute</span></span>  
 <span data-ttu-id="63b3c-107">Атрибут `SqlUserDefinedAggregate` указывает, что метод должен быть зарегистрирован как пользовательское статистическое выражение.</span><span class="sxs-lookup"><span data-stu-id="63b3c-107">The `SqlUserDefinedAggregate` attribute indicates that the method should be registered as a user-defined aggregate.</span></span> <span data-ttu-id="63b3c-108">Каждое пользовательское статистическое выражение должно иметь этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="63b3c-108">Every user-defined aggregate must be annotated with this attribute.</span></span>  
  
 <span data-ttu-id="63b3c-109">Дополнительные сведения см. в разделе [склусердефинедаггрегатеаттрибуте](https://go.microsoft.com/fwlink/?LinkId=124626).</span><span class="sxs-lookup"><span data-stu-id="63b3c-109">For more information, see [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span></span>  
  
## <a name="the-sqlfunction-attribute"></a><span data-ttu-id="63b3c-110">Атрибут SqlFunction</span><span class="sxs-lookup"><span data-stu-id="63b3c-110">The SqlFunction Attribute</span></span>  
 <span data-ttu-id="63b3c-111">Атрибут `SqlFunction` указывает, что метод должен быть зарегистрирован как функция, с соответствующим функции набором атрибутов.</span><span class="sxs-lookup"><span data-stu-id="63b3c-111">The `SqlFunction` attribute indicates the method should be registered as a function, with the appropriate function attributes set.</span></span>  
  
 <span data-ttu-id="63b3c-112">Дополнительные сведения см. в разделе [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span><span class="sxs-lookup"><span data-stu-id="63b3c-112">For more information, see [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span></span>  
  
## <a name="the-sqlfacet-attribute"></a><span data-ttu-id="63b3c-113">Атрибут SqlFacet</span><span class="sxs-lookup"><span data-stu-id="63b3c-113">The SqlFacet Attribute</span></span>  
 <span data-ttu-id="63b3c-114">Атрибут `SqlFacet` позволяет получить сведения о возвращаемом типе выражения определяемого пользователем типа данных.</span><span class="sxs-lookup"><span data-stu-id="63b3c-114">The `SqlFacet` attribute is used to return information about the return type of a user-defined type (UDT) expression.</span></span>  
  
 <span data-ttu-id="63b3c-115">Дополнительные сведения см. в разделе [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span><span class="sxs-lookup"><span data-stu-id="63b3c-115">For more information, see [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span></span>  
  
## <a name="the-sqlprocedure-attribute"></a><span data-ttu-id="63b3c-116">Атрибут SqlProcedure</span><span class="sxs-lookup"><span data-stu-id="63b3c-116">The SqlProcedure Attribute</span></span>  
 <span data-ttu-id="63b3c-117">Атрибут `SqlProcedure` указывает, что метод должен быть зарегистрирован как хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="63b3c-117">The `SqlProcedure` attribute indicates the method should be registered as a stored procedure.</span></span> <span data-ttu-id="63b3c-118">Этот атрибут используется только в среде Visual Studio для автоматической регистрации указанного метода как хранимой процедуры. В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не используется.</span><span class="sxs-lookup"><span data-stu-id="63b3c-118">This attribute is used only by Visual Studio to register the specified method as a stored procedure automatically; it is not used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="63b3c-119">Дополнительные сведения см. в разделе [склпроцедуреаттрибуте](https://go.microsoft.com/fwlink/?LinkId=128021).</span><span class="sxs-lookup"><span data-stu-id="63b3c-119">For more information, see [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span></span>  
  
## <a name="the-sqltrigger-attribute"></a><span data-ttu-id="63b3c-120">Атрибут SqlTrigger</span><span class="sxs-lookup"><span data-stu-id="63b3c-120">The SqlTrigger Attribute</span></span>  
 <span data-ttu-id="63b3c-121">Атрибут `SqlTrigger` указывает, что метод должен быть зарегистрирован как триггер.</span><span class="sxs-lookup"><span data-stu-id="63b3c-121">The `SqlTrigger` attribute indicates the method should be registered as a trigger.</span></span>  
  
 <span data-ttu-id="63b3c-122">Дополнительные сведения см. в разделе [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) и [склтригжераттрибуте](https://go.microsoft.com/fwlink/?LinkId=203898).</span><span class="sxs-lookup"><span data-stu-id="63b3c-122">For more information, see [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) and [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span></span>  
  
## <a name="the-sqluserdefinedtypeattribute"></a><span data-ttu-id="63b3c-123">SqlUserDefinedTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="63b3c-123">The SqlUserDefinedTypeAttribute</span></span>  
 <span data-ttu-id="63b3c-124">К определению класса в сборке можно применить SqlUserDefinedTypeAttribute.</span><span class="sxs-lookup"><span data-stu-id="63b3c-124">You can apply the SqlUserDefinedTypeAttribute to a class definition in the assembly.</span></span> <span data-ttu-id="63b3c-125">В результате этого [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] создает определяемый пользователем тип, привязанный к определению класса с этим пользовательским атрибутом.</span><span class="sxs-lookup"><span data-stu-id="63b3c-125">It causes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to create a user-defined type that is bound to the class definition which has this custom attribute.</span></span>  
  
 <span data-ttu-id="63b3c-126">Дополнительные сведения см. в разделе [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span><span class="sxs-lookup"><span data-stu-id="63b3c-126">For more information, see [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span></span>  
  
## <a name="the-sqlmethod-attribute"></a><span data-ttu-id="63b3c-127">Атрибут SqlMethod</span><span class="sxs-lookup"><span data-stu-id="63b3c-127">The SqlMethod Attribute</span></span>  
 <span data-ttu-id="63b3c-128">Атрибут `SqlMethod` позволяет определить детерминированность и свойства доступа к данным метода или свойства определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="63b3c-128">The `SqlMethod` attribute is used to indicate the determinism and data access properties of a method or a property on a UDT.</span></span>  
  
 <span data-ttu-id="63b3c-129">Дополнительные сведения см. в разделе [склмесодаттрибуте](https://go.microsoft.com/fwlink/?LinkId=128025).</span><span class="sxs-lookup"><span data-stu-id="63b3c-129">For more information, see [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b3c-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="63b3c-130">See Also</span></span>  
 <span data-ttu-id="63b3c-131">[Определяемые пользователем статистические функции CLR](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span><span class="sxs-lookup"><span data-stu-id="63b3c-131">[CLR User-Defined Aggregates](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span></span>  
 <span data-ttu-id="63b3c-132">[Определяемые пользователем функции среды CLR](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="63b3c-132">[CLR User-Defined Functions](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="63b3c-133">[Определяемые пользователем типы CLR](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="63b3c-133">[CLR User-Defined Types](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 <span data-ttu-id="63b3c-134">[Хранимые процедуры CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="63b3c-134">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="63b3c-135">Триггеры CLR</span><span class="sxs-lookup"><span data-stu-id="63b3c-135">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
  
  
