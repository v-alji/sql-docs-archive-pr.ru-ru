---
title: Предварительные требования советника по переходу | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- requirements [Upgrade Advisor]
- software [Upgrade Advisor]
- system requirements [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, prerequisites
- prerequisites [Upgrade Advisor]
- Upgrade Advisor [SQL Server], prerequisites
ms.assetid: d21a39e5-5f81-4096-a7dd-f244e4779992
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 41c97cf585d1768c7aebeec2613ee8744cb220da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659127"
---
# <a name="upgrade-advisor-prerequisites"></a><span data-ttu-id="9e7a8-102">Компоненты, необходимые для помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="9e7a8-102">Upgrade Advisor Prerequisites</span></span>
  <span data-ttu-id="9e7a8-103">В этом разделе описываются программные требования помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-103">This topic describes the software requirements for Upgrade Advisor.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e7a8-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9e7a8-104">Prerequisites</span></span>  
 <span data-ttu-id="9e7a8-105">Ниже перечислены предварительные условия для установки и запуска помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-105">The prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[wiprlhext](../../includes/wiprlhext-md.md)] <span data-ttu-id="9e7a8-106">с пакетом обновления 1 (SP1), [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)], начиная с версии с пакетом обновления 2 (SP2), Windows 7 или [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginning with SP2, Windows 7, or [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span></span>  
  
-   <span data-ttu-id="9e7a8-107">Установщик Windows 4.5.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-107">Windows Installer 4.5.</span></span> <span data-ttu-id="9e7a8-108">Установщик Windows можно установить с [веб-сайта установщик Windows](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="9e7a8-108">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="9e7a8-109">Платформа [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], начиная с версии Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginning with .NET Framework 4.</span></span> <span data-ttu-id="9e7a8-110">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]Компонент доступен на [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] носителе продукта, а также на [веб-сайте загрузки пакетов SDK, распространяемых компонентов и пакета обновления](https://go.microsoft.com/fwlink/?LinkId=48882).</span><span class="sxs-lookup"><span data-stu-id="9e7a8-110">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [SDK, redistributable, and service pack download Web site](https://go.microsoft.com/fwlink/?LinkId=48882).</span></span>  
  
    -   <span data-ttu-id="9e7a8-111">Чтобы установить платформу .NET Framework 4 с установочного диска [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], перейдите в корневой каталог диска.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-111">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="9e7a8-112">Откройте папку «\redist», а затем папку «DotNetFrameworks», после чего запустите файл dotNetFx40_Full_x86_x64.exe (для 32-разрядных и 64-разрядных версий операционных систем).</span><span class="sxs-lookup"><span data-stu-id="9e7a8-112">Then double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for both 32-bit and 64-bit operating systems).</span></span>  
  
-   <span data-ttu-id="9e7a8-113">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom является необходимым условием для установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] помощника по обновлению и не устанавливается программой установки помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="9e7a8-114">Для установки необходимо загрузить и установить [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] пакета дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="9e7a8-114">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7a8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e7a8-115">See Also</span></span>  
 [<span data-ttu-id="9e7a8-116">Установка помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="9e7a8-116">How to: Install Upgrade Advisor</span></span>](../../../2014/sql-server/install/how-to-install-upgrade-advisor.md)  
  
  
