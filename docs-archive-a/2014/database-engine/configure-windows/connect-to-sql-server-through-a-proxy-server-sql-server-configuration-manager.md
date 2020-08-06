---
title: Подключение к SQL Server через прокси-сервер (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Remote WinSock
- RWS
- LATs
- proxy servers [SQL Server]
- connections [SQL Server], proxy server
- Microsoft Proxy Server [SQL Server]
- local address tables [SQL Server]
ms.assetid: 39714de0-2a1f-4179-9091-5c3fa4612545
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: de22ad6043c509f08471a6bea40c0efa18d76842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665545"
---
# <a name="connect-to-sql-server-through-a-proxy-server-sql-server-configuration-manager"></a><span data-ttu-id="76b13-102">Подключение к SQL Server через прокси-сервер (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="76b13-102">Connect to SQL Server Through a Proxy Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="76b13-103">В этом разделе описано, как в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] установить соединение с SQL Server через прокси-сервер с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76b13-103">This topic describes how to connect to SQL Server through a proxy server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="76b13-104">Для удаленного прослушивания прокси-сервером Remote WinSock (RWS) определите таблицу локальных адресов (LAT) для прокси-сервера таким образом, чтобы адрес прослушивающего узла находился вне диапазона записей LAT.</span><span class="sxs-lookup"><span data-stu-id="76b13-104">To listen remotely by way of Remote WinSock (RWS), define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="76b13-105">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="76b13-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-connections-to-sql-server-through-microsoft-proxy-server"></a><span data-ttu-id="76b13-106">Обеспечение соединений с SQL Server с помощью прокси-сервера Microsoft</span><span class="sxs-lookup"><span data-stu-id="76b13-106">To enable connections to SQL Server through Microsoft Proxy Server</span></span>  
  
1.  <span data-ttu-id="76b13-107">Следуйте указаниям в разделе [Настройка сервера для прослушивания указанного TCP-порта (SQL Server Configuration Manager)](configure-a-server-to-listen-on-a-specific-tcp-port.md), чтобы определить, какие TCP/IP-порты используются [!INCLUDE[ssDE](../../includes/ssde-md.md)], или настроить [!INCLUDE[ssDE](../../includes/ssde-md.md)] для использования нужного порта.</span><span class="sxs-lookup"><span data-stu-id="76b13-107">Follow the steps in [Configure a Server to Listen on a Specific TCP Port &#40;SQL Server Configuration Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) to determine which TCP/IP ports are used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to use a desired port.</span></span>  
  
2.  <span data-ttu-id="76b13-108">В прокси-сервере определите таблицу локальных адресов (LAT) для прокси-сервера таким образом, чтобы адрес прослушивающего узла находился вне диапазона записей LAT.</span><span class="sxs-lookup"><span data-stu-id="76b13-108">In your proxy server define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span> <span data-ttu-id="76b13-109">Дополнительные сведения см. в документации по прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="76b13-109">For more information, see your proxy server documentation.</span></span>  
  
  
