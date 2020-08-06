---
title: Создание или удаление псевдонима сервера для использования клиентом (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- server alias
helpviewer_keywords:
- aliases [SQL Server], deleting
- aliases [SQL Server], creating
ms.assetid: b687e376-ee33-470d-b65a-87246bfefe6f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bead257b40c33e3640b18890a7d109d774131123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665123"
---
# <a name="create-or-delete-a-server-alias-for-use-by-a-client-sql-server-configuration-manager"></a><span data-ttu-id="69def-102">Создание или удаление псевдонима сервера для использования клиентом (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="69def-102">Create or Delete a Server Alias for Use by a Client (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="69def-103">В этом разделе описано, как создать и удалить псевдоним сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="69def-103">This topic describes how to create or delete a server alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="69def-104">Псевдоним является альтернативным именем, которое можно использовать для создания соединения.</span><span class="sxs-lookup"><span data-stu-id="69def-104">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="69def-105">Псевдоним инкапсулирует необходимые элементы строки соединения и представляет их с помощью имени, выбранного пользователем.</span><span class="sxs-lookup"><span data-stu-id="69def-105">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="69def-106">Псевдонимы могут использоваться с любым клиентским приложением.</span><span class="sxs-lookup"><span data-stu-id="69def-106">Aliases can be used with any client application.</span></span> <span data-ttu-id="69def-107">После создания псевдонима сервера клиент может соединяться с несколькими серверами по разным сетевым протоколам, не указывая протокол и сведения о соединении для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="69def-107">By creating server aliases, your client computer can connect to multiple servers using different network protocols, without having to specify the protocol and connection details for each one.</span></span> <span data-ttu-id="69def-108">Кроме того, можно также держать постоянно включенными несколько сетевых протоколов, даже если некоторые из них используются время от времени.</span><span class="sxs-lookup"><span data-stu-id="69def-108">In addition, you can also have different network protocols enabled all the time, even if you only need to use them occasionally.</span></span> <span data-ttu-id="69def-109">Если сервер настроен на прослушивание порта или именованного канала, отличных от используемых по умолчанию, и служба браузера SQL Server отключена, то можно создать псевдоним, который будет определять другой номер порта или именованный канал.</span><span class="sxs-lookup"><span data-stu-id="69def-109">If you have configured the server to listen on a non-default port number or named pipe, and you have disabled the SQL Server Browser service, create an alias that specifies the new port number or named pipe.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69def-110">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="69def-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-create-an-alias"></a><span data-ttu-id="69def-111">Создание псевдонима</span><span class="sxs-lookup"><span data-stu-id="69def-111">To create an alias</span></span>  
  
1.  <span data-ttu-id="69def-112">В диспетчере конфигурации SQL Server разверните узел **Конфигурация SQL Server Native Client**, щелкните правой кнопкой мыши элемент **Псевдонимы**и выберите пункт **Создать псевдоним**.</span><span class="sxs-lookup"><span data-stu-id="69def-112">In SQL Server Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Aliases**, and then click **New Alias**.</span></span>  
  
2.  <span data-ttu-id="69def-113">В поле **Имя псевдонима** введите имя для псевдонима.</span><span class="sxs-lookup"><span data-stu-id="69def-113">In the **Alias Name** box, type the name of the alias.</span></span> <span data-ttu-id="69def-114">Клиентские приложения будут пользоваться этим именем при установлении соединения.</span><span class="sxs-lookup"><span data-stu-id="69def-114">Client applications use this name when they connect.</span></span>  
  
3.  <span data-ttu-id="69def-115">В поле **Сервер** введите имя или IP-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="69def-115">In the **Server** box, type the name or IP address of a server.</span></span> <span data-ttu-id="69def-116">Для именованного экземпляра добавьте имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="69def-116">For a named instance append the instance name.</span></span>  
  
4.  <span data-ttu-id="69def-117">В поле **Протокол** выберите протокол, применяемый для данного псевдонима.</span><span class="sxs-lookup"><span data-stu-id="69def-117">In the **Protocol** box, select the protocol used for this alias.</span></span> <span data-ttu-id="69def-118">При выборе протокола заголовок окна дополнительных свойств меняется на «Номер порта», «Имя канала» или «Строка соединения».</span><span class="sxs-lookup"><span data-stu-id="69def-118">Selecting a protocol, changes the title of the optional properties box to Port No, Pipe Name, or Connection String.</span></span>  
  
 <span data-ttu-id="69def-119">Строки подключения, описанные в справке диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , могут оказаться полезными для программистов, создающих собственные строки подключений.</span><span class="sxs-lookup"><span data-stu-id="69def-119">The connection strings described in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help can be useful for programmers who create their own connection strings.</span></span> <span data-ttu-id="69def-120">Чтобы получить доступ к этим данным, в диалоговом окне **Создание псевдонима** нажмите клавишу F1 или кнопку **Справка**.</span><span class="sxs-lookup"><span data-stu-id="69def-120">To access this information, in the **New Alias** dialog box, press F1, or click **Help**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69def-121">Если созданный псевдоним соединяется с неверным сервером или экземпляром, отключите и затем повторно включите соответствующий сетевой протокол.</span><span class="sxs-lookup"><span data-stu-id="69def-121">If a configured alias is connecting to the wrong server or instance, disable and then reenable the associated network protocol.</span></span> <span data-ttu-id="69def-122">Это позволит очистить находящиеся в кэше сведения о соединении и произвести подключение клиента правильно.</span><span class="sxs-lookup"><span data-stu-id="69def-122">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>  
  
#### <a name="to-delete-an-alias"></a><span data-ttu-id="69def-123">Удаление псевдонима</span><span class="sxs-lookup"><span data-stu-id="69def-123">To delete an alias</span></span>  
  
1.  <span data-ttu-id="69def-124">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разверните узел **Конфигурация SQL Server Native Client**и выберите **Псевдонимы**.</span><span class="sxs-lookup"><span data-stu-id="69def-124">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, and then click **Aliases**.</span></span>  
  
2.  <span data-ttu-id="69def-125">На панели сведений щелкните правой кнопкой мыши псевдоним, который необходимо удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="69def-125">In the details pane, right-click the alias that you want to delete, and then click **Delete**.</span></span>  
  
  
