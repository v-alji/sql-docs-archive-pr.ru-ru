---
title: srv_alloc (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_alloc
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b372c1b43987e5bebd1fb82e995dc6d262455ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657110"
---
# <a name="srv_alloc-extended-stored-procedure-api"></a><span data-ttu-id="bf0e1-102">srv_alloc (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="bf0e1-102">srv_alloc (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="bf0e1-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="bf0e1-104">Динамически распределяет память.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-104">Allocates memory dynamically.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf0e1-105">Syntax</span></span>  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf0e1-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bf0e1-106">Arguments</span></span>  
 <span data-ttu-id="bf0e1-107">*size*</span><span class="sxs-lookup"><span data-stu-id="bf0e1-107">*size*</span></span>  
 <span data-ttu-id="bf0e1-108">Указывает число байтов для распределения.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-108">Specifies the number of bytes to allocate.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="bf0e1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf0e1-109">Returns</span></span>  
 <span data-ttu-id="bf0e1-110">Указатель на распределенную память.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-110">A pointer to the newly allocated space.</span></span> <span data-ttu-id="bf0e1-111">Если объем памяти, указываемый аргументом *size*, выделить не удалось, возвращается указатель NULL.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-111">If *size* bytes cannot be allocated, a null pointer is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf0e1-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf0e1-112">Remarks</span></span>  
 <span data-ttu-id="bf0e1-113">Функция **srv_alloc** является эквивалентом функции [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API **GlobalAlloc**.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-113">The **srv_alloc** function is equivalent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API  **GlobalAlloc** function.</span></span> <span data-ttu-id="bf0e1-114">Обычные функции управления памятью библиотеки времени выполнения Windows API на языке C могут использоваться в приложении API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-114">Normal Windows API C run-time memory management functions can be used in an Extended Stored Procedure API application.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf0e1-115">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="bf0e1-115">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="bf0e1-116">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="bf0e1-116">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
