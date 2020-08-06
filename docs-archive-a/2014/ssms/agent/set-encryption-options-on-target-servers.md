---
title: Установка параметров шифрования на целевых серверах | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd10d2e05e59015542f41cc123de993e6128f9f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667538"
---
# <a name="set-encryption-options-on-target-servers"></a><span data-ttu-id="5a6d8-102">Установка параметров шифрования на целевых серверах</span><span class="sxs-lookup"><span data-stu-id="5a6d8-102">Set Encryption Options on Target Servers</span></span>
  <span data-ttu-id="5a6d8-103">Если нельзя использовать сертификат для шифрованной связи по протоколу SSL между главными серверами и некоторыми или всеми целевыми серверами, но канал между ними необходимо шифровать, настройте целевой сервер на использование необходимого уровня безопасности.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-103">If you cannot use a certificate for Secure Sockets Layer (SSL) encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.</span></span>  
  
 <span data-ttu-id="5a6d8-104">Чтобы настроить соответствующий уровень безопасности, необходимый для конкретного канала связи главного сервера или целевого сервера, задайте [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для подраздела реестра агента \*\*\ HKEY_LOCAL_MACHINE \софтваре\микрософт\микрософт SQL Server \\ \*\* \<*instance_name*> **\склсерверажент\мсксенкриптчаннелоптионс (REG_DWORD)** на целевом сервере одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-104">To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values.</span></span> <span data-ttu-id="5a6d8-105">Значение \<*instance_name*> равно **MSSQL.** _n_.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-105">The value of \<*instance_name*> is **MSSQL.**_n_.</span></span> <span data-ttu-id="5a6d8-106">Например, **MSSQL.1** или **MSSQL.3**.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-106">For example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
|<span data-ttu-id="5a6d8-107">Значение</span><span class="sxs-lookup"><span data-stu-id="5a6d8-107">Value</span></span>|<span data-ttu-id="5a6d8-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5a6d8-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a6d8-109">**0**</span><span class="sxs-lookup"><span data-stu-id="5a6d8-109">**0**</span></span>|<span data-ttu-id="5a6d8-110">Отключает шифрование между данным целевым сервером и главным сервером.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-110">Disables encryption between this target server and the master server.</span></span> <span data-ttu-id="5a6d8-111">Выберите этот параметр, только если канал между целевым и главным сервером защищен другими средствами.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-111">Choose this option only when the channel between the target server and master server is secured by another means.</span></span>|  
|<span data-ttu-id="5a6d8-112">**1**</span><span class="sxs-lookup"><span data-stu-id="5a6d8-112">**1**</span></span>|<span data-ttu-id="5a6d8-113">Включает шифрование только между этим целевым сервером и главным сервером, но никакая проверка сертификата не нужна.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-113">Enables encryption only between this target server and the master server, but no certificate validation is required.</span></span>|  
|<span data-ttu-id="5a6d8-114">**2**</span><span class="sxs-lookup"><span data-stu-id="5a6d8-114">**2**</span></span>|<span data-ttu-id="5a6d8-115">Включает полное шифрование SSL и проверку сертификата между этим целевым сервером и главным сервером.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-115">Enables full SSL encryption and certificate validation between this target server and the master server.</span></span> <span data-ttu-id="5a6d8-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-116">This setting is the default.</span></span> <span data-ttu-id="5a6d8-117">Если нет особой причины использовать другое значение, рекомендуется его не изменять.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-117">Unless you have specific reason to choose a different value, we recommend not changing it.</span></span>|  
  
 <span data-ttu-id="5a6d8-118">Если задано **1** или **2** , необходимо, чтобы SSL-шифрование было включено и на главном, и на целевом серверах.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-118">If **1** or **2** is specified, you must have SSL enabled on both the master and target servers.</span></span> <span data-ttu-id="5a6d8-119">Если задано значение **2** , необходимо, чтобы на главном сервере присутствовал сертификат, подписанный должным образом.</span><span class="sxs-lookup"><span data-stu-id="5a6d8-119">If **2** is specified, you must also have a properly signed certificate present on the master server.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a6d8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a6d8-120">See Also</span></span>  
 [<span data-ttu-id="5a6d8-121">Включение шифрования соединений в компоненте Database Engine (диспетчер конфигураций SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5a6d8-121">Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)  
  
  
