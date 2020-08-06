---
title: Выполните действия после установки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665175"
---
# <a name="complete-the-post-installation-steps"></a><span data-ttu-id="cf063-102">Выполнение действий после установки</span><span class="sxs-lookup"><span data-stu-id="cf063-102">Complete the Post-Installation Steps</span></span>
  <span data-ttu-id="cf063-103">После установки компонента распределенного воспроизведения следует изменить учетные записи служб клиента и контроллера распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="cf063-103">After you install Distributed Replay you must modify the Distributed Replay controller and client services accounts.</span></span>  
  
### <a name="to-complete-the-post-installation-steps"></a><span data-ttu-id="cf063-104">Выполнение действий после установки</span><span class="sxs-lookup"><span data-stu-id="cf063-104">To complete the post-installation steps</span></span>  
  
1.  <span data-ttu-id="cf063-105">**Создание правил брандмауэра**. На компьютерах контроллера и клиента в брандмауэре необходимо разрешить входящий трафик для соответствующей службы.</span><span class="sxs-lookup"><span data-stu-id="cf063-105">**Create firewall rules**: On the controller and client computers, you must allow inbound traffic through the firewall for the corresponding service.</span></span> <span data-ttu-id="cf063-106">Укажите правила брандмауэра для исполняемых файлов службы, расположенных в установочных папках.</span><span class="sxs-lookup"><span data-stu-id="cf063-106">Specify the firewall rules for the service executables, located in the installation folders.</span></span>  
  
    1.  <span data-ttu-id="cf063-107">Для службы контроллера создайте правило для файла **DReplayController.exe**, расположенного в папке установки.</span><span class="sxs-lookup"><span data-stu-id="cf063-107">For the controller service, create a rule for **DReplayController.exe**, located in the installation folder.</span></span> <span data-ttu-id="cf063-108">Например, следующая команда включает это правило, где `%InstallPath%` — папка установки службы:</span><span class="sxs-lookup"><span data-stu-id="cf063-108">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  <span data-ttu-id="cf063-109">Для службы клиента на каждом клиентском компьютере создайте правило для файла **DReplayClient.exe**, расположенного в папке установки.</span><span class="sxs-lookup"><span data-stu-id="cf063-109">For the client service, on each client computer, create a rule for **DReplayClient.exe**, located in the installation folder.</span></span> <span data-ttu-id="cf063-110">Например, следующая команда включает это правило, где `%InstallPath%` — папка установки службы:</span><span class="sxs-lookup"><span data-stu-id="cf063-110">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  <span data-ttu-id="cf063-111">**Предоставьте каждому клиенту разрешения на целевом сервере**. После завершения установки службы клиента на клиентских компьютерах следует вручную добавить учетные записи службы клиента в роль системного администратора на целевом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf063-111">**Grant each client permissions on the target server**: After you have completed installing the client service on the client computers, you must manually add the client service accounts to the sysadmin role on the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cf063-112">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf063-112">.NET Framework Security</span></span>  
 <span data-ttu-id="cf063-113">Для установки компонентов распределенного воспроизведения необходимо обладать разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="cf063-113">You must have administrative permissions in order to install any of the Distributed Replay features.</span></span> <span data-ttu-id="cf063-114">Только имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с разрешениями sysadmin может добавлять учетные записи службы клиента в роль sysadmin тестового сервера.</span><span class="sxs-lookup"><span data-stu-id="cf063-114">Only a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login having sysadmin permissions can add the client service accounts to the sysadmin server role of the test server.</span></span> <span data-ttu-id="cf063-115">Дополнительные сведения о вопросах безопасности распределенного воспроизведения см. в разделе [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="cf063-115">For more information about Distributed Replay security considerations, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
  
