---
title: Регистрация подключенного сервера
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.f1
helpviewer_keywords:
- Registered Servers [SQL Server], register connected servers
- connected server registrations [SQL Server]
ms.assetid: 77deb5f5-0f80-484f-8b8b-29afa67ec18f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1d337d2da7d305165307745fb02526e37b53bbd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658028"
---
# <a name="register-a-connected-server-sql-server-management-studio"></a><span data-ttu-id="038b6-102">Регистрация подключенного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="038b6-102">Register a Connected Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="038b6-103">В этом разделе описано, как производить регистрацию серверов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="038b6-103">This topic describes how to register servers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="038b6-104">Регистрация сервера дает возможность сохранить данные о соединении для тех серверов, к которым часто осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="038b6-104">By registering the server, you can save the connection information for servers that you access frequently.</span></span> <span data-ttu-id="038b6-105">Сервер может быть зарегистрирован перед установкой соединения или во время соединения из обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="038b6-105">A server can be registered before connecting, or at the time of connection from Object Explorer.</span></span>  
  
 <span data-ttu-id="038b6-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="038b6-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="038b6-107">**Регистрация сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="038b6-107">**To register a server, using:**</span></span>  
  
     [<span data-ttu-id="038b6-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="038b6-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="038b6-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="038b6-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-register-a-connected-server"></a><span data-ttu-id="038b6-110">Регистрация подключенного сервера</span><span class="sxs-lookup"><span data-stu-id="038b6-110">To register a connected server</span></span>  
  
1.  <span data-ttu-id="038b6-111">В обозревателе объектов щелкните правой кнопкой мыши имя сервера, с которым уже установлено соединение, а затем нажмите кнопку **Зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="038b6-111">In Object Explorer, right-click a server to which you already are connected, and then click **Register**.</span></span>  
  
     <span data-ttu-id="038b6-112">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="038b6-112">**Server name**</span></span>  
     <span data-ttu-id="038b6-113">Введите имя сервера, которое нужно использовать для зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="038b6-113">Enter the name you want to use for the registered server.</span></span> <span data-ttu-id="038b6-114">Регистрация локального или удаленного сервера с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] позволяет сохранить сведения о соединении с сервером для будущих соединений.</span><span class="sxs-lookup"><span data-stu-id="038b6-114">Registering a local or remote server using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lets you store the server connection information for future connections.</span></span> <span data-ttu-id="038b6-115">Значением по умолчанию для этого поля является имя сервера, введенное при соединении с ним.</span><span class="sxs-lookup"><span data-stu-id="038b6-115">This field defaults to the server name entered when you were connecting to the server.</span></span> <span data-ttu-id="038b6-116">Можно оставить это имя сервера или ввести другое легко запоминающееся имя.</span><span class="sxs-lookup"><span data-stu-id="038b6-116">You can retain this server name or enter another easy-to-use name for the server.</span></span>  
  
     <span data-ttu-id="038b6-117">**Описание сервера**</span><span class="sxs-lookup"><span data-stu-id="038b6-117">**Server description**</span></span>  
     <span data-ttu-id="038b6-118">Введите необязательное описание сервера.</span><span class="sxs-lookup"><span data-stu-id="038b6-118">Enter an optional description of the server.</span></span> <span data-ttu-id="038b6-119">Максимально допустимое количество знаков — 250.</span><span class="sxs-lookup"><span data-stu-id="038b6-119">The maximum number of characters allowed is 250.</span></span>  
  
     <span data-ttu-id="038b6-120">**Выберите группу серверов**</span><span class="sxs-lookup"><span data-stu-id="038b6-120">**Select a server group**</span></span>  
     <span data-ttu-id="038b6-121">Выберите группу серверов, в которой нужно сохранить регистрацию сервера.</span><span class="sxs-lookup"><span data-stu-id="038b6-121">Select the server group where you want to save the server registration.</span></span>  
  
     <span data-ttu-id="038b6-122">**Новая группа**</span><span class="sxs-lookup"><span data-stu-id="038b6-122">**New Group**</span></span>  
     <span data-ttu-id="038b6-123">Щелкните, чтобы открыть диалоговое окно **Создать группу**, в котором нужно создать новую группу серверов для зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="038b6-123">Click to launch the **New Group** dialog box, where you can create a new server group for the registered server.</span></span>  
  
     <span data-ttu-id="038b6-124">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="038b6-124">**Save**</span></span>  
     <span data-ttu-id="038b6-125">Выберите, чтобы сохранить введенные данные и создать зарегистрированный сервер.</span><span class="sxs-lookup"><span data-stu-id="038b6-125">Click to save the information you have entered and create a registered server.</span></span>  
  
  
