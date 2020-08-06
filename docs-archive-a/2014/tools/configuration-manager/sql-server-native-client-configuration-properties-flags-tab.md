---
title: Свойства конфигурации SQL Server Native Client (вкладка "Флаги") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3ca7b87963fc3848bbb933a5c21f9d608d37d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667971"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a><span data-ttu-id="84a65-102">Свойства конфигурации собственного клиента SQL Server (вкладка «Флаги»)</span><span class="sxs-lookup"><span data-stu-id="84a65-102">SQL Server Native Client Configuration Properties (Flags Tab)</span></span>
  <span data-ttu-id="84a65-103">Клиенты [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на этом компьютере связываются с серверами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи протоколов, предоставляемых файлом библиотеки нативного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84a65-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this machine, communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers using the protocols provided in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client library file.</span></span> <span data-ttu-id="84a65-104">На этой странице можно настроить компьютер клиента на запрос зашифрованного соединения на основе протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="84a65-104">This page provides configures the client computer to request an encrypted connection using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="84a65-105">Если не удается установить зашифрованное соединение, подключение завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="84a65-105">If an encrypted connection cannot be established, the connection will fail.</span></span>  
  
 <span data-ttu-id="84a65-106">Процесс входа в систему всегда шифруется.</span><span class="sxs-lookup"><span data-stu-id="84a65-106">The login process is always encrypted.</span></span> <span data-ttu-id="84a65-107">Указанные далее параметры применимы только к шифрованию данных.</span><span class="sxs-lookup"><span data-stu-id="84a65-107">The options below apply only to encrypting data.</span></span> <span data-ttu-id="84a65-108">Дополнительные сведения о том, как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет шифрование обмена данными, а также инструкции по настройке клиента на доверие к корневому центру сертификата сервера см. в статьях "Шифрование соединений с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" и "Инструкции. Включение зашифрованных соединений с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] (диспетчер конфигурации[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] )" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84a65-108">For more information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encrypts communication and for instructions on how to configure the client to trust the root authority of the server certificate, see "Encrypting Connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" and "How to: Enable Encrypted Connections to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="84a65-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="84a65-109">Options</span></span>  
 <span data-ttu-id="84a65-110">**Принудительное шифрование протокола**</span><span class="sxs-lookup"><span data-stu-id="84a65-110">**Force protocol encryption**</span></span>  
 <span data-ttu-id="84a65-111">Запрос соединения с использованием SSL.</span><span class="sxs-lookup"><span data-stu-id="84a65-111">Request a connection using SSL.</span></span>  
  
 <span data-ttu-id="84a65-112">**Надежный сертификат сервера**</span><span class="sxs-lookup"><span data-stu-id="84a65-112">**Trust Server Certificate**</span></span>  
 <span data-ttu-id="84a65-113">При установке значения **Нет**клиентский процесс выполняет попытку проверки сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="84a65-113">When set to **No**, the client process attempts to validate the server certificate.</span></span> <span data-ttu-id="84a65-114">И клиент, и сервер должны обладать сертификатами, выданными общим центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="84a65-114">The client and server must have each have a certificate issues from a public certification authority.</span></span> <span data-ttu-id="84a65-115">Если на компьютере клиента нет сертификата или если проверка сертификата заканчивается неудачей, соединение закрывается.</span><span class="sxs-lookup"><span data-stu-id="84a65-115">If the certificate is not present on the client computer, or if the validation of the certificate fails, the connection is terminated.</span></span>  
  
 <span data-ttu-id="84a65-116">При установке значения **Да**клиент не проверяет сертификат сервера, тем самым позволяя использовать самозаверяющий сертификат.</span><span class="sxs-lookup"><span data-stu-id="84a65-116">When set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span>  
  
 <span data-ttu-id="84a65-117">Флаг**Доверять сертификату сервера** используется, только если флаг **Принудительное шифрование протокола** имеет значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="84a65-117">**Trust Server Certificate** is only available if **Force protocol encryption** is set to **Yes**.</span></span>  
  
  
