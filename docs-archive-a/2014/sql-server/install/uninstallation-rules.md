---
title: Правила удаления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 07554612-8cb6-4bd9-adde-956177261ccd
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c2e1c3e2e36177053a43b032dd4721dc503fa20c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659143"
---
# <a name="uninstallation-rules"></a><span data-ttu-id="60049-102">Правила удаления</span><span class="sxs-lookup"><span data-stu-id="60049-102">Uninstallation rules</span></span>
  <span data-ttu-id="60049-103">Страница правил удаления выполняет набор правил, чтобы гарантировать успешное завершение работы программы установки.</span><span class="sxs-lookup"><span data-stu-id="60049-103">The Uninstallation Rules page will run a set of rules to ensure that the Setup operation can complete successfully.</span></span>  
  
 <span data-ttu-id="60049-104">Программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверяет конфигурацию компьютера перед началом установки.</span><span class="sxs-lookup"><span data-stu-id="60049-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="60049-105">Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средство проверки конфигурации системы (SCC) просматривает компьютер, на котором устанавливается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60049-105">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="60049-106">Средство SCC проверяет наличие условий, препятствующих успешной установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60049-106">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="60049-107">Прежде чем программа установки запустит мастер удаления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , SCC получает сведения о состоянии каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="60049-107">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uninstallation wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="60049-108">Затем оно сравнивает результаты с требуемыми условиями и предоставляет рекомендации по устранению критических препятствий.</span><span class="sxs-lookup"><span data-stu-id="60049-108">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="60049-109">При проверке конфигурации системы создается отчет, содержащий краткое описание всех выполненных правил и состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="60049-109">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="60049-110">Отчет о проверке конфигурации системы находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="60049-110">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="60049-111">Прежде чем начинать установку, ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="60049-111">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="60049-112">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="60049-112">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="60049-113">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="60049-113">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="60049-114">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="60049-114">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="60049-115">Версии SQL Server на местных языках</span><span class="sxs-lookup"><span data-stu-id="60049-115">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="60049-116">Другие ссылки:</span><span class="sxs-lookup"><span data-stu-id="60049-116">Other references:</span></span>  
  
1.  [<span data-ttu-id="60049-117">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="60049-117">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="60049-118">Подготовка к установке отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="60049-118">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="60049-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="60049-119">See Also</span></span>  
 [<span data-ttu-id="60049-120">Установка правил</span><span class="sxs-lookup"><span data-stu-id="60049-120">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
