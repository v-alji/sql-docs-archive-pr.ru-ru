---
title: Работа с поставщиком WMI для управления конфигурацией | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- WMI Provider for Configuration Management, connection strings
- WMI Provider for Configuration Management, security
- late binding [WMI]
- WMI Provider for Configuration Management, late binding
- binding [WMI]
ms.assetid: 34daa922-7074-41d0-9077-042bb18c222a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80f311fb0abae2337f6ea4a5d5d85aaa0d320b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664058"
---
# <a name="working-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="a2e97-102">Работа с поставщиком WMI для управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="a2e97-102">Working with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="a2e97-103">Перед тем как приступить к программированию с помощью поставщика WMI для управления компьютером, примите во внимание следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="a2e97-103">Consider the following before programming with the WMI Provider for Computer Management:</span></span>  
  
## <a name="binding"></a><span data-ttu-id="a2e97-104">Привязка</span><span class="sxs-lookup"><span data-stu-id="a2e97-104">Binding</span></span>  
 <span data-ttu-id="a2e97-105">Поставщик WMI для управления компьютером является моделью объектов COM, он поддерживает раннее и позднее связывания.</span><span class="sxs-lookup"><span data-stu-id="a2e97-105">The WMI Provider for Configuration Management is a COM object model and it supports early and late binding.</span></span> <span data-ttu-id="a2e97-106">В случае позднего связывания при помощи таких языков скриптов, как VBScript, можно программно управлять службами, параметрами сети и псевдонимами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2e97-106">With late binding you can use script languages, such as VBScript, to manipulate the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and aliases programmatically.</span></span>  
  
 <span data-ttu-id="a2e97-107">Дополнительные сведения о программировании поставщиков WMI с помощью языков сценариев см [!INCLUDE[msCoName](../../includes/msconame-md.md)] . на [веб-сайте](https://go.microsoft.com/fwlink/?linkid=15426)MSDN.</span><span class="sxs-lookup"><span data-stu-id="a2e97-107">For further information about programming WMI Provider implementations using scripting languages, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="specifying-a-connection-string"></a><span data-ttu-id="a2e97-108">Задание строки соединения</span><span class="sxs-lookup"><span data-stu-id="a2e97-108">Specifying a Connection String</span></span>  
 <span data-ttu-id="a2e97-109">Приложения направляют поставщика WMI для управления конфигурацией к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] путем соединения с пространством имен WMI, определенным поставщиком.</span><span class="sxs-lookup"><span data-stu-id="a2e97-109">Applications direct the WMI Provider for Configuration Management to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by connecting to a WMI namespace defined by the provider.</span></span> <span data-ttu-id="a2e97-110">Служба Windows WMI сопоставляет это пространство имен с файлом DLL поставщика и загружает его в память.</span><span class="sxs-lookup"><span data-stu-id="a2e97-110">The Windows WMI service maps this namespace to the provider DLL and loads it into memory.</span></span> <span data-ttu-id="a2e97-111">Все экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] представлены одним пространством имен WMI.</span><span class="sxs-lookup"><span data-stu-id="a2e97-111">All instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are represented with a single WMI namespace.</span></span> <span data-ttu-id="a2e97-112">Значение по умолчанию этого пространства имен:</span><span class="sxs-lookup"><span data-stu-id="a2e97-112">The namespace defaults to</span></span>  
  
```  
\\.\root\Microsoft\SqlServer\ComputerManagement12\instance_name  
```  
  
 <span data-ttu-id="a2e97-113">где `instance_name` в установке по умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет значение по умолчанию `MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="a2e97-113">where `instance_name` defaults to `MSSQLSERVER` in a default installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a2e97-114">**Примечание.** При подключении через брандмауэр Windows необходимо убедиться, что компьютеры настроены соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a2e97-114">**Note:** If you are connecting through Windows Firewall you will need to make sure your computers are configured appropriately.</span></span> <span data-ttu-id="a2e97-115">См. статью "подключение через брандмауэр Windows" в документации инструментарий управления Windows (WMI) на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [веб-сайте](https://go.microsoft.com/fwlink/?linkid=15426)MSDN.</span><span class="sxs-lookup"><span data-stu-id="a2e97-115">See the "Connecting Through Windows Firewall" article in the Windows Management Instrumentation documentation on [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="permissions-and-server-authentication"></a><span data-ttu-id="a2e97-116">Разрешения и проверка подлинности сервера</span><span class="sxs-lookup"><span data-stu-id="a2e97-116">Permissions and Server Authentication</span></span>  
 <span data-ttu-id="a2e97-117">Чтобы получить доступ к поставщику WMI для управления конфигурацией, скрипт управления WMI клиента должен выполняться на целевом компьютере в контексте администратора.</span><span class="sxs-lookup"><span data-stu-id="a2e97-117">To access the WMI Provider for Configuration Management, the client WMI management script must be running in the context of an administrator on the target computer.</span></span> <span data-ttu-id="a2e97-118">Необходимо членство в локальной группе администраторов Windows на компьютере, которым требуется управлять.</span><span class="sxs-lookup"><span data-stu-id="a2e97-118">You need to be a member of the local Windows administrators group on the computer you want to manage.</span></span>  
  
 <span data-ttu-id="a2e97-119">Администратор может задавать групповые политики для управления доступом пользователей к поставщикам WMI.</span><span class="sxs-lookup"><span data-stu-id="a2e97-119">The administrator can set group policies to control user access to WMI providers.</span></span> <span data-ttu-id="a2e97-120">Дополнительные сведения о задании групповых политик см. в разделе «Групповая политика и MMC» в справке по диспетчеру конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2e97-120">For more information about setting group policies see "Group Policy and MMC" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help.</span></span>  
  
 <span data-ttu-id="a2e97-121">При помощи скрипта управления инструментарием WMI можно обновлять учетную запись, под которой выполняются службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2e97-121">The WMI management script can be used to update the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services run.</span></span>  
  
 <span data-ttu-id="a2e97-122">Поставщик WMI для управления конфигурацией поддерживает сертификаты безопасности.</span><span class="sxs-lookup"><span data-stu-id="a2e97-122">Security certificates are supported by the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="a2e97-123">Дополнительные сведения о сертификатах см. в разделе [Иерархия шифрования](../security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="a2e97-123">For more information about certificates, see [Encryption Hierarchy](../security/encryption/encryption-hierarchy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e97-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2e97-124">See Also</span></span>  
 [<span data-ttu-id="a2e97-125">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2e97-125">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
