---
title: MSSQLSERVER_26014 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8114183b212767d01013eee9387d8b2efa2e0d7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664256"
---
# <a name="mssqlserver_26014"></a><span data-ttu-id="5c72b-102">MSSQLSERVER_26014</span><span class="sxs-lookup"><span data-stu-id="5c72b-102">MSSQLSERVER_26014</span></span>
    
## <a name="details"></a><span data-ttu-id="5c72b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5c72b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c72b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5c72b-104">Product Name</span></span>|<span data-ttu-id="5c72b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c72b-105">SQL Server</span></span>|  
|<span data-ttu-id="5c72b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5c72b-106">Event ID</span></span>|<span data-ttu-id="5c72b-107">26014</span><span class="sxs-lookup"><span data-stu-id="5c72b-107">26014</span></span>|  
|<span data-ttu-id="5c72b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5c72b-108">Event Source</span></span>|<span data-ttu-id="5c72b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5c72b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5c72b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5c72b-110">Component</span></span>|<span data-ttu-id="5c72b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5c72b-111">SQLEngine</span></span>|  
|<span data-ttu-id="5c72b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5c72b-112">Symbolic Name</span></span>|<span data-ttu-id="5c72b-113">SNI_SSL_USER_CERT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="5c72b-113">SNI_SSL_USER_CERT_FAILURE</span></span>|  
|<span data-ttu-id="5c72b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5c72b-114">Message Text</span></span>|<span data-ttu-id="5c72b-115">Не удалось загрузить указанный пользователем сертификат [Cert Hash(sha1) "%hs"].</span><span class="sxs-lookup"><span data-stu-id="5c72b-115">Unable to load user-specified certificate [Cert Hash(sha1) "%hs"].</span></span> <span data-ttu-id="5c72b-116">Сервер не будет принимать соединения.</span><span class="sxs-lookup"><span data-stu-id="5c72b-116">The server will not accept a connection.</span></span> <span data-ttu-id="5c72b-117">Убедитесь в том, что сертификат установлен правильно.</span><span class="sxs-lookup"><span data-stu-id="5c72b-117">You should verify that the certificate is correctly installed.</span></span> <span data-ttu-id="5c72b-118">См. раздел «Настройка сертификата для использования протоколом SSL» в электронной документации.</span><span class="sxs-lookup"><span data-stu-id="5c72b-118">See "Configuring Certificate for Use by SSL" in Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5c72b-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5c72b-119">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5c72b-120">попытался загрузить сертификат, указанный в сообщении, но эта операция окончилась неудачей.</span><span class="sxs-lookup"><span data-stu-id="5c72b-120">attempted to load the certificate named in the message but the operation failed.</span></span> <span data-ttu-id="5c72b-121">Необходимо устранить эту проблему, прежде чем использовать этот сертификат в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c72b-121">This problem must be resolved before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use this certificate.</span></span>  
  
 <span data-ttu-id="5c72b-122">Возможны следующие причины ошибки.</span><span class="sxs-lookup"><span data-stu-id="5c72b-122">Possible causes of the error include:</span></span>  
  
-   <span data-ttu-id="5c72b-123">Сертификат перемещен или удален.</span><span class="sxs-lookup"><span data-stu-id="5c72b-123">The certificate could have been moved or deleted.</span></span>  
  
-   <span data-ttu-id="5c72b-124">Изменилось имя входа, используемое в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не имеет разрешения для доступа к сертификату.</span><span class="sxs-lookup"><span data-stu-id="5c72b-124">If the login used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not have permission to access the certificate.</span></span>  
  
-   <span data-ttu-id="5c72b-125">Истек срок действия сертификата.</span><span class="sxs-lookup"><span data-stu-id="5c72b-125">The certificate may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5c72b-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5c72b-126">User Action</span></span>  
 <span data-ttu-id="5c72b-127">Убедитесь, что сертификат, указанный в сообщении, существует в системе, является доступным и допустимым для использования.</span><span class="sxs-lookup"><span data-stu-id="5c72b-127">Make sure the certificate named in the message exists on the system, is accessible, and it is valid for use.</span></span>  
  
  
