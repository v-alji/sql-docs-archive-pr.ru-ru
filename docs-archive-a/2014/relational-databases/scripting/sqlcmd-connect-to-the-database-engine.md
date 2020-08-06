---
title: Подключение к компоненту Database Engine при помощи программы sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sqlcmd utility, Database Engine connections
- Named Pipes [SQL Server], sqlcmd utility
- TCP/IP [SQL Server], client protocols
- network protocols [SQL Server], sqlcmd utility
- protocols [SQL Server], sqlcmd utility
- VIA
- client protocols [SQL Server]
ms.assetid: 74b0fb71-7f8e-4171-9431-d07528532524
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b409683b651e3e6508baced5eb3bc9fcc631e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656304"
---
# <a name="connect-to-the-database-engine-with-sqlcmd"></a><span data-ttu-id="5afd0-102">Подключение к компоненту Database Engine при помощи программы sqlcmd</span><span class="sxs-lookup"><span data-stu-id="5afd0-102">Connect to the Database Engine With sqlcmd</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5afd0-103">поддерживает клиентское подключение при помощи сетевого протокола TCP/IP (по умолчанию) и протокола именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="5afd0-103">supports client communication with the TCP/IP network protocol (the default), and the named pipes protocol.</span></span> <span data-ttu-id="5afd0-104">Может также использоваться протокол общей памяти, если клиент устанавливает соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="5afd0-104">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="5afd0-105">Существуют три наиболее часто используемых способа для выбора протокола.</span><span class="sxs-lookup"><span data-stu-id="5afd0-105">There are three common methods of selecting the protocol.</span></span> <span data-ttu-id="5afd0-106">Протокол, используемый служебной программой **sqlcmd** , определяется в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="5afd0-106">The protocol used by the **sqlcmd** utility is determined in the following order:</span></span>  
  
-   <span data-ttu-id="5afd0-107">Служебная программа**sqlcmd** использует протокол, который указан в составе строки подключения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5afd0-107">**sqlcmd** uses the protocol specified as part of the connection string as described below.</span></span>  
  
-   <span data-ttu-id="5afd0-108">Если в строке подключения не указан протокол, программа **sqlcmd** использует протокол, определенный как часть псевдонима, к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="5afd0-108">If no protocol is specified as part the connection string, **sqlcmd** will use the protocol defined as part of the alias that it is connecting to.</span></span> <span data-ttu-id="5afd0-109">Инструкции по настройке **sqlcmd** для использования определенного сетевого протокола при помощи создания псевдонима см. в статье [Создание или удаление псевдонима сервера для использования клиентом (диспетчер конфигурации SQL Server)](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="5afd0-109">To configure **sqlcmd** to use a specific network protocol by creating an alias, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="5afd0-110">Если протокол не задается каким-либо иным образом, программа **sqlcmd** использует сетевой протокол, определяемый порядком протоколов в диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5afd0-110">If the protocol is not specified in some other way, **sqlcmd** will use the network protocol determined by the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
 <span data-ttu-id="5afd0-111">В следующих примерах демонстрируются различные способы соединения с экземпляром по умолчанию компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] через порт 1433 и с именованными экземплярами компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , которые прослушивают порт 1691.</span><span class="sxs-lookup"><span data-stu-id="5afd0-111">The following examples show various ways of connecting to the default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] on port 1433, and named instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] presumed to be listening on port 1691.</span></span> <span data-ttu-id="5afd0-112">В некоторых этих примерах используется IP-адрес адаптера замыкания на себя (127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="5afd0-112">Some of these examples use the IP address of the loopback adapter (127.0.0.1).</span></span> <span data-ttu-id="5afd0-113">Проведите проверку при помощи IP-адреса сетевой интерфейсной платы компьютера.</span><span class="sxs-lookup"><span data-stu-id="5afd0-113">Test using the IP address of your computer network interface card.</span></span>  
  
 <span data-ttu-id="5afd0-114">Подключение к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] с заданием имени экземпляра:</span><span class="sxs-lookup"><span data-stu-id="5afd0-114">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the instance name:</span></span>  
  
```  
sqlcmd -S ComputerA  
sqlcmd -S ComputerA\instanceB  
```  
  
 <span data-ttu-id="5afd0-115">Подключение к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] с указанием IP-адреса:</span><span class="sxs-lookup"><span data-stu-id="5afd0-115">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the IP address:</span></span>  
  
```  
sqlcmd -S 127.0.0.1  
sqlcmd -S 127.0.0.1\instanceB  
```  
  
 <span data-ttu-id="5afd0-116">Подключение к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] с указанием порта TCP/IP:</span><span class="sxs-lookup"><span data-stu-id="5afd0-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by specifying the TCP\IP port number:</span></span>  
  
```  
sqlcmd -S ComputerA,1433  
sqlcmd -S ComputerA,1691  
sqlcmd -S 127.0.0.1,1433  
sqlcmd -S 127.0.0.1,1691  
```  
  
### <a name="to-connect-using-tcpip"></a><span data-ttu-id="5afd0-117">Подключение по протоколу TCP/IP</span><span class="sxs-lookup"><span data-stu-id="5afd0-117">To connect using TCP/IP</span></span>  
  
-   <span data-ttu-id="5afd0-118">Подключение производится с помощью следующего общего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="5afd0-118">Connect using the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S tcp:<computer name>,<port number>  
    ```  
  
-   <span data-ttu-id="5afd0-119">Подключение к экземпляру по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="5afd0-119">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1433  
    sqlcmd -S tcp:127.0.0.1,1433  
    ```  
  
-   <span data-ttu-id="5afd0-120">Подключение к именованному экземпляру:</span><span class="sxs-lookup"><span data-stu-id="5afd0-120">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S tcp:ComputerA,1691  
    sqlcmd -S tcp:127.0.0.1,1691  
    ```  
  
### <a name="to-connect-using-named-pipes"></a><span data-ttu-id="5afd0-121">Подключение через именованные каналы</span><span class="sxs-lookup"><span data-stu-id="5afd0-121">To connect using named pipes</span></span>  
  
-   <span data-ttu-id="5afd0-122">Подключитесь, используя один из следующих вариантов синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="5afd0-122">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S np:\\<computer name>\<pipe name>  
    ```  
  
-   <span data-ttu-id="5afd0-123">Подключение к экземпляру по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="5afd0-123">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\sql\query  
    ```  
  
-   <span data-ttu-id="5afd0-124">Подключение к именованному экземпляру:</span><span class="sxs-lookup"><span data-stu-id="5afd0-124">Connect to a named instance instance:</span></span>  
  
    ```  
    sqlcmd -S np:\\ComputerA\pipe\MSSQL$<instancename>\sql\query  
    sqlcmd -S np:\\127.0.0.1\pipe\MSSQL$<instancename>\sql\query  
    ```  
  
### <a name="to-connect-using-shared-memory-a-local-procedure-call-from-a-client-on-the-server"></a><span data-ttu-id="5afd0-125">Подключение через общую память (вызов локальной процедуры) из клиента на сервере</span><span class="sxs-lookup"><span data-stu-id="5afd0-125">To connect using shared memory (a local procedure call) from a client on the server</span></span>  
  
-   <span data-ttu-id="5afd0-126">Подключитесь, используя один из следующих вариантов синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="5afd0-126">Connect using one of the following general syntax:</span></span>  
  
    ```  
    sqlcmd -S lpc:<computer name>  
    ```  
  
-   <span data-ttu-id="5afd0-127">Подключение к экземпляру по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="5afd0-127">Connect to the default instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA  
    ```  
  
-   <span data-ttu-id="5afd0-128">Подключение к именованному экземпляру:</span><span class="sxs-lookup"><span data-stu-id="5afd0-128">Connect to a named instance:</span></span>  
  
    ```  
    sqlcmd -S lpc:ComputerA\<instancename>  
    ```  
  
  
