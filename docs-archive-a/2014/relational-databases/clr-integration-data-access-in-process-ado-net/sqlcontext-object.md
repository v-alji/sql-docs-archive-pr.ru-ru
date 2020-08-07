---
title: Объект SqlContext | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- Windows identity [CLR integration]
- SqlContext object
- context [CLR integration]
ms.assetid: 67437853-8a55-44d9-9337-90689ebba730
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f036e274925f7b28b79f619f8e24b3e8804140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734154"
---
# <a name="sqlcontext-object"></a><span data-ttu-id="bd09d-102">Объект SqlContext</span><span class="sxs-lookup"><span data-stu-id="bd09d-102">SqlContext Object</span></span>
  <span data-ttu-id="bd09d-103">На сервере управляемый код запускается при вызове процедуры, функции или метода для определяемого пользователем типа данных CLR или когда действие вызывает срабатывание триггера, определенного на одном из языков платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd09d-103">You invoke managed code in the server when you call a procedure or function, when you call a method on a common language runtime (CLR) user-defined type, or when your action fires a trigger defined in any of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework languages.</span></span> <span data-ttu-id="bd09d-104">Так как выполнение этого кода необходимо как часть соединения пользователя, требуется доступ к контексту участника из кода, работающего на сервере.</span><span class="sxs-lookup"><span data-stu-id="bd09d-104">Because execution of this code is requested as part of a user connection, access to the context of the caller from the code running in the server is required.</span></span> <span data-ttu-id="bd09d-105">Кроме того, определенные операции доступа к данным могут быть допустимы, только если они выполняются в контексте участника.</span><span class="sxs-lookup"><span data-stu-id="bd09d-105">In addition, certain data access operations may only be valid if run under the context of the caller.</span></span> <span data-ttu-id="bd09d-106">Например, доступ к вставленным или удаленным псевдотаблицам, применяемым в операциях триггеров, допустим только в контексте участника.</span><span class="sxs-lookup"><span data-stu-id="bd09d-106">For example, access to inserted and deleted pseudo-tables used in trigger operations is only valid under the context of the caller.</span></span>  
  
 <span data-ttu-id="bd09d-107">Контекст участника извлекается из объекта `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-107">The context of the caller is abstracted in a `SqlContext` object.</span></span> <span data-ttu-id="bd09d-108">Дополнительные сведения о методах и свойствах `SqlTriggerContext` см. разделе `Microsoft.SqlServer.Server.SqlTriggerContext` справочной документации по пакету SDK платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd09d-108">For more information about the `SqlTriggerContext` methods and properties, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="bd09d-109">Объект `SqlContext` обеспечивает доступ к следующим компонентам.</span><span class="sxs-lookup"><span data-stu-id="bd09d-109">`SqlContext` provides access to the following components:</span></span>  
  
-   <span data-ttu-id="bd09d-110">`SqlPipe`: объект `SqlPipe` представляет "канал", по которому результаты передаются клиенту.</span><span class="sxs-lookup"><span data-stu-id="bd09d-110">`SqlPipe`: The `SqlPipe` object represents the "pipe" through which results flow to the client.</span></span> <span data-ttu-id="bd09d-111">Дополнительные сведения об `SqlPipe` объекте см. в разделе [объект SqlPipe](sqlpipe-object.md).</span><span class="sxs-lookup"><span data-stu-id="bd09d-111">For more information about the `SqlPipe` object, see [SqlPipe Object](sqlpipe-object.md).</span></span>  
  
-   <span data-ttu-id="bd09d-112">`SqlTriggerContext`: объект `SqlTriggerContext` можно получить только из триггера CLR.</span><span class="sxs-lookup"><span data-stu-id="bd09d-112">`SqlTriggerContext`: The `SqlTriggerContext` object can only be retrieved from within a CLR trigger.</span></span> <span data-ttu-id="bd09d-113">Он предоставляет сведения об операции, которая вызвала срабатывание триггера, а также карту столбцов, которые были обновлены.</span><span class="sxs-lookup"><span data-stu-id="bd09d-113">It provides information about the operation that caused the trigger to fire and a map of the columns that were updated.</span></span> <span data-ttu-id="bd09d-114">Дополнительные сведения об `SqlTriggerContext` объекте см. в разделе [объект SqlTriggerContext](sqltriggercontext-object.md).</span><span class="sxs-lookup"><span data-stu-id="bd09d-114">For more information about the `SqlTriggerContext` object, see [SqlTriggerContext Object](sqltriggercontext-object.md).</span></span>  
  
-   <span data-ttu-id="bd09d-115">`IsAvailable`: свойство `IsAvailable` используется для определения доступности контекста.</span><span class="sxs-lookup"><span data-stu-id="bd09d-115">`IsAvailable`: The `IsAvailable` property is used to determine context availability.</span></span>  
  
-   <span data-ttu-id="bd09d-116">`WindowsIdentity`: свойство `WindowsIdentity` используется для получения удостоверения Windows участника.</span><span class="sxs-lookup"><span data-stu-id="bd09d-116">`WindowsIdentity`: The `WindowsIdentity` property is used to retrieve the Windows identity of the caller.</span></span>  
  
## <a name="determining-context-availability"></a><span data-ttu-id="bd09d-117">Определение доступности контекста</span><span class="sxs-lookup"><span data-stu-id="bd09d-117">Determining Context Availability</span></span>  
 <span data-ttu-id="bd09d-118">Выполните запрос к классу `SqlContext`, чтобы определить, работает ли выполняемый в данный момент код в процессе.</span><span class="sxs-lookup"><span data-stu-id="bd09d-118">Query the `SqlContext` class to see if the currently executing code is running in-process.</span></span> <span data-ttu-id="bd09d-119">Чтобы сделать это, проверьте свойство `IsAvailable` объекта `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-119">To do this, check the `IsAvailable` property of the `SqlContext` object.</span></span> <span data-ttu-id="bd09d-120">Свойство `IsAvailable` предназначено только для чтения; оно возвращает значение `True`, если вызывающий код выполняется внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а также если можно получить доступ к другим членам объекта `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-120">The `IsAvailable` property is read-only, and returns `True` if the calling code is running inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and if other `SqlContext` members can be accessed.</span></span> <span data-ttu-id="bd09d-121">Если свойство `IsAvailable` возвращает значение `False`, все остальные члены `SqlContext`, если они используются, формируют исключение `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-121">If the `IsAvailable` property returns `False`, all the other `SqlContext` members throw an `InvalidOperationException`, if used.</span></span> <span data-ttu-id="bd09d-122">Если свойство `IsAvailable` возвращает значение `False`, любая попытка открыть объект соединения, имеющий в строке соединения текст «context connection=true», закончится неудачей.</span><span class="sxs-lookup"><span data-stu-id="bd09d-122">If `IsAvailable` returns `False`, any attempt to open a connection object that has "context connection=true" in the connection string fails.</span></span>  
  
## <a name="retrieving-windows-identity"></a><span data-ttu-id="bd09d-123">Извлечение удостоверения Windows</span><span class="sxs-lookup"><span data-stu-id="bd09d-123">Retrieving Windows Identity</span></span>  
 <span data-ttu-id="bd09d-124">Код CLR, выполняющийся внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], всегда запускается в контексте учетной записи процесса.</span><span class="sxs-lookup"><span data-stu-id="bd09d-124">CLR code executing inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is always invoked in the context of the process account.</span></span> <span data-ttu-id="bd09d-125">Если код должен выполнить определенные действия с использованием удостоверения вызывающего пользователя, а не удостоверения процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то необходимо получить токен олицетворения при помощи свойства `WindowsIdentity` объекта `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-125">If the code should perform certain actions using the identity of the calling user, instead of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process identity, then an impersonation token should be obtained through the `WindowsIdentity` property of the `SqlContext` object.</span></span> <span data-ttu-id="bd09d-126">Свойство `WindowsIdentity` возвращает экземпляр `WindowsIdentity`, представляющий удостоверение [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows участника или значение NULL, если проверка подлинности клиента выполнялась при помощи проверки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd09d-126">The `WindowsIdentity` property returns a `WindowsIdentity` instance representing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows identity of the caller, or null if the client was authenticated using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="bd09d-127">Доступ к этому свойству могут получить только сборки, имеющие разрешения `EXTERNAL_ACCESS` или `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-127">Only assemblies marked with `EXTERNAL_ACCESS` or `UNSAFE` permissions can access this property.</span></span>  
  
 <span data-ttu-id="bd09d-128">Получив объект `WindowsIdentity`, вызывающие могут олицетворять учетную запись клиента и выполнять действия от их имени.</span><span class="sxs-lookup"><span data-stu-id="bd09d-128">After obtaining the `WindowsIdentity` object, callers can impersonate the client account and perform actions on their behalf.</span></span>  
  
 <span data-ttu-id="bd09d-129">Если инициировавший выполнение хранимой процедуры или функции клиент соединился с сервером при помощи проверки подлинности Windows, удостоверение участника доступно только через метод `SqlContext.WindowsIdentity`.</span><span class="sxs-lookup"><span data-stu-id="bd09d-129">The identity of the caller is only available through `SqlContext.WindowsIdentity` if the client that initiated execution of the stored-procedure or function connected to the server using Windows Authentication.</span></span> <span data-ttu-id="bd09d-130">Если использовалась проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], это свойство имеет значение NULL, а код не может олицетворять участника.</span><span class="sxs-lookup"><span data-stu-id="bd09d-130">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication was used instead, this property is null and the code is unable to impersonate the caller.</span></span>  
  
### <a name="example"></a><span data-ttu-id="bd09d-131">Пример</span><span class="sxs-lookup"><span data-stu-id="bd09d-131">Example</span></span>  
 <span data-ttu-id="bd09d-132">В следующем примере показано, как получить удостоверение Windows вызывающего клиента и олицетворить этого клиента.</span><span class="sxs-lookup"><span data-stu-id="bd09d-132">The following example shows how to get the Windows identity of the calling client and impersonate the client.</span></span>  
  
 <span data-ttu-id="bd09d-133">C#</span><span class="sxs-lookup"><span data-stu-id="bd09d-133">C#</span></span>  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void WindowsIDTestProc()  
{  
    WindowsIdentity clientId = null;  
    WindowsImpersonationContext impersonatedUser = null;  
  
    // Get the client ID.  
    clientId = SqlContext.WindowsIdentity;  
  
    // This outer try block is used to thwart exception filter   
    // attacks which would prevent the inner finally   
    // block from executing and resetting the impersonation.  
    try  
    {  
        try  
        {  
            impersonatedUser = clientId.Impersonate();  
            if (impersonatedUser != null)  
            {  
                // Perform some action using impersonation.  
            }  
        }  
        finally  
        {  
            // Undo impersonation.  
            if (impersonatedUser != null)  
                impersonatedUser.Undo();  
        }  
    }  
    catch  
    {  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="bd09d-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd09d-134">Visual Basic</span></span>  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  WindowsIDTestProcVB ()  
    Dim clientId As WindowsIdentity  
    Dim impersonatedUser As WindowsImpersonationContext  
  
    ' Get the client ID.  
    clientId = SqlContext.WindowsIdentity  
  
    ' This outer try block is used to thwart exception filter   
    ' attacks which would prevent the inner finally   
    ' block from executing and resetting the impersonation.  
  
    Try  
        Try  
  
            impersonatedUser = clientId.Impersonate()  
  
            If impersonatedUser IsNot Nothing Then  
                ' Perform some action using impersonation.  
            End If  
  
        Finally  
            ' Undo impersonation.  
            If impersonatedUser IsNot Nothing Then  
                impersonatedUser.Undo()  
            End If  
        End Try  
  
    Catch e As Exception  
  
        Throw e  
  
    End Try  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd09d-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd09d-135">See Also</span></span>  
 <span data-ttu-id="bd09d-136">[Объект SqlPipe](sqlpipe-object.md) </span><span class="sxs-lookup"><span data-stu-id="bd09d-136">[SqlPipe Object](sqlpipe-object.md) </span></span>  
 <span data-ttu-id="bd09d-137">[Объект SqlTriggerContext](sqltriggercontext-object.md) </span><span class="sxs-lookup"><span data-stu-id="bd09d-137">[SqlTriggerContext Object](sqltriggercontext-object.md) </span></span>  
 <span data-ttu-id="bd09d-138">[Триггеры CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="bd09d-138">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="bd09d-139">Внутрипроцессные расширения SQL Server для ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bd09d-139">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
