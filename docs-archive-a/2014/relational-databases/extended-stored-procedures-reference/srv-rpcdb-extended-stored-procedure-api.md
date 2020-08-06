---
title: srv_rpcdb (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c951a4a821bbd49748182d9ddf5df017344a174d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739989"
---
# <a name="srv_rpcdb-extended-stored-procedure-api"></a><span data-ttu-id="d79bd-102">srv_rpcdb (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="d79bd-102">srv_rpcdb (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d79bd-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="d79bd-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d79bd-104">Возвращает компонент имени базы данных для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="d79bd-104">Returns the database name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79bd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d79bd-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="d79bd-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d79bd-106">Arguments</span></span>  
 <span data-ttu-id="d79bd-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="d79bd-107">*srvproc*</span></span>  
 <span data-ttu-id="d79bd-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="d79bd-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="d79bd-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="d79bd-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="d79bd-110">*len*</span><span class="sxs-lookup"><span data-stu-id="d79bd-110">*len*</span></span>  
 <span data-ttu-id="d79bd-111">Указатель на переменную типа `int`, которая получает длину имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="d79bd-111">Is a pointer to an `int` variable that receives the length of the database name.</span></span> <span data-ttu-id="d79bd-112">Если переменная *len* имеет значение NULL, длина имени базы данных не возвращается.</span><span class="sxs-lookup"><span data-stu-id="d79bd-112">If *len* is NULL, the length of the database name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d79bd-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d79bd-113">Returns</span></span>  
 <span data-ttu-id="d79bd-114">Указатель DBCHAR на строку, оканчивающуюся нулевым байтом, для части текущей удаленной хранимой процедуры, представляющей имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="d79bd-114">A DBCHAR pointer to the null-terminated string for the database name part of the current remote stored procedure.</span></span> <span data-ttu-id="d79bd-115">При отсутствии текущей удаленной хранимой процедуры возвращается значение NULL, а параметру *len* присваивается значение –1.</span><span class="sxs-lookup"><span data-stu-id="d79bd-115">If there is no current remote stored procedure, NULL is returned and the *len* parameter is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d79bd-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="d79bd-116">Remarks</span></span>  
 <span data-ttu-id="d79bd-117">Эта функция возвращает только компонент базы данных из имени объекта удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="d79bd-117">This function returns only the database component of the remote stored procedure object name.</span></span> <span data-ttu-id="d79bd-118">Он не включает ни необязательные описатели для владельца, ни имя и номер удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="d79bd-118">It does not include the optional specifiers for owner, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d79bd-119">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="d79bd-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d79bd-120">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d79bd-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
