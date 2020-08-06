---
title: Характеристики выполнения расширенных хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], executing
- executing extended stored procedures [SQL Server]
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
author: rothja
ms.author: jroth
ms.openlocfilehash: edbd73797699d65f694e91bc3035e0dc9366c9d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655737"
---
# <a name="execution-characteristics-of-extended-stored-procedures"></a><span data-ttu-id="9f57a-102">Характеристики выполнения расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="9f57a-102">Execution Characteristics of Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9f57a-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9f57a-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="9f57a-104">Выполнение расширенных хранимых процедур имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="9f57a-104">The execution of an extended stored procedure has these characteristics:</span></span>  
  
-   <span data-ttu-id="9f57a-105">Функция расширенной хранимой процедуры выполняется в контексте безопасности [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f57a-105">The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9f57a-106">расширенная хранимая процедура выполняется в пространстве процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="9f57a-106">The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9f57a-107">поток, связанный с выполнением расширенной хранимой процедуры, тот же, что используется для клиентского соединения.</span><span class="sxs-lookup"><span data-stu-id="9f57a-107">The thread associated with the execution of the extended stored procedure is the same one used for the client connection.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9f57a-108">Прежде чем добавить расширенные хранимые процедуры на сервер и предоставить разрешение на их выполнение другим пользователям, системный администратор должен тщательно проверить каждую хранимую процедуру, чтобы убедиться, что она не содержит вредоносного или злонамеренного кода.</span><span class="sxs-lookup"><span data-stu-id="9f57a-108">Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.</span></span>  
  
-  
  
 <span data-ttu-id="9f57a-109">После загрузки библиотеки DLL расширенной хранимой процедуры библиотека DLL остается загруженной в адресное пространство сервера до тех пор, пока [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не будет остановлена или администратор явно выгрузит БИБЛИОТЕКУ DLL с помощью команды DBCC *DLL_name* (Free).</span><span class="sxs-lookup"><span data-stu-id="9f57a-109">After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).</span></span>  
  
 <span data-ttu-id="9f57a-110">Расширенная хранимая процедура может выполняться в [!INCLUDE[tsql](../../includes/tsql-md.md)] как хранимая процедура с помощью инструкции EXECUTE:</span><span class="sxs-lookup"><span data-stu-id="9f57a-110">The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:</span></span>  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f57a-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f57a-111">Parameters</span></span>  
 <span data-ttu-id="9f57a-112">\@ *retval*</span><span class="sxs-lookup"><span data-stu-id="9f57a-112">\@ *retval*</span></span>  
 <span data-ttu-id="9f57a-113">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9f57a-113">Is a return value.</span></span>  
  
 <span data-ttu-id="9f57a-114">\@*param1*</span><span class="sxs-lookup"><span data-stu-id="9f57a-114">\@ *param1*</span></span>  
 <span data-ttu-id="9f57a-115">Входной параметр.</span><span class="sxs-lookup"><span data-stu-id="9f57a-115">Is an input parameter.</span></span>  
  
 <span data-ttu-id="9f57a-116">\@*Param2*</span><span class="sxs-lookup"><span data-stu-id="9f57a-116">\@ *param2*</span></span>  
 <span data-ttu-id="9f57a-117">Входной и (или) выходной параметр.</span><span class="sxs-lookup"><span data-stu-id="9f57a-117">Is an input/output parameter.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9f57a-118">Расширенные хранимые процедуры увеличивают производительность и расширяют возможности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f57a-118">Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="9f57a-119">Однако из-за того, что DLL-библиотека расширенной хранимой процедуры и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] совместно используют одно и то же адресное пространство, проблемная процедура может отрицательно повлиять на работу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f57a-119">However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning.</span></span> <span data-ttu-id="9f57a-120">Хотя исключения, вызываемые DLL-библиотеками расширенных хранимых процедур, обрабатываются [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], тем не менее можно повредить области данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f57a-120">Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas.</span></span> <span data-ttu-id="9f57a-121">В целях безопасности добавлять расширенные хранимые процедуры к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут только системные администраторы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f57a-121">As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9f57a-122">Перед установкой эти процедуры следует тщательно протестировать.</span><span class="sxs-lookup"><span data-stu-id="9f57a-122">These procedures should be thoroughly tested before they are installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f57a-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f57a-123">See Also</span></span>  
 <span data-ttu-id="9f57a-124">[Программирование расширенных хранимых процедур](database-engine-extended-stored-procedures-programming.md) </span><span class="sxs-lookup"><span data-stu-id="9f57a-124">[Programming Extended Stored Procedures](database-engine-extended-stored-procedures-programming.md) </span></span>  
 [<span data-ttu-id="9f57a-125">Запрос расширенных хранимых процедур, установленных в SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f57a-125">Querying Extended Stored Procedures Installed in SQL Server</span></span>](querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
