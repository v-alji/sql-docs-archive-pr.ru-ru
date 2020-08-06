---
title: srv_pfield (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
author: rothja
ms.author: jroth
ms.openlocfilehash: 90680d59dbf36ad3f713fd7a09d07553890a8668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751019"
---
# <a name="srv_pfield-extended-stored-procedure-api"></a><span data-ttu-id="385cd-102">srv_pfield (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="385cd-102">srv_pfield (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="385cd-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="385cd-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="385cd-104">Возвращает сведения о подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="385cd-104">Returns information about a database connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="385cd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="385cd-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="385cd-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="385cd-106">Arguments</span></span>  
 <span data-ttu-id="385cd-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="385cd-107">*srvproc*</span></span>  
 <span data-ttu-id="385cd-108">Указатель, определяющий подключение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="385cd-108">Pointer identifying a database connection.</span></span>  
  
 <span data-ttu-id="385cd-109">*полями*</span><span class="sxs-lookup"><span data-stu-id="385cd-109">*field*</span></span>  
 <span data-ttu-id="385cd-110">Задает возвращаемые сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="385cd-110">Specifies data on the connection to return.</span></span>  
  
|<span data-ttu-id="385cd-111">Значение</span><span class="sxs-lookup"><span data-stu-id="385cd-111">Value</span></span>|<span data-ttu-id="385cd-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="385cd-112">Returns</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="385cd-113">SRV_APPLNAME</span><span class="sxs-lookup"><span data-stu-id="385cd-113">SRV_APPLNAME</span></span>|<span data-ttu-id="385cd-114">Имя приложения, задаваемое клиентом при установлении соединения.</span><span class="sxs-lookup"><span data-stu-id="385cd-114">The application name provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="385cd-115">SRV_BCPFLAG</span><span class="sxs-lookup"><span data-stu-id="385cd-115">SRV_BCPFLAG</span></span>|<span data-ttu-id="385cd-116">Флаг, имеющий значение TRUE, если клиент готовится к операции массового копирования, и FALSE в противном случае.</span><span class="sxs-lookup"><span data-stu-id="385cd-116">A flag that is TRUE if the client is preparing for a bulk copy operation; otherwise, FALSE.</span></span>|  
|<span data-ttu-id="385cd-117">SRV_CLIB</span><span class="sxs-lookup"><span data-stu-id="385cd-117">SRV_CLIB</span></span>|<span data-ttu-id="385cd-118">Имя библиотеки, позволяющей клиенту общаться с сервером.</span><span class="sxs-lookup"><span data-stu-id="385cd-118">The name of the library that enables the client to talk to a server.</span></span>|  
|<span data-ttu-id="385cd-119">SRV_CPID</span><span class="sxs-lookup"><span data-stu-id="385cd-119">SRV_CPID</span></span>|<span data-ttu-id="385cd-120">Идентификатор клиентского процесса на клиентском компьютере-источнике.</span><span class="sxs-lookup"><span data-stu-id="385cd-120">The client process ID on the client source computer.</span></span>|  
|<span data-ttu-id="385cd-121">SRV_HOST</span><span class="sxs-lookup"><span data-stu-id="385cd-121">SRV_HOST</span></span>|<span data-ttu-id="385cd-122">Имя клиентского компьютера, сообщаемое клиентом при установлении соединения.</span><span class="sxs-lookup"><span data-stu-id="385cd-122">The name of the client's machine provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="385cd-123">SRV_LIBVERS</span><span class="sxs-lookup"><span data-stu-id="385cd-123">SRV_LIBVERS</span></span>|<span data-ttu-id="385cd-124">Версия клиентской библиотеки.</span><span class="sxs-lookup"><span data-stu-id="385cd-124">The version of the client library.</span></span>|  
|<span data-ttu-id="385cd-125">SRV_LSECURE</span><span class="sxs-lookup"><span data-stu-id="385cd-125">SRV_LSECURE</span></span>|<span data-ttu-id="385cd-126">Флаг.</span><span class="sxs-lookup"><span data-stu-id="385cd-126">A flag.</span></span> <span data-ttu-id="385cd-127">Имеет значение TRUE, если соединение использует для входа в систему встроенную безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="385cd-127">TRUE if the connection used integrated security to login.</span></span>|  
|<span data-ttu-id="385cd-128">SRV_NETWORK_MODULE</span><span class="sxs-lookup"><span data-stu-id="385cd-128">SRV_NETWORK_MODULE</span></span>|<span data-ttu-id="385cd-129">Имя сетевой библиотеки DLL, используемой соединением.</span><span class="sxs-lookup"><span data-stu-id="385cd-129">The name of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="385cd-130">SRV_NETWORK_VERSION</span><span class="sxs-lookup"><span data-stu-id="385cd-130">SRV_NETWORK_VERSION</span></span>|<span data-ttu-id="385cd-131">Версия сетевой библиотеки DLL, используемой соединением.</span><span class="sxs-lookup"><span data-stu-id="385cd-131">The version of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="385cd-132">SRV_NETWORK_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="385cd-132">SRV_NETWORK_CONNECTION</span></span>|<span data-ttu-id="385cd-133">Строка соединения, передаваемая в сетевую библиотеку DLL и используемая для текущего соединения *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="385cd-133">The connection string passed to the Net-Library DLL used for the current *srvproc* connection.</span></span>|  
|<span data-ttu-id="385cd-134">SRV_PIPEHANDLE</span><span class="sxs-lookup"><span data-stu-id="385cd-134">SRV_PIPEHANDLE</span></span>|<span data-ttu-id="385cd-135">Строка, содержащая дескриптор канала подключенного клиента, или NULL, если клиент подключен по сети, не использующей именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="385cd-135">A string containing the pipe handle of a connected client, or NULL if the client is connected on a network that does not use named pipes.</span></span> <span data-ttu-id="385cd-136">Для использования этого дескриптора как допустимого дескриптора канала в [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows строку нужно преобразовать в числовой формат.</span><span class="sxs-lookup"><span data-stu-id="385cd-136">To use this handle as a valid pipe handle with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convert this string to an integer.</span></span>|  
|<span data-ttu-id="385cd-137">SRV_RMTSERVER</span><span class="sxs-lookup"><span data-stu-id="385cd-137">SRV_RMTSERVER</span></span>|<span data-ttu-id="385cd-138">Сервер, с которого вошел в систему клиентский процесс.</span><span class="sxs-lookup"><span data-stu-id="385cd-138">The server from which the client process is logged in.</span></span> <span data-ttu-id="385cd-139">Если вход в систему выполнялся с клиента, значение представляет собой пустую строку.</span><span class="sxs-lookup"><span data-stu-id="385cd-139">If the login is from a client, this value is an empty string.</span></span>|  
|<span data-ttu-id="385cd-140">SRV_ROWSENT</span><span class="sxs-lookup"><span data-stu-id="385cd-140">SRV_ROWSENT</span></span>|<span data-ttu-id="385cd-141">Количество строк, уже переданных процессом *srvproc* для текущего набора результатов.</span><span class="sxs-lookup"><span data-stu-id="385cd-141">The number of rows already sent by *srvproc* for the current set of results.</span></span>|  
|<span data-ttu-id="385cd-142">SRV_SPID</span><span class="sxs-lookup"><span data-stu-id="385cd-142">SRV_SPID</span></span>|<span data-ttu-id="385cd-143">Идентификатор серверного потока *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="385cd-143">The server thread ID of the *srvproc*.</span></span> <span data-ttu-id="385cd-144">Для расширенных хранимых процедур это значение совпадает со столбцом \*\*kpid \*\* таблицы **sys.sysprocesses** и может изменяться со временем.</span><span class="sxs-lookup"><span data-stu-id="385cd-144">For extended stored procedures, this value is the same as the **kpid** column of **sys.sysprocesses**, and it can change over time.</span></span>|  
|<span data-ttu-id="385cd-145">SRV_SPROC_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="385cd-145">SRV_SPROC_CODEPAGE</span></span>|<span data-ttu-id="385cd-146">Кодовая страница, используемая сервером для интерпретации данных в многобайтовой кодировке.</span><span class="sxs-lookup"><span data-stu-id="385cd-146">Codepage that the server uses to interpret multbyte data.</span></span>|  
|<span data-ttu-id="385cd-147">SRV_STATUS</span><span class="sxs-lookup"><span data-stu-id="385cd-147">SRV_STATUS</span></span>|<span data-ttu-id="385cd-148">Текущее состояние *srvproc*: запущена или закрыта</span><span class="sxs-lookup"><span data-stu-id="385cd-148">The current status of *srvproc*: running or closed</span></span>|  
|<span data-ttu-id="385cd-149">SRV_TYPE</span><span class="sxs-lookup"><span data-stu-id="385cd-149">SRV_TYPE</span></span>|<span data-ttu-id="385cd-150">Тип соединения *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="385cd-150">The connection type of *srvproc*.</span></span> <span data-ttu-id="385cd-151">Если возвращается значение server, *srvproc* принадлежит экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="385cd-151">If server is returned, *srvproc* is from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="385cd-152">Если возвращается значение client, *srvproc* принадлежит клиенту DB-Library или ODBC.</span><span class="sxs-lookup"><span data-stu-id="385cd-152">If client is returned, *srvproc* is from a DB-Library or ODBC client.</span></span>|  
|<span data-ttu-id="385cd-153">SRV_USER</span><span class="sxs-lookup"><span data-stu-id="385cd-153">SRV_USER</span></span>|<span data-ttu-id="385cd-154">Имя пользователя, которое использовалось для установки соединения.</span><span class="sxs-lookup"><span data-stu-id="385cd-154">The user name of the connection.</span></span>|  
|||  
  
 <span data-ttu-id="385cd-155">*len*</span><span class="sxs-lookup"><span data-stu-id="385cd-155">*len*</span></span>  
 <span data-ttu-id="385cd-156">Представляет собой указатель на переменную **int**, в которой хранится длина возвращаемого значения *field*.</span><span class="sxs-lookup"><span data-stu-id="385cd-156">Is a pointer to an **int** variable that contains the length of the returned *field* value.</span></span> <span data-ttu-id="385cd-157">Если значение *len* равно NULL, длина строки не возвращается.</span><span class="sxs-lookup"><span data-stu-id="385cd-157">If *len* is NULL, the length of the string is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="385cd-158">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="385cd-158">Returns</span></span>  
 <span data-ttu-id="385cd-159">Указатель на оканчивающуюся нулевым байтом строку, содержащую текущее значение указанного поля в процедуре SRV_PROC.</span><span class="sxs-lookup"><span data-stu-id="385cd-159">A pointer to a null-terminated string containing the current value for the specified field in the SRV_PROC structure.</span></span> <span data-ttu-id="385cd-160">Если поле пусто, то возвращается допустимый указатель на пустую строку, а *len* содержит 0.</span><span class="sxs-lookup"><span data-stu-id="385cd-160">If the field is empty, a valid pointer to an empty string is returned and *len* contains 0.</span></span> <span data-ttu-id="385cd-161">Если поле неизвестно, то возвращается значение NULL, а *len* содержит значение –1.</span><span class="sxs-lookup"><span data-stu-id="385cd-161">If the field is unknown, NULL is returned and *len* contains the value -1.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="385cd-162">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="385cd-162">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="385cd-163">Дополнительные сведения об исследовании и проверке безопасности см. в [Центре разработчиков безопасности](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="385cd-163">For information about security review and testing, see the [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
