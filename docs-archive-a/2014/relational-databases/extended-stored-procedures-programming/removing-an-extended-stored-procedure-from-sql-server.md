---
title: Удаление расширенной хранимой процедуры из SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.openlocfilehash: 284da815de073248669da032c06ddeeb68c697a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752155"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a><span data-ttu-id="9a916-102">Удаление расширенной хранимой процедуры из SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a916-102">Removing an Extended Stored Procedure from SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9a916-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9a916-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="9a916-104">Чтобы удалить каждую функцию расширенной хранимой процедуры в определяемой пользователем библиотеке DLL расширенной хранимой процедуры, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] системный администратор должен запустить **sp_dropextendedproc** системную хранимую процедуру, указав имя функции и имя библиотеки DLL, в которой находится эта функция.</span><span class="sxs-lookup"><span data-stu-id="9a916-104">To drop each extended stored procedure function in a user-defined extended stored procedure DLL, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must run the **sp_dropextendedproc** system stored procedure, specifying the name of the function and the name of the DLL in which that function resides.</span></span> <span data-ttu-id="9a916-105">Например, эта команда удаляет функцию **xp_hello**, расположенную в библиотеке DLL с именем xp_hello.dll, из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9a916-105">For example, this command removes the function **xp_hello**, located in a DLL named xp_hello.dll, from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="9a916-106">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , **sp_dropextendedproc** не удаляет Системные расширенные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="9a916-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], **sp_dropextendedproc** does not drop system extended stored procedures.</span></span> <span data-ttu-id="9a916-107">Вместо этого системный администратор должен отклонить разрешение EXECUTE на расширенную хранимую процедуру для роли **Public** .</span><span class="sxs-lookup"><span data-stu-id="9a916-107">Instead, the system administrator should deny EXECUTE permission on the extended stored procedure to the **public** role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a916-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a916-108">See Also</span></span>  
 [<span data-ttu-id="9a916-109">sp_dropextendedproc (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9a916-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
