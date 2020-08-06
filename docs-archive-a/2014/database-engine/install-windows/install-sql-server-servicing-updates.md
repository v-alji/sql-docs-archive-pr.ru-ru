---
title: Установка обновлений для обслуживания SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace0fd187386d9a9d96e82f61d1efaa254f08c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729754"
---
# <a name="install-sql-server-2014-servicing-updates"></a><span data-ttu-id="4295e-102">Установка обновлений для обслуживания SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4295e-102">Install SQL Server 2014 Servicing Updates</span></span>
  <span data-ttu-id="4295e-103">В этом разделе описывается установка обновлений для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4295e-103">This topic provides information about installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4295e-104">В разделе рассматриваются следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="4295e-104">This section provides information about the following:</span></span>  
  
-   <span data-ttu-id="4295e-105">Установка обновлений для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при установке нового экземпляра</span><span class="sxs-lookup"><span data-stu-id="4295e-105">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] during a new installation</span></span>  
  
-   <span data-ttu-id="4295e-106">Установка обновлений для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] после установки экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4295e-106">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed.</span></span>  
  
 <span data-ttu-id="4295e-107">Пользователям рекомендуется своевременно оценивать и устанавливать последние обновления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы обеспечить наличие последних обновлений безопасности для систем.</span><span class="sxs-lookup"><span data-stu-id="4295e-107">We recommend that customers evaluate and install latest [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates in a timely manner to make sure that systems are up-to-date with the most recent security updates.</span></span>  
  
## <a name="installing-updates-for-sscurrent-during-a-new-installation"></a><span data-ttu-id="4295e-108">Установка обновлений для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при установке нового экземпляра</span><span class="sxs-lookup"><span data-stu-id="4295e-108">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] During a New Installation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4295e-109">объединяет последние обновления продукта с установкой основного продукта, чтобы он и применимые обновления устанавливались одновременно.</span><span class="sxs-lookup"><span data-stu-id="4295e-109">setup integrates the latest product updates with the main product installation so that the main product and its applicable updates are installed at the same time.</span></span> <span data-ttu-id="4295e-110">Функция обновления продукта может искать подходящие обновления в следующих источниках.</span><span class="sxs-lookup"><span data-stu-id="4295e-110">Product Update can search for the applicable updates from:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4295e-111">Update</span><span class="sxs-lookup"><span data-stu-id="4295e-111">Update</span></span>  
  
-   <span data-ttu-id="4295e-112">Службы Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="4295e-112">Windows Server Update Services (WSUS)</span></span>  
  
-   <span data-ttu-id="4295e-113">Локальная папка</span><span class="sxs-lookup"><span data-stu-id="4295e-113">A local folder</span></span>  
  
-   <span data-ttu-id="4295e-114">Сетевая папка</span><span class="sxs-lookup"><span data-stu-id="4295e-114">A network share</span></span>  
  
 <span data-ttu-id="4295e-115">Когда программа установки обнаруживает последние версии соответствующих обновлений, эти обновления загружаются и интегрируются в текущую процедуру установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4295e-115">After Setup finds the latest versions of the applicable updates, it downloads and integrates them with the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup process.</span></span> <span data-ttu-id="4295e-116">Функция обновления продукта может включить в установку пакет обновления, накопительное обновление или и то и другое.</span><span class="sxs-lookup"><span data-stu-id="4295e-116">Product Update can include a cumulative update, service pack, or service pack plus cumulative update.</span></span> <span data-ttu-id="4295e-117">Функция обновления продукта является расширением [функции интегрированной установки](https://go.microsoft.com/fwlink/?LinkId=219945) , существовавшей в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span><span class="sxs-lookup"><span data-stu-id="4295e-117">Product Update functionality is an extension of the [Slipstream Functionality](https://go.microsoft.com/fwlink/?LinkId=219945) that was available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span></span>  
  
## <a name="installing-updates-for-sscurrent-after-it-has-already-been-installed"></a><span data-ttu-id="4295e-118">Установка обновлений для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] после установки экземпляра</span><span class="sxs-lookup"><span data-stu-id="4295e-118">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed</span></span>  
 <span data-ttu-id="4295e-119">На установленном экземпляре [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] рекомендуется применить все доступные обновления: выпуски общего распространения (GDR-Security/критические обновления), пакеты обновления (SP), а также Последнее доступное накопительное обновление (Cu).</span><span class="sxs-lookup"><span data-stu-id="4295e-119">On an installed instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you apply all available updates: General Distribution Releases (GDR - security/critical updates), Service Packs (SP), as well as the latest available Cumulative Update (CU).</span></span>  
  
 <span data-ttu-id="4295e-120">В зависимости от типа выпуска для обслуживания SQL Server обновления доступны через Центр обновления Майкрософт (MU), центра загрузки Майкрософт и (или) сервера исправлений службы поддержки пользователей.</span><span class="sxs-lookup"><span data-stu-id="4295e-120">Depending on the type of servicing release, SQL Server updates are available via Microsoft Update (MU), the Microsoft Download Center, and/or the Customer Support Services hotfix Server.</span></span> <span data-ttu-id="4295e-121">Обновления для системы безопасности и критических обновлений для SQL Server автоматически предоставляются Центр обновления Майкрософт (чтобы они могли видеть эти обновления, необходимо принять участие в программе MU через Центр обновления Windows на панели управления).</span><span class="sxs-lookup"><span data-stu-id="4295e-121">Security and Critical updates for SQL Server are automatically provided by Microsoft Update (to be able to see these updates you need to opt-in to MU through Windows Update in Control panel).</span></span> <span data-ttu-id="4295e-122">Пакеты обновления доступны в виде необязательных или важных загружаемых файлов, а также в центре загрузки.</span><span class="sxs-lookup"><span data-stu-id="4295e-122">Service Packs are available on MU as Optional/Important downloads as well as the Download Center.</span></span> <span data-ttu-id="4295e-123">Накопительные обновления доступны на сервере загрузки исправлений Майкрософт, приведенном в статьях базы знаний CU.</span><span class="sxs-lookup"><span data-stu-id="4295e-123">Cumulative updates are available on the Microsoft hotfix download server provided in CU Knowledge Base articles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4295e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="4295e-124">See Also</span></span>  
 <span data-ttu-id="4295e-125">[Установка SQL Server 2014 с помощью мастера установки &#40;установки&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="4295e-125">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 <span data-ttu-id="4295e-126">[Установка обновлений из командной строки](installing-updates-from-the-command-prompt.md) [Добавление компонентов в экземпляр компонента SQL Server 2014 &#40;установки&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span><span class="sxs-lookup"><span data-stu-id="4295e-126">[Installing updates from the command prompt](installing-updates-from-the-command-prompt.md) [Add Features to an Instance of SQL Server 2014 &#40;Setup&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span></span>  
 [<span data-ttu-id="4295e-127">Удаление установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4295e-127">Drop a SQL Server 2014 Installation</span></span>](repair-a-failed-sql-server-installation.md)  
  
  
