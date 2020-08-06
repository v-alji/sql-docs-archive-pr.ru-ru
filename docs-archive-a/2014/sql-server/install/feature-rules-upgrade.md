---
title: Правила компонентов (обновление) | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 653b15db-a984-4b4b-b224-81b0285b099b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0527c1ba26fed86a6c1a3d3a2ea7c11b096474f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666400"
---
# <a name="feature-rules-upgrade"></a><span data-ttu-id="e43ab-102">Правила компонентов (обновление)</span><span class="sxs-lookup"><span data-stu-id="e43ab-102">Feature Rules (Upgrade)</span></span>
  <span data-ttu-id="e43ab-103">Программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверяет конфигурацию компьютера перед началом установки.</span><span class="sxs-lookup"><span data-stu-id="e43ab-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="e43ab-104">Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] система сканирует компьютер, на котором устанавливается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и проверяет условия, препятствующие успешному выполнению операции установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e43ab-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the system scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed and checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="e43ab-105">Прежде чем программа установки запустит мастер обновления, она получает сведения о состоянии каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="e43ab-105">Before Setup starts the upgrade wizard, it retrieves the status of each item.</span></span> <span data-ttu-id="e43ab-106">Затем оно сравнивает результаты с требуемыми условиями и предоставляет рекомендации по устранению критических препятствий.</span><span class="sxs-lookup"><span data-stu-id="e43ab-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="e43ab-107">При проверке конфигурации системы создается отчет, содержащий краткое описание всех выполненных правил и состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="e43ab-107">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="e43ab-108">Отчет о проверке конфигурации системы находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="e43ab-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="e43ab-109">Прежде чем начинать установку, ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="e43ab-109">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="e43ab-110">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e43ab-110">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="e43ab-111">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e43ab-111">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="e43ab-112">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="e43ab-112">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="e43ab-113">Версии SQL Server на местных языках</span><span class="sxs-lookup"><span data-stu-id="e43ab-113">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="e43ab-114">Другие ссылки:</span><span class="sxs-lookup"><span data-stu-id="e43ab-114">Other references:</span></span>  
  
1.  [<span data-ttu-id="e43ab-115">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="e43ab-115">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="e43ab-116">Подготовка к установке отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="e43ab-116">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="e43ab-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e43ab-117">See Also</span></span>  
 [<span data-ttu-id="e43ab-118">Установка правил</span><span class="sxs-lookup"><span data-stu-id="e43ab-118">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
