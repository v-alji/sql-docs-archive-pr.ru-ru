---
title: MSSQL_ENG018456 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018456 error
ms.assetid: 3daa8144-d81f-445a-b6c3-4bb3e9fd1526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b05ca549781215e0c4f247110fee87f6def56f04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733954"
---
# <a name="mssql_eng018456"></a><span data-ttu-id="7d65e-102">MSSQL_ENG018456</span><span class="sxs-lookup"><span data-stu-id="7d65e-102">MSSQL_ENG018456</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7d65e-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="7d65e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d65e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7d65e-104">Product Name</span></span>|<span data-ttu-id="7d65e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d65e-105">SQL Server</span></span>|  
|<span data-ttu-id="7d65e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7d65e-106">Event ID</span></span>|<span data-ttu-id="7d65e-107">18456</span><span class="sxs-lookup"><span data-stu-id="7d65e-107">18456</span></span>|  
|<span data-ttu-id="7d65e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7d65e-108">Event Source</span></span>|<span data-ttu-id="7d65e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d65e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d65e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7d65e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7d65e-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7d65e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7d65e-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7d65e-112">Message Text</span></span>|<span data-ttu-id="7d65e-113">Ошибка входа пользователя '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="7d65e-113">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d65e-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7d65e-114">Explanation</span></span>  
 <span data-ttu-id="7d65e-115">Ошибка MSSQL_ENG018456 возникает при неудачной попытке входа в систему.</span><span class="sxs-lookup"><span data-stu-id="7d65e-115">Error MSSQL_ENG018456 is raised whenever a login attempt fails.</span></span> <span data-ttu-id="7d65e-116">Если сообщение об ошибке включает учетную запись **distributor_admin** (Ошибка входа пользователя 'distributor_admin'.), проблема заключается в учетной записи, которая используется репликацией.</span><span class="sxs-lookup"><span data-stu-id="7d65e-116">If the error message includes the account **distributor_admin** (Login failed for user 'distributor_admin'.), the issue is with an account used by replication.</span></span> <span data-ttu-id="7d65e-117">Репликация создает удаленный сервер **repl_distributor**, предоставляющий возможность обмена данными между распространителем и издателем.</span><span class="sxs-lookup"><span data-stu-id="7d65e-117">Replication creates a remote server, **repl_distributor**, which allows communication between the Distributor and Publisher.</span></span> <span data-ttu-id="7d65e-118">Имя входа **distributor_admin** связано с этим удаленным сервером и должно иметь правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="7d65e-118">The login **distributor_admin** is associated with this remote server and must have a valid password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d65e-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7d65e-119">User Action</span></span>  
 <span data-ttu-id="7d65e-120">Убедитесь в том, что для учетной записи указан пароль.</span><span class="sxs-lookup"><span data-stu-id="7d65e-120">Ensure that you have specified a password for this account.</span></span> <span data-ttu-id="7d65e-121">Дополнительные сведения см. в разделе [Организация безопасности распространителя](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="7d65e-121">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d65e-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d65e-122">See Also</span></span>  
 [<span data-ttu-id="7d65e-123">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="7d65e-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
