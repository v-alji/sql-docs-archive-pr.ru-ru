---
title: Параметры для средства проверки конфигурации системы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, system configuration checks
- failed system configuration checks [SQL Server]
- verifying configuration before installation
- SCC [SQL Server]
- system configuration checker
- scanning computer before installation [SQL Server]
- checking configuration before installation
- status information [SQL Server], system configuration checker
- parameters [SQL Server], system configuration checker
- configuration checkers [SQL Server]
- Setup [SQL Server], system configuration checker
ms.assetid: 8e712c15-6bfa-4d71-b303-9526101e5594
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bf159d3c6184974d108075cd65e32b449d441bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734430"
---
# <a name="check-parameters-for-the-system-configuration-checker"></a><span data-ttu-id="63fbd-102">Параметры для средства проверки конфигурации системы</span><span class="sxs-lookup"><span data-stu-id="63fbd-102">Check Parameters for the System Configuration Checker</span></span>
  <span data-ttu-id="63fbd-103">Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средство проверки конфигурации системы (SCC) просматривает компьютер, на котором устанавливается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63fbd-103">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="63fbd-104">Средство SCC проверяет наличие условий, препятствующих успешной установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63fbd-104">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="63fbd-105">Прежде чем программа установки запустит мастер установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , SCC получает сведения о состоянии каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="63fbd-105">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="63fbd-106">Затем оно сравнивает результаты с требуемыми условиями и предоставляет рекомендации по устранению критических препятствий.</span><span class="sxs-lookup"><span data-stu-id="63fbd-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="63fbd-107">Средство проверки конфигурации создает отчет, содержащий краткое описание всех выполненных правил и состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="63fbd-107">The system configuration checker generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="63fbd-108">Отчет о проверке конфигурации системы находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="63fbd-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fbd-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="63fbd-109">See Also</span></span>  
 <span data-ttu-id="63fbd-110">[Требования к оборудованию и программному обеспечению для установки SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="63fbd-110">[Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 <span data-ttu-id="63fbd-111">[Вопросы безопасности при установке SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="63fbd-111">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="63fbd-112">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="63fbd-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
  
