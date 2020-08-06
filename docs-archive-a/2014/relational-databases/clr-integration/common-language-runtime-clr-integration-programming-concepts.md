---
title: Основные понятия программирования интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- CLR [SQL Server] See common language runtime [SQL Server]
- Database Engine [SQL Server], .NET Framework
- .NET Framework [SQL Server], Database Engine programming
- common language runtime [SQL Server]
- .NET Framework [SQL Server]
ms.assetid: 951bf851-3e6e-4361-ae6a-2bcd5b837ebd
author: rothja
ms.author: jroth
ms.openlocfilehash: 38323b0145132ad60d59c001d5147a7d19942462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658300"
---
# <a name="common-language-runtime-clr-integration-programming-concepts"></a><span data-ttu-id="d36db-102">Основные понятия о программировании интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-102">Common Language Runtime (CLR) Integration Programming Concepts</span></span>
  <span data-ttu-id="d36db-103">Начиная с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] обеспечивает интеграцию с компонентами CLR платформы .NET Framework для [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d36db-103">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="d36db-104">Это означает, что хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции, определяемые пользователем статистические функции и возвращающие табличные значение потоковые функции теперь могут разрабатываться с использованием любого языка .NET Framework, включая [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET и [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d36db-104">This means that you can now write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="d36db-105">Пространство имен Microsoft.SqlServer.Server содержит основные возможности программирования CLR для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36db-105">The Microsoft.SqlServer.Server namespace includes core functionality for CLR programming in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d36db-106">Однако пространство имен Microsoft.SqlServer.Server документировано в пакете .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="d36db-106">However, the Microsoft.SqlServer.Server namespace is documented in the .NET Framework SDK.</span></span> <span data-ttu-id="d36db-107">Эта документация не включена в электронную документацию по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36db-107">This documentation is not included in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d36db-108">По умолчанию платформа .NET Framework устанавливается вместе с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], но пакет .NET Framework SDK в эту установку не включен.</span><span class="sxs-lookup"><span data-stu-id="d36db-108">By default, the .NET Framework is installed with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but the .NET Framework SDK is not.</span></span> <span data-ttu-id="d36db-109">Если пакет SDK установлен на рабочем компьютере и не добавлен к коллекции электронной документации, то ссылки на содержимое пакета SDK, имеющиеся в этом разделе, работать не будут.</span><span class="sxs-lookup"><span data-stu-id="d36db-109">Without the SDK installed on your computer and included in the Books Online collection, links to SDK content in this section do not work.</span></span> <span data-ttu-id="d36db-110">Установите пакет .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="d36db-110">Install the .NET Framework SDK.</span></span> <span data-ttu-id="d36db-111">После установки добавьте пакет SDK в коллекцию электронной документации и оглавление, следуя инструкциям в разделе [Установка пакета SDK для .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d36db-111">Once installed, add the SDK to the Books Online collection and table of contents by following the instructions in [Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span></span>  
  
 <span data-ttu-id="d36db-112">В следующей таблице приводится список подразделов данного раздела.</span><span class="sxs-lookup"><span data-stu-id="d36db-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="d36db-113">Общие сведения об интеграции&#41; среды CLR &#40;</span><span class="sxs-lookup"><span data-stu-id="d36db-113">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](common-language-runtime-integration-overview.md)  
 <span data-ttu-id="d36db-114">Содержит общие сведения о среде CLR и описывает способы и преимущества использования технологии в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36db-114">Provides a brief overview of the CLR, and describes how and why this technology has been used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d36db-115">Описывает преимущества использования среды CLR для создания объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="d36db-115">Describes the benefits of using the CLR to create database objects.</span></span>  
  
 [<span data-ttu-id="d36db-116">Сборки (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="d36db-116">Assemblies &#40;Database Engine&#41;</span></span>](assemblies-database-engine.md)  
 <span data-ttu-id="d36db-117">Описывает использование в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] сборок для развертывания функций, хранимых процедур, триггеров, пользовательских статистических функций и определяемых пользователем типов данных, написанных на одном из языков управляемого кода, поддерживаемых средой CLR [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework, а не на языке [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36db-117">Describes how assemblies are used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework common language runtime (CLR), and not written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 [<span data-ttu-id="d36db-118">Создание объектов базы данных с помощью среды CLR &#40;интеграция&#41; CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-118">Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration</span></span>](database-objects/building-database-objects-with-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="d36db-119">Описывает виды объектов, которые можно строить с использованием среды CLR, и рассматривает требования к построению объектов баз данных CLR.</span><span class="sxs-lookup"><span data-stu-id="d36db-119">Describes the kinds of objects that can be built using the CLR, and reviews the requirements for building CLR database objects.</span></span>  
  
 [<span data-ttu-id="d36db-120">Доступ к данным из объектов среды CLR для работы с базами данных</span><span class="sxs-lookup"><span data-stu-id="d36db-120">Data Access from CLR Database Objects</span></span>](data-access/data-access-from-clr-database-objects.md)  
 <span data-ttu-id="d36db-121">Описывает, как подпрограмма CLR может обращаться к данным, хранящимся в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36db-121">Describes how a CLR routine can access data stored in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d36db-122">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-122">CLR Integration Security</span></span>](security/clr-integration-security.md)  
 <span data-ttu-id="d36db-123">Описывает модель безопасности для средств интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="d36db-123">Describes the CLR integration security model.</span></span>  
  
 [<span data-ttu-id="d36db-124">Отладка объектов базы данных среды CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-124">Debugging CLR Database Objects</span></span>](debugging-clr-database-objects.md)  
 <span data-ttu-id="d36db-125">Описывает ограничения и требования для отладки объектов базы данных CLR.</span><span class="sxs-lookup"><span data-stu-id="d36db-125">Describes limitations of and requirements for debugging CLR database objects.</span></span>  
  
 [<span data-ttu-id="d36db-126">Развертывание объектов базы данных CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-126">Deploying CLR Database Objects</span></span>](deploying-clr-database-objects.md)  
 <span data-ttu-id="d36db-127">Описывает развертывание сборок на рабочих серверах.</span><span class="sxs-lookup"><span data-stu-id="d36db-127">Describes deploying assemblies to production servers.</span></span>  
  
 [<span data-ttu-id="d36db-128">Управление сборками интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-128">Managing CLR Integration Assemblies</span></span>](assemblies/managing-clr-integration-assemblies.md)  
 <span data-ttu-id="d36db-129">Описывает способы создания и удаления сборок интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="d36db-129">Describes how to create and drop CLR integration assemblies.</span></span>  
  
 [<span data-ttu-id="d36db-130">Наблюдение и устранение неполадок в управляемых объектах базы данных</span><span class="sxs-lookup"><span data-stu-id="d36db-130">Monitoring and Troubleshooting Managed Database Objects</span></span>](monitoring-and-troubleshooting-managed-database-objects.md)  
 <span data-ttu-id="d36db-131">Данный раздел содержит информацию о средствах, которые можно использовать для наблюдения и диагностики управляемых объектов базы данных и сборок, работающих в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36db-131">Provides information about the tools that can be used to monitor and troubleshoot managed database objects and assemblies running in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d36db-132">Сценарии использования и примеры интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="d36db-132">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="d36db-133">Описывает сценарии использования и образцы кода, использующие объекты CLR.</span><span class="sxs-lookup"><span data-stu-id="d36db-133">Describes usage scenarios and code samples using CLR objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36db-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="d36db-134">See Also</span></span>  
 <span data-ttu-id="d36db-135">[Сборки &#40;ядро СУБД&#41;](assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d36db-135">[Assemblies &#40;Database Engine&#41;](assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="d36db-136">[Установка пакета SDK платформы .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d36db-136">[Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span></span>  
  
  
