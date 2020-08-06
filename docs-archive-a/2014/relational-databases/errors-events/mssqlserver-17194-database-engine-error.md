---
title: MSSQLSERVER_17194 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3f56a104841c4825bba1f60b3588fadd63555c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658795"
---
# <a name="mssqlserver_17194"></a><span data-ttu-id="95c72-102">MSSQLSERVER_17194</span><span class="sxs-lookup"><span data-stu-id="95c72-102">MSSQLSERVER_17194</span></span>
    
## <a name="details"></a><span data-ttu-id="95c72-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="95c72-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95c72-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="95c72-104">Product Name</span></span>|<span data-ttu-id="95c72-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="95c72-105">SQL Server</span></span>|  
|<span data-ttu-id="95c72-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="95c72-106">Event ID</span></span>|<span data-ttu-id="95c72-107">17194</span><span class="sxs-lookup"><span data-stu-id="95c72-107">17194</span></span>|  
|<span data-ttu-id="95c72-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="95c72-108">Event Source</span></span>|<span data-ttu-id="95c72-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="95c72-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="95c72-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="95c72-110">Component</span></span>|<span data-ttu-id="95c72-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="95c72-111">SQLEngine</span></span>|  
|<span data-ttu-id="95c72-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="95c72-112">Symbolic Name</span></span>||  
|<span data-ttu-id="95c72-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="95c72-113">Message Text</span></span>|<span data-ttu-id="95c72-114">Серверу не удалось загрузить библиотеку поставщика SSL, необходимую для входа. Соединение было закрыто.</span><span class="sxs-lookup"><span data-stu-id="95c72-114">The server was unable to load the SSL provider library needed to log in; the connection has been closed.</span></span> <span data-ttu-id="95c72-115">С помощью SSL шифруется последовательность входа в систему или весь обмен данными (в зависимости от конфигурации сервера).</span><span class="sxs-lookup"><span data-stu-id="95c72-115">SSL is used to encrypt either the login sequence or all communications, depending on how the administrator has configured the server.</span></span> <span data-ttu-id="95c72-116">Дополнительные сведения об этой ошибке см. в электронной документации:  0xXXXX.</span><span class="sxs-lookup"><span data-stu-id="95c72-116">See Books Online for information on this error message:  0xXXXX.</span></span> <span data-ttu-id="95c72-117">[Клиент: 11.11.11.11]</span><span class="sxs-lookup"><span data-stu-id="95c72-117">[CLIENT: 11.11.11.11]</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="95c72-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="95c72-118">Explanation</span></span>  
 <span data-ttu-id="95c72-119">Эта ошибка означает, что клиент закрыл соединение.</span><span class="sxs-lookup"><span data-stu-id="95c72-119">This error indicates that the client has closed the connection.</span></span> <span data-ttu-id="95c72-120">Она может возникать по истечении времени ожидания соединения.</span><span class="sxs-lookup"><span data-stu-id="95c72-120">This error could occur because the connection time-out has expired.</span></span> <span data-ttu-id="95c72-121">Эта ошибка возвращает значение, переданное операционной системой. Это значение описывает соответствующую неполадку.</span><span class="sxs-lookup"><span data-stu-id="95c72-121">The error message displays a value from the operating system that describes the underlying problem.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95c72-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="95c72-122">User Action</span></span>  
 <span data-ttu-id="95c72-123">Если в сообщении выведен код ошибки 0x2746 (десятичное значение 10054), то это означает, что соединение было сброшено клиентом. Обычно это происходит при истечении времени ожидания. Для устранения этой ошибки необходимо увеличить время ожидания соединения для клиента или вызывающей программы.</span><span class="sxs-lookup"><span data-stu-id="95c72-123">If the error code in the message is 0x2746 (decimal value 10054), this means that the connection was reset by the client, typically because of a time-out. To resolve the error, increase the connection time-out on the client or calling program.</span></span>  
  
 <span data-ttu-id="95c72-124">Для определения возможных решений для других значений, выдаваемых сообщением об ошибке, выполните команду **net helpmsg**, указав для нее десятичное значение кода ошибки.</span><span class="sxs-lookup"><span data-stu-id="95c72-124">To determine a possible solution for other error message values, use the operating system command **net helpmsg** and specify the decimal value of the error code.</span></span>  
  
 <span data-ttu-id="95c72-125">Дополнительные сведения о подключении к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в статьях [Сетевая конфигурация сервера](../../database-engine/configure-windows/server-network-configuration.md) и [Конфигурация клиентской сети](../../database-engine/configure-windows/client-network-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="95c72-125">For more information about how to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) and [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="95c72-126">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="95c72-126">Internal-Only</span></span>  
  
