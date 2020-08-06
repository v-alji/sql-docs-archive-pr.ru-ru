---
title: Олицетворение и учетные данные для подключений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
ms.openlocfilehash: cdbc52e07f4502adda7301ce7f635c050ed9c3c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665381"
---
# <a name="impersonation-and-credentials-for-connections"></a><span data-ttu-id="05144-102">Олицетворение и учетные данные для соединений</span><span class="sxs-lookup"><span data-stu-id="05144-102">Impersonation and Credentials for Connections</span></span>
  <span data-ttu-id="05144-103">В условиях интеграции [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] со средой CLR использовать проверку подлинности Windows сложнее, чем проверку подлинности SQL Server, но более безопасно.</span><span class="sxs-lookup"><span data-stu-id="05144-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] common language runtime (CLR) integration, using Windows Authentication is complex, but is more secure than using SQL Server Authentication.</span></span> <span data-ttu-id="05144-104">При использовании проверки подлинности Windows имейте ввиду следующие замечания.</span><span class="sxs-lookup"><span data-stu-id="05144-104">When using Windows Authentication, keep in mind the following considerations.</span></span>  
  
 <span data-ttu-id="05144-105">По умолчанию процесс SQL Server, который подключается к Windows, приобретает контекст безопасности учетной записи службы Windows SQL Server.</span><span class="sxs-lookup"><span data-stu-id="05144-105">By default, a SQL Server process that connects out to Windows acquires the security context of the SQL Server Windows service account.</span></span> <span data-ttu-id="05144-106">Однако возможно также сопоставить функцию CLR с удостоверением-посредником, чтобы у исходящих соединений был контекст безопасности, отличный от учетной записи службы Windows.</span><span class="sxs-lookup"><span data-stu-id="05144-106">But it is possible to map a CLR function to a proxy identity, so that its outbound connections have a different security context than that of the Windows service account.</span></span>  
  
 <span data-ttu-id="05144-107">В некоторых случаях бывает необходимо олицетворить вызывающего при помощи свойства `SqlContext.WindowsIdentity`, а не запускать его, как учетную запись службы.</span><span class="sxs-lookup"><span data-stu-id="05144-107">In some cases, you may want to impersonate the caller by using the `SqlContext.WindowsIdentity` property instead of running as the service account.</span></span> <span data-ttu-id="05144-108">Экземпляр `WindowsIdentity` представляет идентификатор клиента, запустившего вызывающий код, и его можно использовать только если клиент использовал проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="05144-108">The `WindowsIdentity` instance represents the identity of the client that invoked the calling code, and is only available when the client used Windows Authentication.</span></span> <span data-ttu-id="05144-109">Получив экземпляр `WindowsIdentity`, можно вызвать метод `Impersonate`, чтобы изменить токен безопасности потока, а затем открыть соединения ADO.NET от имени клиента.</span><span class="sxs-lookup"><span data-stu-id="05144-109">After you have obtained the `WindowsIdentity` instance, you can call `Impersonate` to change the security token of the thread, and then open ADO.NET connections on behalf of the client.</span></span>  
  
 <span data-ttu-id="05144-110">После вызова SQLContext. WindowsIdentity. IMPERSONATE вы не сможете получить доступ к локальным данным, и вы не сможете получить доступ к системным данным.</span><span class="sxs-lookup"><span data-stu-id="05144-110">After you call SQLContext.WindowsIdentity.Impersonate, you cannot access local data and you cannot access system data.</span></span> <span data-ttu-id="05144-111">Чтобы снова получить доступ к данным, необходимо вызвать метод WindowsImpersonationContext. Undo.</span><span class="sxs-lookup"><span data-stu-id="05144-111">To access data again, you have to call WindowsImpersonationContext.Undo.</span></span>  
  
 <span data-ttu-id="05144-112">В следующем примере показано, как выполнять олицетворение вызывающего объекта с помощью свойства `SqlContext.WindowsIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05144-112">The following example shows how to impersonate the caller by using the `SqlContext.WindowsIdentity` property.</span></span>  
  
 <span data-ttu-id="05144-113">Visual C#</span><span class="sxs-lookup"><span data-stu-id="05144-113">Visual C#</span></span>  
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="05144-114">Сведения об изменениях в работе олицетворения см. в разделе [критические изменения в функциях ядро СУБД в SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="05144-114">For information about behavior changes in impersonation, see [Breaking Changes to Database Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="05144-115">Более того, если был получен экземпляр идентификатора [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, то по умолчанию нельзя перенести этот экземпляр на другой компьютер; по умолчанию инфраструктура безопасности Windows не позволяет делать этого.</span><span class="sxs-lookup"><span data-stu-id="05144-115">Furthermore, if you obtained the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows identity instance, by default you cannot propagate that instance to another computer; Windows security infrastructure restricts that by default.</span></span> <span data-ttu-id="05144-116">Однако существует механизм под названием «делегирование», который позволяет распространять идентификаторы Windows на несколько доверенных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="05144-116">There is, however, a mechanism called "delegation" that enables propagation of Windows identities across multiple trusted computers.</span></span> <span data-ttu-id="05144-117">Дополнительные сведения о делегировании см. в статье TechNet "[Переход по протоколу Kerberos и ограниченное делегирование](https://go.microsoft.com/fwlink/?LinkId=50419)".</span><span class="sxs-lookup"><span data-stu-id="05144-117">You can learn more about delegation in the TechNet article, "[Kerberos Protocol Transition and Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=50419)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05144-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="05144-118">See Also</span></span>  
 [<span data-ttu-id="05144-119">Объект SqlContext</span><span class="sxs-lookup"><span data-stu-id="05144-119">SqlContext Object</span></span>](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
