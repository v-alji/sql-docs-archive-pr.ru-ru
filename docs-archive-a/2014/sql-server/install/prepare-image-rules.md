---
title: Правила подготовки образа | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 609a7c06-9527-4ef5-8e75-0c44e1958c5a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8c9c09e6e9abb3ee3e17d4942cb8e518f5d551a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666931"
---
# <a name="prepare-image-rules"></a><span data-ttu-id="1be78-102">Правила подготовки образа</span><span class="sxs-lookup"><span data-stu-id="1be78-102">Prepare Image Rules</span></span>
  <span data-ttu-id="1be78-103">Программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] проверяет конфигурацию компьютера перед началом установки.</span><span class="sxs-lookup"><span data-stu-id="1be78-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="1be78-104">Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средство проверки конфигурации системы (SCC) просматривает компьютер, на котором устанавливается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1be78-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="1be78-105">Средство SCC проверяет наличие условий, препятствующих успешной установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1be78-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="1be78-106">Прежде чем программа установки запустит мастер, SCC получает сведения о состоянии каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="1be78-106">Before Setup starts the wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="1be78-107">Затем оно сравнивает результаты с требуемыми условиями и предоставляет рекомендации по устранению критических препятствий.</span><span class="sxs-lookup"><span data-stu-id="1be78-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="1be78-108">При проверке конфигурации системы создается отчет, содержащий краткое описание всех выполненных правил и состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="1be78-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="1be78-109">Отчет о проверке конфигурации системы находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="1be78-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="1be78-110">Прежде чем начинать установку, ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="1be78-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="1be78-111">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1be78-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="1be78-112">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1be78-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="1be78-113">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="1be78-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="1be78-114">Версии SQL Server на местных языках</span><span class="sxs-lookup"><span data-stu-id="1be78-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="1be78-115">Другие ссылки:</span><span class="sxs-lookup"><span data-stu-id="1be78-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="1be78-116">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="1be78-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="1be78-117">Подготовка к установке отказоустойчивого кластера</span><span class="sxs-lookup"><span data-stu-id="1be78-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
  
