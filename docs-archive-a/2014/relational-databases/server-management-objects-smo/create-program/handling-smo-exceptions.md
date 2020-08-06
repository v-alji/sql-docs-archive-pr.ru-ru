---
title: Обработка исключений SMO | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SMO [SQL Server], exceptions
- exceptions [SMO]
- SQL Server Management Objects, exceptions
- inner exceptions [SMO]
ms.assetid: 4c725ff2-6588-44ca-b86a-87979e164153
author: stevestein
ms.author: sstein
ms.openlocfilehash: f4ae9e475a019c9bf874ee3f8365f3f3ac8e19d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668202"
---
# <a name="handling-smo-exceptions"></a><span data-ttu-id="d9129-102">Обработка исключений SMO</span><span class="sxs-lookup"><span data-stu-id="d9129-102">Handling SMO Exceptions</span></span>
  <span data-ttu-id="d9129-103">В управляемом коде при возникновении ошибок вызываются исключения.</span><span class="sxs-lookup"><span data-stu-id="d9129-103">In managed code, exceptions are thrown when an error occurs.</span></span> <span data-ttu-id="d9129-104">Методы и свойства объектов SMO не сообщают об ошибке или успешном выполнении в возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="d9129-104">SMO methods and properties do not report success or failure in the return value.</span></span> <span data-ttu-id="d9129-105">Исключения могут быть перехвачены и обработаны в обработчике исключений.</span><span class="sxs-lookup"><span data-stu-id="d9129-105">Instead, exceptions can be caught and handled by an exception handler.</span></span>  
  
 <span data-ttu-id="d9129-106">В объектах SMO существуют различные классы исключений.</span><span class="sxs-lookup"><span data-stu-id="d9129-106">Different exception classes exist in the SMO.</span></span> <span data-ttu-id="d9129-107">Сведения об исключении можно извлечь из свойств исключения, таких как свойство `Message`, которое предоставляет текстовое сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="d9129-107">Information about the exception can be extracted from the exception properties such as the `Message` property that gives a text message about the exception.</span></span>  
  
 <span data-ttu-id="d9129-108">Инструкции обработки исключения зависят от конкретного языка программирования.</span><span class="sxs-lookup"><span data-stu-id="d9129-108">The exception handling statements are specific to the programming language.</span></span> <span data-ttu-id="d9129-109">Например, в языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic это инструкция `Catch`.</span><span class="sxs-lookup"><span data-stu-id="d9129-109">For example, in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic it is the `Catch` statement.</span></span>  
  
## <a name="inner-exceptions"></a><span data-ttu-id="d9129-110">Внутренние исключения</span><span class="sxs-lookup"><span data-stu-id="d9129-110">Inner Exceptions</span></span>  
 <span data-ttu-id="d9129-111">Исключения могут быть общими и конкретными.</span><span class="sxs-lookup"><span data-stu-id="d9129-111">Exceptions can either be general or specific.</span></span> <span data-ttu-id="d9129-112">Общие исключения содержат набор конкретных исключений.</span><span class="sxs-lookup"><span data-stu-id="d9129-112">General exceptions contain a set of specific exceptions.</span></span> <span data-ttu-id="d9129-113">Несколько инструкций `Catch` можно использовать, чтобы обработать ожидаемые ошибки и позволить остальным ошибкам пройти через обработку общих исключений.</span><span class="sxs-lookup"><span data-stu-id="d9129-113">Several `Catch` statements can be used to handle anticipated errors and let remaining errors fall through to general exception handling code.</span></span> <span data-ttu-id="d9129-114">Исключения часто происходят в каскадной последовательности.</span><span class="sxs-lookup"><span data-stu-id="d9129-114">Exceptions often occur in a cascading sequence.</span></span> <span data-ttu-id="d9129-115">Часто исключение объекта SMO может быть вызвано исключением SQL.</span><span class="sxs-lookup"><span data-stu-id="d9129-115">Frequently, an SMO exception might have been caused by an SQL exception.</span></span> <span data-ttu-id="d9129-116">Чтобы это обнаружить, можно последовательно использовать свойство `InnerException`, чтобы определить исходное исключение, которое вызвало конечное исключение верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="d9129-116">The way to detect this is to use the `InnerException` property successively to determine the original exception that caused the final, top-level exception.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9129-117">`SQLException`Исключение объявляется в пространстве имен **System. Data. SqlClient** .</span><span class="sxs-lookup"><span data-stu-id="d9129-117">The `SQLException` exception is declared in the **System.Data.SqlClient** namespace.</span></span>  
  
 <span data-ttu-id="d9129-118">![Диаграмма, показывающая уровни, из которых могут вызываться исключения](../../../database-engine/dev-guide/media/exception-flow.gif "Диаграмма, показывающая уровни, из которых могут вызываться исключения")</span><span class="sxs-lookup"><span data-stu-id="d9129-118">![A diagram that shows the levels from which an excp](../../../database-engine/dev-guide/media/exception-flow.gif "A diagram that shows the levels from which an excp")</span></span>  
  
 <span data-ttu-id="d9129-119">Диаграмма показывает поток исключений по уровням приложения.</span><span class="sxs-lookup"><span data-stu-id="d9129-119">The diagram shows the flow of exceptions through the layers of the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9129-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d9129-120">Example</span></span>  
 <span data-ttu-id="d9129-121">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="d9129-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="d9129-122">Дополнительные сведения см. в статьях [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) или [Создание Visual Basic проекта SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="d9129-122">For more information, see [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) or [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="catching-an-exception-in-visual-basic"></a><span data-ttu-id="d9129-123">Перехват исключения на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9129-123">Catching an Exception in Visual Basic</span></span>  
 <span data-ttu-id="d9129-124">В этом примере кода показано, как использовать инструкцию `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] для перехвата исключения объекта SMO.</span><span class="sxs-lookup"><span data-stu-id="d9129-124">This code example shows how to use the `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] statement to catch a SMO exception.</span></span> <span data-ttu-id="d9129-125">Все исключения объектов SMO имеют тип SmoException и перечислены в справке по объектам SMO.</span><span class="sxs-lookup"><span data-stu-id="d9129-125">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="d9129-126">Последовательность внутренних исключений отображается, чтобы показать основание ошибки.</span><span class="sxs-lookup"><span data-stu-id="d9129-126">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="d9129-127">Дополнительные сведения см. в документации по среде [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="d9129-127">For more information, see the [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET documentation.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBExceptions1](SMO How to#SMO_VBExceptions1)]  -->  
  
## <a name="catching-an-exception-in-visual-c"></a><span data-ttu-id="d9129-128">Перехват исключения на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="d9129-128">Catching an Exception in Visual C#</span></span>  
 <span data-ttu-id="d9129-129">В этом примере кода показано, как использовать инструкцию `Try...Catch...Finally` в Visual C# для перехвата исключения объекта SMO.</span><span class="sxs-lookup"><span data-stu-id="d9129-129">This code example shows how to use the `Try...Catch...Finally` Visual C# statement to catch a SMO exception.</span></span> <span data-ttu-id="d9129-130">Все исключения объектов SMO имеют тип SmoException и перечислены в справке по объектам SMO.</span><span class="sxs-lookup"><span data-stu-id="d9129-130">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="d9129-131">Последовательность внутренних исключений отображается, чтобы показать основание ошибки.</span><span class="sxs-lookup"><span data-stu-id="d9129-131">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="d9129-132">Дополнительные сведения см. в документации по языку Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d9129-132">For more information, see the Visual C# documentation.</span></span>  
  
```  
{   
//This sample requires the Microsoft.SqlServer.Management.Smo.Agent namespace to be included.   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define an Operator object variable by supplying the parent SQL Agent and the name arguments in the constructor.   
//Note that the Operator type requires [] parenthesis to differentiate it from a Visual Basic key word.   
op = new Operator(srv.JobServer, "Test_Operator");   
op.Create();   
//Start exception handling.   
try {   
    //Create the operator again to cause an SMO exception.   
    OperatorCategory opx;   
    opx = new OperatorCategory(srv.JobServer, "Test_Operator");   
    opx.Create();   
}   
//Catch the SMO exception   
catch (SmoException smoex) {   
    Console.WriteLine("This is an SMO Exception");   
   //Display the SMO exception message.   
   Console.WriteLine(smoex.Message);   
   //Display the sequence of non-SMO exceptions that caused the SMO exception.   
   Exception ex;   
   ex = smoex.InnerException;   
   while (!object.ReferenceEquals(ex.InnerException, (null))) {   
      Console.WriteLine(ex.InnerException.Message);   
      ex = ex.InnerException;   
    }   
    }   
   //Catch other non-SMO exceptions.   
   catch (Exception ex) {   
      Console.WriteLine("This is not an SMO exception.");   
}   
}  
```  
  
  
