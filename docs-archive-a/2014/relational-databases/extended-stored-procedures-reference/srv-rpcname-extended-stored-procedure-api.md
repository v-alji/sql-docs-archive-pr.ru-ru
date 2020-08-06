---
title: srv_rpcname (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcname
ms.assetid: 0a1424e4-3319-4836-b8d8-5e0344cc683f
author: rothja
ms.author: jroth
ms.openlocfilehash: 21530b3e7b8aaa8c5a3f8770762cde7e258e3a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751015"
---
# <a name="srv_rpcname-extended-stored-procedure-api"></a><span data-ttu-id="b43bd-102">srv_ rpcname (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="b43bd-102">srv_rpcname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b43bd-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b43bd-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="b43bd-104">Возвращает компонент имени процедуры для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b43bd-104">Returns the procedure name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b43bd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b43bd-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcname (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b43bd-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b43bd-106">Arguments</span></span>  
 <span data-ttu-id="b43bd-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="b43bd-107">*srvproc*</span></span>  
 <span data-ttu-id="b43bd-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, получивший удаленную хранимую процедуру).</span><span class="sxs-lookup"><span data-stu-id="b43bd-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="b43bd-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="b43bd-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="b43bd-110">*len*</span><span class="sxs-lookup"><span data-stu-id="b43bd-110">*len*</span></span>  
 <span data-ttu-id="b43bd-111">Указатель на целочисленную переменную, принимающую длину имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="b43bd-111">Is a pointer to an integer variable that receives the length of the database name.</span></span> <span data-ttu-id="b43bd-112">Если значением *len* является NULL, длина имени удаленной хранимой процедуры не возвращается.</span><span class="sxs-lookup"><span data-stu-id="b43bd-112">If *len* is NULL, the length of the remote stored procedure name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b43bd-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b43bd-113">Returns</span></span>  
 <span data-ttu-id="b43bd-114">Указатель DBCHAR на оканчивающуюся нулевым байтом строку для компонента имени текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b43bd-114">A DBCHAR pointer to the null-terminated string for the remote stored procedure name component of the current remote stored procedure.</span></span> <span data-ttu-id="b43bd-115">Если текущей удаленной хранимой процедуры не существует, возвращается NULL, а значение *len* устанавливается равным -1.</span><span class="sxs-lookup"><span data-stu-id="b43bd-115">If there is not a current remote stored procedure, NULL is returned and *len* is set to -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b43bd-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="b43bd-116">Remarks</span></span>  
 <span data-ttu-id="b43bd-117">Эта функция возвращает только имя удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b43bd-117">This function returns only the name of the remote stored procedure.</span></span> <span data-ttu-id="b43bd-118">Она не включает необязательные описатели владельца, имени базы данных и номера удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b43bd-118">It does not include the optional specifiers for owner, database name, and remote stored procedure number.</span></span>  
  
 <span data-ttu-id="b43bd-119">Поскольку вызов **srv_rpcname** допускается и при отсутствии удаленной хранимой процедуры (информационной ошибки не возникает), эта функция дает возможность определить, существует ли удаленная хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="b43bd-119">Because it is valid to call **srv_rpcname** when there is not a remote stored procedure (no informational error occurs), this function provides a method for determining whether a remote stored procedure exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b43bd-120">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="b43bd-120">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="b43bd-121">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="b43bd-121">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
