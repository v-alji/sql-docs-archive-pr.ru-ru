---
title: Как работают расширенные хранимые процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], about extended stored procedures
ms.assetid: 6e946d8c-3268-4b59-8a1c-1637909cd701
author: rothja
ms.author: jroth
ms.openlocfilehash: 75082fed6b70c214b4f55b85034ffa371824d24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666612"
---
# <a name="how-extended-stored-procedures-work"></a><span data-ttu-id="8b7ad-102">Принципы работы расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="8b7ad-102">How Extended Stored Procedures Work</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8b7ad-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8b7ad-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="8b7ad-104">Принцип работы расширенной хранимой процедуры заключается в следующем.</span><span class="sxs-lookup"><span data-stu-id="8b7ad-104">The process by which an extended stored procedure works is:</span></span>  
  
1.  <span data-ttu-id="8b7ad-105">Когда клиент выполняет расширенную хранимую процедуру, запрос передается в виде потока табличных данных (TDS) или в формате протокола SOAP из клиентского приложения в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b7ad-105">When a client executes an extended stored procedure, the request is transmitted in tabular data stream (TDS) or Simple Object Access Protocol (SOAP) format from the client application to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8b7ad-106">ищет DLL-библиотеки, связанные с расширенной хранимой процедурой, и загружает их, если они еще не загружены.</span><span class="sxs-lookup"><span data-stu-id="8b7ad-106">searches for the DLL associated with the extended stored procedure, and loads the DLL if it is not already loaded.</span></span>  
  
3.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8b7ad-107">вызывает запрошенную расширенную хранимую процедуру (реализованную как функцию внутри DLL-библиотеки).</span><span class="sxs-lookup"><span data-stu-id="8b7ad-107">calls the requested extended stored procedure (implemented as a function inside the DLL).</span></span>  
  
4.  <span data-ttu-id="8b7ad-108">Расширенная хранимая процедура передает результирующий набор и возвращает параметры обратно на сервер через API-интерфейс расширенной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="8b7ad-108">The extended stored procedure passes result sets and return parameters back to the server by through the Extended Stored Procedure API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b7ad-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b7ad-109">See Also</span></span>  
 [<span data-ttu-id="8b7ad-110">Программирование расширенных хранимых процедур ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="8b7ad-110">Database Engine Extended Stored Procedure Programming</span></span>](../database-engine-extended-stored-procedure-programming.md)  
  
  
