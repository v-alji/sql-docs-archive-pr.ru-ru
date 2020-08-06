---
title: Установка репликации SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- components [SQL Server replication]
- command line installations [SQL Server replication]
- installing replication
- replication [SQL Server], installing
- command prompt [SQL Server replication]
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ba941fda1d463e7bb4a26bd2fbb45d2a82ca27b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729761"
---
# <a name="install-sql-server-replication"></a><span data-ttu-id="4511e-102">Установка репликации SQL Server</span><span class="sxs-lookup"><span data-stu-id="4511e-102">Install SQL Server Replication</span></span>
  <span data-ttu-id="4511e-103">Компоненты репликации можно установить с помощью мастера установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или через командную строку.</span><span class="sxs-lookup"><span data-stu-id="4511e-103">Replication components can be installed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or at a command prompt.</span></span> <span data-ttu-id="4511e-104">Репликацию можно установить при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]или при изменении существующего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4511e-104">Install replication when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or when you modify an existing instance.</span></span>  
  
 <span data-ttu-id="4511e-105">После установки компонентов репликации необходимо настроить сервер перед началом использования репликации.</span><span class="sxs-lookup"><span data-stu-id="4511e-105">After replication components are installed, you must configure the server before you can use replication.</span></span> <span data-ttu-id="4511e-106">Дополнительные сведения см. в разделе [Настройка распространения](../../relational-databases/replication/configure-distribution.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4511e-106">For more information, see [Configure Distribution](../../relational-databases/replication/configure-distribution.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4511e-107">Если при изменении существующего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]устанавливаются компоненты репликации, то после завершения установки необходимо перезапустить агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4511e-107">If you install replication components when you modify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent after the installation is completed.</span></span> <span data-ttu-id="4511e-108">Это действие гарантирует, что агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] распознает подсистемы агента репликации и сможет обращаться к агентам репликации из шагов задания.</span><span class="sxs-lookup"><span data-stu-id="4511e-108">This action helps ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent recognizes the replication agent subsystems and can call replication agents from job steps.</span></span>  
  
## <a name="installing-replication-by-using-setup"></a><span data-ttu-id="4511e-109">Установка репликации с помощью программы установки</span><span class="sxs-lookup"><span data-stu-id="4511e-109">Installing Replication by Using Setup</span></span>  
 <span data-ttu-id="4511e-110">**Установка репликации при установке нового экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="4511e-110">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="4511e-111">Чтобы установить компоненты репликации, включая объекты RMO, на странице **Выбор компонентов** мастера установки выберите **Репликация SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="4511e-111">To install replication components, including Replication Management Objects (RMO), select **SQL Server Replication** on the **Feature Selection** page of the Installation Wizard.</span></span>  
  
## <a name="installing-replication-from-the-command-prompt"></a><span data-ttu-id="4511e-112">Установка репликации из командной строки</span><span class="sxs-lookup"><span data-stu-id="4511e-112">Installing Replication from the Command Prompt</span></span>  
 <span data-ttu-id="4511e-113">**Установка репликации при установке нового экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="4511e-113">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="4511e-114">См. раздел [Install SQL Server 2014 из командной строки](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="4511e-114">See [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4511e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="4511e-115">See Also</span></span>  
 <span data-ttu-id="4511e-116">[Установка SQL Server 2014](install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4511e-116">[Install SQL Server 2014](install-sql-server.md) </span></span>  
 <span data-ttu-id="4511e-117">[Установка SQL Server 2014 из командной строки](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="4511e-117">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 [<span data-ttu-id="4511e-118">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4511e-118">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
