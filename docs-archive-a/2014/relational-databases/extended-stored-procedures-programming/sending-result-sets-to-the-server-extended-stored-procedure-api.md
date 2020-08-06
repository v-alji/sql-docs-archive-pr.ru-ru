---
title: Отправка результирующих наборов на сервер (API-интерфейс расширенных хранимых процедур) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], sending result sets
- result sets [SQL Server], extended stored procedures
ms.assetid: 9d54673d-ea9d-4ac6-825a-f216ad8b0e34
author: rothja
ms.author: jroth
ms.openlocfilehash: 82984440f96416189eb18f900764ee7bdaf05a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654286"
---
# <a name="sending-result-sets-to-the-server-extended-stored-procedure-api"></a><span data-ttu-id="13fd4-102">Отправка результирующих наборов на сервер (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="13fd4-102">Sending Result Sets to the Server (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="13fd4-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="13fd4-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="13fd4-104">При отправке результирующего набора в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Расширенная хранимая процедура должна вызывать соответствующий API следующим образом:</span><span class="sxs-lookup"><span data-stu-id="13fd4-104">When sending a result set to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the extended stored procedure should call the appropriate API as follows:</span></span>  
  
-   <span data-ttu-id="13fd4-105">Функция **srv_sendmsg** может быть вызвана в любом порядке до или после отправки всех строк (если таковые имеются) с **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="13fd4-105">The **srv_sendmsg** function may be called in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="13fd4-106">Все сообщения должны отправляться клиенту перед отправкой состояния завершения с **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="13fd4-106">All messages must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="13fd4-107">Функция **srv_sendrow** вызывается по разу для каждой из строк, отправляемых клиенту.</span><span class="sxs-lookup"><span data-stu-id="13fd4-107">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="13fd4-108">Все строки должны отправляться клиенту перед отправкой сообщений, значений состояния или состояний завершения с помощью **srv_sendmsg**, **srv_status** аргумента для **SRV_PFIELD**или **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="13fd4-108">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, the **srv_status** argument of **srv_pfield**, or **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="13fd4-109">При отправке строки, в которой не были все столбцы, определенные с помощью **srv_describe** , приложение создает информационное сообщение об ошибке и возвращает клиенту ошибку.</span><span class="sxs-lookup"><span data-stu-id="13fd4-109">Sending a row that has not had all its columns defined with **srv_describe** causes the application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="13fd4-110">В этом случае строка не отправляется.</span><span class="sxs-lookup"><span data-stu-id="13fd4-110">In this case, the row is not sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fd4-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="13fd4-111">See Also</span></span>  
 [<span data-ttu-id="13fd4-112">Создание расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="13fd4-112">Creating Extended Stored Procedures</span></span>](creating-extended-stored-procedures.md)  
  
  
