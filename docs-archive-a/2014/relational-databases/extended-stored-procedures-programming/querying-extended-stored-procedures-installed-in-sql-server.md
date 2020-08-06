---
title: Запрос расширенных хранимых процедур, установленных в SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f44db9053ad18c3a6902a30aaab4f81610c5a8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657111"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a><span data-ttu-id="a4419-102">Запрос расширенных хранимых процедур, установленных в SQL Server</span><span class="sxs-lookup"><span data-stu-id="a4419-102">Querying Extended Stored Procedures Installed in SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a4419-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a4419-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="a4419-104">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Прошедший проверку подлинности пользователь может отобразить определенные в данный момент расширенные хранимые процедуры и имя библиотеки DLL, к которой они относятся, выполнив **sp_helpextendedproc** системной процедуры.</span><span class="sxs-lookup"><span data-stu-id="a4419-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authenticated user can display the currently defined extended stored procedures and the name of the DLL to which each belongs by running the **sp_helpextendedproc** system procedure.</span></span> <span data-ttu-id="a4419-105">Например, в следующем примере возвращается библиотека DLL, к которой принадлежит **xp_hello** :</span><span class="sxs-lookup"><span data-stu-id="a4419-105">For example, the following example returns the DLL to which **xp_hello** belongs:</span></span>  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="a4419-106">Если **sp_helpextendedproc** выполняется без указания расширенной хранимой процедуры, отображаются все расширенные хранимые процедуры и их библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="a4419-106">If **sp_helpextendedproc** is executed without specifying an extended stored procedure, all the extended stored procedures and their DLLs are displayed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a4419-107">Сведения будут возвращены только для тех расширенных хранимых процедур, владельцем которых является вошедший в систему пользователь или на которые он имеет разрешение.</span><span class="sxs-lookup"><span data-stu-id="a4419-107">Information will be returned for only those extended stored procedures that the logged in user owns or has permissions to.</span></span> <span data-ttu-id="a4419-108">Только члены предопределенной роли сервера **sysadmin** и **db_owner**, **db_securityadmin**и предопределенных ролей базы данных **db_ddladmin** могут просматривать сведения обо всех расширенных хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="a4419-108">Only members of the **sysadmin** fixed server role and the **db_owner**, **db_securityadmin**, and the **db_ddladmin** fixed database roles can view information for all extended stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4419-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4419-109">See Also</span></span>  
 <span data-ttu-id="a4419-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4419-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span></span>  
 <span data-ttu-id="a4419-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4419-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="a4419-112">sp_dropextendedproc (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4419-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
