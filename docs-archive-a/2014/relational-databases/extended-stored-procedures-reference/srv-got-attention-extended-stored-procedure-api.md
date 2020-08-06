---
title: srv_got_attention (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_got_attention
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_got_attention
ms.assetid: 805e68e1-d17f-41bd-8b9f-a27283bb6fbe
author: rothja
ms.author: jroth
ms.openlocfilehash: bb5432e2f5e259187e506237842fbb9110e27a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751039"
---
# <a name="srv_got_attention-extended-stored-procedure-api"></a><span data-ttu-id="9c293-102">srv_got_attention (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="9c293-102">srv_got_attention (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9c293-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9c293-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9c293-104">Проверяет, следует ли прервать выполнение текущего задания или разорвать соединение, и возвращает TRUE, если текущее задание было прервано или соединение разорвано.</span><span class="sxs-lookup"><span data-stu-id="9c293-104">Checks whether the current connection or task needs to be aborted and returns TRUE if the connection is killed or the batch is aborted</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c293-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c293-105">Syntax</span></span>  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c293-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c293-106">Parameters</span></span>  
 <span data-ttu-id="9c293-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9c293-107">*srvproc*</span></span>  
 <span data-ttu-id="9c293-108">Указатель, определяющий подключение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="9c293-108">Pointer identifying a database connection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c293-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c293-109">Return Value</span></span>  
 <span data-ttu-id="9c293-110">Возвращает TRUE, если выполнение текущего пакета было прервано или соединение разорвано.</span><span class="sxs-lookup"><span data-stu-id="9c293-110">TRUE if the connection is killed or the batch is aborted.</span></span> <span data-ttu-id="9c293-111">Возвращает FALSE, если текущий пакет по-прежнему выполняется или соединение существует.</span><span class="sxs-lookup"><span data-stu-id="9c293-111">FALSE if the connection or batch is active.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c293-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c293-112">Remarks</span></span>  
 <span data-ttu-id="9c293-113">Расширенная хранимая процедура, которая выполняется в течение длительного времени, должна периодически проверять соединение с сервером путем вызова функции **srv_got_attention**, чтобы завершиться, когда прерывается выполнение текущего пакета или разрывается соединение.</span><span class="sxs-lookup"><span data-stu-id="9c293-113">A long-running extended stored procedure should check the server attention by calling **srv_got_attention** periodically so that the procedure may terminate itself when the connection is killed or the batch is aborted.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c293-114">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="9c293-114">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9c293-115">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9c293-115">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
