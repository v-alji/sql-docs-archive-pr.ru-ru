---
title: Мастер SQL Server отказоустойчивого кластера — подготовка | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c446730a-cc71-4aaa-b142-99fd004ffb1a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 6847c8c138a45c171e178789be8ff66879e57c28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666341"
---
# <a name="sql-server-failover-cluster-wizard---prepare"></a><span data-ttu-id="7b9d8-102">Мастер отказоустойчивой кластеризации SQL Server — подготовка</span><span class="sxs-lookup"><span data-stu-id="7b9d8-102">SQL Server Failover Cluster Wizard - Prepare</span></span>
  <span data-ttu-id="7b9d8-103">Программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверяет конфигурацию компьютера перед началом установки.</span><span class="sxs-lookup"><span data-stu-id="7b9d8-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="7b9d8-104">Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средство проверки конфигурации системы (SCC) просматривает компьютер, на котором устанавливается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b9d8-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="7b9d8-105">Средство SCC проверяет наличие условий, препятствующих успешной установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b9d8-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="7b9d8-106">Прежде чем программа установки запустит мастер установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , SCC получает сведения о состоянии каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="7b9d8-106">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="7b9d8-107">Затем оно сравнивает результаты с требуемыми условиями и предоставляет рекомендации по устранению критических препятствий.</span><span class="sxs-lookup"><span data-stu-id="7b9d8-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="7b9d8-108">При проверке конфигурации системы создается отчет, содержащий краткое описание всех выполненных правил и состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="7b9d8-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="7b9d8-109">Отчет о проверке конфигурации системы находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="7b9d8-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="7b9d8-110">Прежде чем начинать установку, ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="7b9d8-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="7b9d8-111">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7b9d8-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="7b9d8-112">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7b9d8-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="7b9d8-113">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b9d8-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="7b9d8-114">Версии SQL Server на местных языках</span><span class="sxs-lookup"><span data-stu-id="7b9d8-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="7b9d8-115">Другие ссылки:</span><span class="sxs-lookup"><span data-stu-id="7b9d8-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="7b9d8-116">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="7b9d8-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="7b9d8-117">Подготовка к установке отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="7b9d8-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b9d8-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b9d8-118">See Also</span></span>  
 [<span data-ttu-id="7b9d8-119">Установка правил</span><span class="sxs-lookup"><span data-stu-id="7b9d8-119">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
