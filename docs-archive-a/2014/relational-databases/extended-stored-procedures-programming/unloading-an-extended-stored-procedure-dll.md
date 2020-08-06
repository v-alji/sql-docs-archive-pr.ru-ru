---
title: Выгрузка DLL-библиотеки расширенной хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], unloading
- unloading extended stored procedures
ms.assetid: 4c75ab14-af54-4965-b376-8d75d385c941
author: rothja
ms.author: jroth
ms.openlocfilehash: 7bd4855390e95d949ab769d6567d6f106959dcde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654280"
---
# <a name="unloading-an-extended-stored-procedure-dll"></a><span data-ttu-id="da997-102">Выгрузка DLL-библиотеки расширенной хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="da997-102">Unloading an Extended Stored Procedure DLL</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="da997-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="da997-103">Use CLR Integration instead.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="da997-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]загружает БИБЛИОТЕКУ DLL расширенной хранимой процедуры, как только выполняется вызов одной из функций библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="da997-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads an extended stored procedure DLL as soon as a call is made to one of the functions of the DLL.</span></span> <span data-ttu-id="da997-105">DLL-библиотека остается загруженной до тех пор, пока не выключается сервер или системный администратор не выгружает ее с помощью инструкции DBCC.</span><span class="sxs-lookup"><span data-stu-id="da997-105">The DLL remains loaded until the server is shut down or until the system administrator uses the DBCC statement to unload it.</span></span> <span data-ttu-id="da997-106">Например, эта команда выгружает **xp_hello.dll**, позволяя системному администратору Копировать более новую версию этого файла в каталог без выключения сервера.</span><span class="sxs-lookup"><span data-stu-id="da997-106">For example, this command unloads the **xp_hello.dll**, allowing the system administrator to copy a newer version of this file to the directory without shutting down the server:</span></span>  
  
```  
DBCC xp_hello(FREE)  
```  
  
## <a name="see-also"></a><span data-ttu-id="da997-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="da997-107">See Also</span></span>  
 [<span data-ttu-id="da997-108">DBCC dllname &#40;бесплатный&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="da997-108">DBCC dllname &#40;FREE&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dllname-free-transact-sql)  
  
  
