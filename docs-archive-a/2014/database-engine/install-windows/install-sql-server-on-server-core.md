---
title: Установка SQL Server 2014 на Server Core | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 1dd294cc-5b69-4d0c-9005-3e307b75678b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2614c43bb763757db7db46b1c7a966221da96f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729785"
---
# <a name="install-sql-server-2014-on-server-core"></a><span data-ttu-id="bb9b1-102">Установка SQL Server 2014 в операционной системе Server Core</span><span class="sxs-lookup"><span data-stu-id="bb9b1-102">Install SQL Server 2014 on Server Core</span></span>
  <span data-ttu-id="bb9b1-103">Можно установить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поверх установленной Server Core ОС [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-103">You can install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="bb9b1-104">В этом разделе приводятся подробные сведения, относящиеся к установке [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] на Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-104">This topic provides setup-specific details for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core.</span></span>  
  
 <span data-ttu-id="bb9b1-105">Вариант установки Server Core для операционной системы [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] или [!INCLUDE[win8srv](../../includes/win8srv-md.md)] предусматривает наличие среды, минимально необходимой для запуска конкретных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-105">The Server Core installation option for the [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] operating system provides a minimal environment for running specific server roles.</span></span> <span data-ttu-id="bb9b1-106">Это дает возможность снизить требования к обслуживанию и управлению и уменьшить уязвимость для атак со стороны этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-106">This helps to reduce maintenance and management requirements and the attack surface for those server roles.</span></span> <span data-ttu-id="bb9b1-107">Дополнительные сведения о реализации Server Core в см [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] . в разделе [Server Core для Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) ( https://go.microsoft.com/fwlink/?LinkId=202439) .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-107">For more information on Server Core as implemented on [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)], see [Server Core for Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) (https://go.microsoft.com/fwlink/?LinkId=202439).</span></span> <span data-ttu-id="bb9b1-108">Дополнительные сведения о реализации Server Core в операционной системе [!INCLUDE[win8srv](../../includes/win8srv-md.md)] см. в разделе [Server Core для Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-108">For more information on Server Core as implemented on [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bb9b1-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bb9b1-109">Prerequisites</span></span>  
  
|<span data-ttu-id="bb9b1-110">Требование</span><span class="sxs-lookup"><span data-stu-id="bb9b1-110">Requirement</span></span>|<span data-ttu-id="bb9b1-111">Как установить</span><span class="sxs-lookup"><span data-stu-id="bb9b1-111">How to install</span></span>|  
|-----------------|--------------------|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="bb9b1-112">2.0 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-112">2.0 SP2</span></span>|<span data-ttu-id="bb9b1-113">Входит в программу установки Server Core [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) и [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-113">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="bb9b1-114">Если платформа не разрешена, то программа установки включает ее по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-114">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="bb9b1-115">Невозможно параллельно запустить на данном компьютере версии 2.0, 3.0 и 3.5.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-115">It is not possible to run versions 2.0, 3.0, and 3.5 side by side on a computer.</span></span> <span data-ttu-id="bb9b1-116">При установке платформы .NET Framework 3.5 с пакетом обновления 1 (SP1) вы получаете уровни 2.0 и 3.0 автоматически.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-116">When you install the .NET Framework 3.5 SP1, you get the 2.0 and 3.0 layers automatically.</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="bb9b1-117">3.5 с пакетом обновления 1 (SP1) Full Profile</span><span class="sxs-lookup"><span data-stu-id="bb9b1-117">3.5 SP1 Full Profile</span></span>|<span data-ttu-id="bb9b1-118">Входит в программу установки Server Core [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-118">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span> <span data-ttu-id="bb9b1-119">Если платформа не разрешена, то программа установки включает ее по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-119">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="bb9b1-120">На компьютере, работающем под управлением серверной ОС Windows, необходимо загрузить и установить платформу .NET Framework 3.5 с пакетом обновления 1 (SP1) перед началом установки, чтобы установить компоненты, зависимые от .NET Framework 3.5 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-120">On a computer with Windows server operating system you must download and install .NET Framework 3.5 SP1 before you run Setup, to install components dependent on .NET 3.5 SP1.</span></span><br /><br /> <span data-ttu-id="bb9b1-121">Дополнительные сведения о рекомендациях и рекомендации по получению и включению .NET Framework 3,5 в [!INCLUDE[win8srv](../../includes/win8srv-md.md)] см. в разделе [рекомендации по развертыванию Microsoft .NET Framework 3,5](https://msdn.microsoft.com/library/windows/hardware/hh975396) ( https://msdn.microsoft.com/library/windows/hardware/hh975396) .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-121">For more information about the recommendations and guidance on how to acquire and enable .NET Framework 3.5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Microsoft .NET Framework 3.5 Deployment Considerations](https://msdn.microsoft.com/library/windows/hardware/hh975396) (https://msdn.microsoft.com/library/windows/hardware/hh975396).</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="bb9b1-122">4 Server Core Profile</span><span class="sxs-lookup"><span data-stu-id="bb9b1-122">4 Server Core Profile</span></span>|<span data-ttu-id="bb9b1-123">Для всех выпусков [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , кроме [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], программа установки устанавливает платформу [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile как обязательное ПО.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-123">For all editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], Setup installs the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile as a prerequisite.</span></span><br /><br /> <span data-ttu-id="bb9b1-124">Для [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)] Загрузите [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4-файловый профиль Server core из [Microsoft .NET Framework 4 (автономный установщик) для Server Core](https://www.microsoft.com/download/details.aspx?id=17718) ( https://www.microsoft.com/download/details.aspx?id=17718) и установите его перед тем, как продолжить установку).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-124">For [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)], download the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile from [Microsoft .NET Framework 4 (Standalone Installer) for Server Core](https://www.microsoft.com/download/details.aspx?id=17718) (https://www.microsoft.com/download/details.aspx?id=17718), and install it before you proceed with the setup.</span></span>|  
|<span data-ttu-id="bb9b1-125">Установщик Windows 4.5</span><span class="sxs-lookup"><span data-stu-id="bb9b1-125">Windows Installer 4.5</span></span>|<span data-ttu-id="bb9b1-126">Поставляется с установкой Server Core с [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) и [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-126">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
|<span data-ttu-id="bb9b1-127">Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="bb9b1-127">Windows PowerShell 2.0</span></span>|<span data-ttu-id="bb9b1-128">Поставляется с установкой Server Core с [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) и [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-128">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
  
##  <a name="supported-features"></a><a name="BK_SupportedFeatures"></a> <span data-ttu-id="bb9b1-129">Поддерживаемые компоненты</span><span class="sxs-lookup"><span data-stu-id="bb9b1-129">Supported Features</span></span>  
 <span data-ttu-id="bb9b1-130">В следующей таблице можно найти компоненты, которые поддерживаются в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в установке Server Core ОС [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) и [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-130">Use the following table to find which features are supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|<span data-ttu-id="bb9b1-131">Компонент</span><span class="sxs-lookup"><span data-stu-id="bb9b1-131">Feature</span></span>|<span data-ttu-id="bb9b1-132">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="bb9b1-132">Supported</span></span>|  
|-------------|---------------|  
|<span data-ttu-id="bb9b1-133">Службы[!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b1-133">[!INCLUDE[ssDE](../../includes/ssde-md.md)] Services</span></span>|<span data-ttu-id="bb9b1-134">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-134">Yes</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb9b1-135">Репликация</span><span class="sxs-lookup"><span data-stu-id="bb9b1-135">Replication</span></span>|<span data-ttu-id="bb9b1-136">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-136">Yes</span></span>|  
|<span data-ttu-id="bb9b1-137">Полнотекстовый поиск</span><span class="sxs-lookup"><span data-stu-id="bb9b1-137">Full Text Search</span></span>|<span data-ttu-id="bb9b1-138">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-138">Yes</span></span>|  
|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|<span data-ttu-id="bb9b1-139">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-139">Yes</span></span>|  
|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|<span data-ttu-id="bb9b1-140">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-140">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb9b1-141">Data Tools (SSDT)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-141">Data Tools (SSDT)</span></span>|<span data-ttu-id="bb9b1-142">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-142">No</span></span>|  
|<span data-ttu-id="bb9b1-143">Средства связи клиентских средств</span><span class="sxs-lookup"><span data-stu-id="bb9b1-143">Client Tools Connectivity</span></span>|<span data-ttu-id="bb9b1-144">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-144">Yes</span></span>|  
|<span data-ttu-id="bb9b1-145">Integration Services Server<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="bb9b1-145">Integration Services Server<sup>[1]</sup></span></span>|<span data-ttu-id="bb9b1-146">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-146">Yes</span></span>|  
|<span data-ttu-id="bb9b1-147">Обратная совместимость клиентских средств</span><span class="sxs-lookup"><span data-stu-id="bb9b1-147">Client Tools Backward Compatibility</span></span>|<span data-ttu-id="bb9b1-148">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-148">No</span></span>|  
|<span data-ttu-id="bb9b1-149">Пакет SDK клиентских средств</span><span class="sxs-lookup"><span data-stu-id="bb9b1-149">Client Tools SDK</span></span>|<span data-ttu-id="bb9b1-150">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-150">No</span></span>|  
|<span data-ttu-id="bb9b1-151">Электронная документация по[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b1-151">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="bb9b1-152">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-152">No</span></span>|  
|<span data-ttu-id="bb9b1-153">Основные средства управления</span><span class="sxs-lookup"><span data-stu-id="bb9b1-153">Management Tools - Basic</span></span>|<span data-ttu-id="bb9b1-154">Только удаленный<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="bb9b1-154">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="bb9b1-155">Средства управления — полный набор</span><span class="sxs-lookup"><span data-stu-id="bb9b1-155">Management Tools - Complete</span></span>|<span data-ttu-id="bb9b1-156">Только удаленный<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="bb9b1-156">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="bb9b1-157">Контроллер распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="bb9b1-157">Distributed Replay Controller</span></span>|<span data-ttu-id="bb9b1-158">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-158">No</span></span>|  
|<span data-ttu-id="bb9b1-159">Клиент распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="bb9b1-159">Distributed Replay Client</span></span>|<span data-ttu-id="bb9b1-160">Только удаленный<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="bb9b1-160">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="bb9b1-161">Пакет SDK для подключения клиентов SQL</span><span class="sxs-lookup"><span data-stu-id="bb9b1-161">SQL Client Connectivity SDK</span></span>|<span data-ttu-id="bb9b1-162">Да</span><span class="sxs-lookup"><span data-stu-id="bb9b1-162">Yes</span></span>|  
|<span data-ttu-id="bb9b1-163">Microsoft Sync Framework</span><span class="sxs-lookup"><span data-stu-id="bb9b1-163">Microsoft Sync Framework</span></span>|<span data-ttu-id="bb9b1-164">Да<sup>[3]</sup></span><span class="sxs-lookup"><span data-stu-id="bb9b1-164">Yes<sup>[3]</sup></span></span>|  
|[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]|<span data-ttu-id="bb9b1-165">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-165">No</span></span>|  
|[!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]|<span data-ttu-id="bb9b1-166">Нет</span><span class="sxs-lookup"><span data-stu-id="bb9b1-166">No</span></span>|  
  
 <span data-ttu-id="bb9b1-167"><sup>[1]</sup> Дополнительные сведения о новом сервере Integration Services и его возможностях [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] см. в разделе [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-167"><sup>[1]</sup>For more information about the new Integration Services Server and its features in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="bb9b1-168"><sup>[2]</sup> Установка этих компонентов на Server Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-168"><sup>[2]</sup>Installation of these features on Server Core is not supported.</span></span> <span data-ttu-id="bb9b1-169">Эти компоненты могут быть установлены на другом сервере, отличном от [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, и подключены к службам [!INCLUDE[ssDE](../../includes/ssde-md.md)] , установленным в Server Core.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-169">These components can be installed on a different server that is not [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, and connected to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] services installed on Server Core.</span></span>  
  
 <span data-ttu-id="bb9b1-170"><sup>[3]</sup> Microsoft Sync Framework не входит в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] пакет установки.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-170"><sup>[3]</sup>Microsoft Sync Framework is not included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation package.</span></span> <span data-ttu-id="bb9b1-171">Вы можете скачать соответствующую версию Sync Framework из [центра загрузки Майкрософт](https://go.microsoft.com/fwlink/?LinkId=221788) ( https://go.microsoft.com/fwlink/?LinkId=221788) на странице) и установить ее на компьютере, на котором выполняется установка Server Core [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-171">You can download the appropriate version of Sync Framework from this [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) (https://go.microsoft.com/fwlink/?LinkId=221788) page and install it on a computer that is running Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
## <a name="supported-scenario-matrix"></a><span data-ttu-id="bb9b1-172">Матрица поддерживаемых сценариев</span><span class="sxs-lookup"><span data-stu-id="bb9b1-172">Supported Scenario Matrix</span></span>  
 <span data-ttu-id="bb9b1-173">В следующей таблице показана матрица поддерживаемых сценариев для установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] на экземпляре Server Core [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) и [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-173">The following table shows the supported scenario matrix for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|||  
|-|-|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb9b1-174">, выпуски</span><span class="sxs-lookup"><span data-stu-id="bb9b1-174">editions</span></span>|<span data-ttu-id="bb9b1-175">Все [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-разрядные выпуски<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="bb9b1-175">All [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-bit editions<sup>[1]</sup></span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb9b1-176">, язык</span><span class="sxs-lookup"><span data-stu-id="bb9b1-176">language</span></span>|<span data-ttu-id="bb9b1-177">Все языки</span><span class="sxs-lookup"><span data-stu-id="bb9b1-177">All languages</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb9b1-178">, язык в языке ОС-локали (сочетание)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-178">language on OS language/locale (combination)</span></span>|<span data-ttu-id="bb9b1-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для JPN (японский) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on JPN (Japanese) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для GER (немецкий) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on GER (German) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для CHS (китайский — Китай) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on CHS (Chinese-China) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для ARA (арабский (SA)) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ARA (Arabic (SA)) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для THA (тайский) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on THA (Thai) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для TRK (турецкий) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on TRK (Turkish) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для pt-PT (португальский, Португалия) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on pt-PT (Portuguese Portugal) Windows</span></span><br /><br /> <span data-ttu-id="bb9b1-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для ENG (английский) Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ENG (English) Windows</span></span>|  
|<span data-ttu-id="bb9b1-187">Выпуск Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-187">Windows edition</span></span>|<span data-ttu-id="bb9b1-188">64-разрядная версия[!INCLUDE[win8srv](../../includes/win8srv-md.md)] x64 Datacenter</span><span class="sxs-lookup"><span data-stu-id="bb9b1-188">[!INCLUDE[win8srv](../../includes/win8srv-md.md)] 64-bit x64 Datacenter</span></span><br /><br /> <span data-ttu-id="bb9b1-189">64-разрядная версия[!INCLUDE[win8srv](../../includes/win8srv-md.md)] x64 Standard</span><span class="sxs-lookup"><span data-stu-id="bb9b1-189">[!INCLUDE[win8srv](../../includes/win8srv-md.md)] 64-bit x64 Standard</span></span><br /><br /> <span data-ttu-id="bb9b1-190">64-разрядная версия[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] x64 Data Center Server Core Edition с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-190">[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64-bit x64 Data Center Server Core</span></span><br /><br /> <span data-ttu-id="bb9b1-191">64-разрядная версия[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] x64 Enterprise Server Core с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-191">[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64-bit x64 Enterprise Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="bb9b1-192">Windows Server Standard Server Core с пакетом обновления 1 (SP1) для 64-разрядных систем с архитектурой x64</span><span class="sxs-lookup"><span data-stu-id="bb9b1-192">SP1 64-bit x64 Standard Server Core</span></span><br /><br /> <span data-ttu-id="bb9b1-193">64-разрядная версия[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] x64 Web Server Core с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-193">[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64-bit x64 Web Server Core</span></span>|  
  
 <span data-ttu-id="bb9b1-194"><sup>[1]</sup> Установка 32-разрядных версий [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] не поддерживается в Server Core.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-194"><sup>[1]</sup>Installing the 32-bit version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] editions is not supported on Server Core.</span></span>  
  
## <a name="upgrading"></a><span data-ttu-id="bb9b1-195">Обновление</span><span class="sxs-lookup"><span data-stu-id="bb9b1-195">Upgrading</span></span>  
 <span data-ttu-id="bb9b1-196">В установках Server Core поддерживается обновление с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] до [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-196">On Server Core installations, upgrading from [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is supported.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="bb9b1-197">Установка</span><span class="sxs-lookup"><span data-stu-id="bb9b1-197">Installation</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="bb9b1-198">не поддерживает установку с помощью мастера установки в операционной системе Server Core.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-198">does not support setup by using the installation wizard on the Server Core operating system.</span></span> <span data-ttu-id="bb9b1-199">При установке на Server Core программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает полный тихий режим без вывода сообщений с использованием параметра /Q или простой режим без вывода сообщений с использованием параметра /QS.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-199">When installing on Server Core, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup supports full quiet mode by using the /Q parameter, or Quiet Simple mode by using the /QS parameter.</span></span> <span data-ttu-id="bb9b1-200">Дополнительные сведения см. в статье [Установка SQL Server 2014 из командной строки](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-200">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="bb9b1-201">нельзя установить параллельно с более ранними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на компьютере с [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-201">cannot be installed side-by-side with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span></span>  
  
 <span data-ttu-id="bb9b1-202">Независимо от метода установки, необходимо подтвердить свое согласие с условиями лицензии на использование пакета программ как физического лица или от имени организации, если на используемое программное обеспечение не распространяется отдельное соглашение [!INCLUDE[msCoName](../../includes/msconame-md.md)] , такое как соглашение о корпоративном лицензировании Майкрософт или отдельное соглашение с независимым поставщиком программного обеспечения или изготовителем оборудования (OEM).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-202">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="bb9b1-203">Условия лицензионного соглашения отображаются для ознакомления и принятия в пользовательском интерфейсе программы установки.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-203">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="bb9b1-204">Автоматические установки (с использованием параметров /Q или /QS) должны включать параметр /IACCEPTSQLSERVERLICENSETERMS.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-204">Unattended installations (using the /Q or /QS parameters) must include the /IACCEPTSQLSERVERLICENSETERMS parameter.</span></span> <span data-ttu-id="bb9b1-205">Ознакомиться с условиями лицензии можно на странице [Условия лицензионного соглашения о программном обеспечении Майкрософт](https://go.microsoft.com/fwlink/?LinkId=148209).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-205">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb9b1-206">В зависимости от способа получения ПО (например, по [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), на его использование могут распространяться дополнительные условия.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-206">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
 <span data-ttu-id="bb9b1-207">Для установки отдельных компонентов используйте параметр /FEATURES и укажите значения родительского компонента или компонентов.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-207">To install specific features, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="bb9b1-208">Дополнительные сведения о параметрах компонентов и их использовании см. в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-208">For more information about feature parameters and their use, see the following sections.</span></span>  
  
### <a name="feature-parameters"></a><span data-ttu-id="bb9b1-209">Параметры компонентов</span><span class="sxs-lookup"><span data-stu-id="bb9b1-209">Feature Parameters</span></span>  
  
|<span data-ttu-id="bb9b1-210">Параметр компонента</span><span class="sxs-lookup"><span data-stu-id="bb9b1-210">Feature parameter</span></span>|<span data-ttu-id="bb9b1-211">Описание</span><span class="sxs-lookup"><span data-stu-id="bb9b1-211">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="bb9b1-212">SQLENGINE</span><span class="sxs-lookup"><span data-stu-id="bb9b1-212">SQLENGINE</span></span>|<span data-ttu-id="bb9b1-213">Устанавливает только компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-213">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bb9b1-214">РЕПЛИКАЦИЯ</span><span class="sxs-lookup"><span data-stu-id="bb9b1-214">REPLICATION</span></span>|<span data-ttu-id="bb9b1-215">Устанавливает компонент репликации вместе с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-215">Installs the Replication component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bb9b1-216">FULLTEXT</span><span class="sxs-lookup"><span data-stu-id="bb9b1-216">FULLTEXT</span></span>|<span data-ttu-id="bb9b1-217">Устанавливает компонент FullText вместе с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-217">Installs the FullText component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bb9b1-218">AS</span><span class="sxs-lookup"><span data-stu-id="bb9b1-218">AS</span></span>|<span data-ttu-id="bb9b1-219">Устанавливает все компоненты служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-219">Installs all [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="bb9b1-220">IS</span><span class="sxs-lookup"><span data-stu-id="bb9b1-220">IS</span></span>|<span data-ttu-id="bb9b1-221">Устанавливает все компоненты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-221">Installs all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="bb9b1-222">CONN</span><span class="sxs-lookup"><span data-stu-id="bb9b1-222">CONN</span></span>|<span data-ttu-id="bb9b1-223">Устанавливает компоненты подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-223">Installs the connectivity components.</span></span>|  
  
 <span data-ttu-id="bb9b1-224">В следующих примерах показано использование параметров компонентов.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-224">See the following examples of the usage of feature parameters:</span></span>  
  
|<span data-ttu-id="bb9b1-225">Параметр и значения</span><span class="sxs-lookup"><span data-stu-id="bb9b1-225">Parameter and values</span></span>|<span data-ttu-id="bb9b1-226">Описание</span><span class="sxs-lookup"><span data-stu-id="bb9b1-226">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="bb9b1-227">/FEATURES=SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb9b1-227">/FEATURES=SQLEngine</span></span>|<span data-ttu-id="bb9b1-228">Устанавливает только компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-228">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="bb9b1-229">/FEATURES=SQLEngine, FullText</span><span class="sxs-lookup"><span data-stu-id="bb9b1-229">/FEATURES=SQLEngine,FullText</span></span>|<span data-ttu-id="bb9b1-230">Устанавливает компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] с компонентом Full-Text Search.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-230">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and full-text.</span></span>|  
|<span data-ttu-id="bb9b1-231">/FEATURES=SQLEngine, Conn</span><span class="sxs-lookup"><span data-stu-id="bb9b1-231">/FEATURES=SQLEngine,Conn</span></span>|<span data-ttu-id="bb9b1-232">Устанавливает компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] и компоненты подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-232">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the connectivity components.</span></span>|  
|<span data-ttu-id="bb9b1-233">/FEATURES=SQLEngine, AS, IS, Conn</span><span class="sxs-lookup"><span data-stu-id="bb9b1-233">/FEATURES=SQLEngine,AS,IS,Conn</span></span>|<span data-ttu-id="bb9b1-234">Устанавливает компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)], службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]и компоненты подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-234">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and the connectivity components.</span></span>|  
  
### <a name="installation-options"></a><span data-ttu-id="bb9b1-235">Варианты установки</span><span class="sxs-lookup"><span data-stu-id="bb9b1-235">Installation Options</span></span>  
 <span data-ttu-id="bb9b1-236">Программа установки поддерживает следующие варианты установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в операционной системе Server Core.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-236">The Setup supports the following installation options while installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core operating system:</span></span>  
  
1.  <span data-ttu-id="bb9b1-237">**Установка из командной строки**</span><span class="sxs-lookup"><span data-stu-id="bb9b1-237">**Installation from Command Line**</span></span>  
  
     <span data-ttu-id="bb9b1-238">Чтобы установить конкретные компоненты с помощью командной строки, необходимо использовать параметр /FEATURES и указать родительский компонент или конкретные компоненты.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-238">To install specific features using the command prompt installation option, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="bb9b1-239">Ниже приведен пример указания параметров в командной строке.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-239">The following is an example of using the parameters from the command line:</span></span>  
  
    ```cmd
    setup.exe /qs /ACTION=Install /FEATURES=SQLEngine,Replication /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="<DomainName\UserName>" /SQLSVCPASSWORD="<StrongPassword>" /SQLSYSADMINACCOUNTS="<DomainName\UserName>" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /TCPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS  
    ```  
  
2.  <span data-ttu-id="bb9b1-240">**Установка с помощью файла конфигурации**</span><span class="sxs-lookup"><span data-stu-id="bb9b1-240">**Installation using Configuration File**</span></span>  
  
     <span data-ttu-id="bb9b1-241">Программа установки поддерживает использование файлов конфигурации только через командную строку.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-241">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="bb9b1-242">Файл конфигурации — это текстовый файл, содержащий параметры (пара «имя-значение») и комментарии с описанием.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-242">The configuration file is a text file with the basic structure of a parameter (name/value pair) and a descriptive comment.</span></span> <span data-ttu-id="bb9b1-243">Файл конфигурации, который указывается в командной строке, должен иметь расширение INI.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-243">The configuration file specified at the command prompt should have an .INI file name extension.</span></span> <span data-ttu-id="bb9b1-244">Ниже приведены примеры файла ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-244">See the following examples of ConfigurationFile.INI:</span></span>  
  
    -   <span data-ttu-id="bb9b1-245">Установка [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b1-245">Installing [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
         <span data-ttu-id="bb9b1-246">В следующем примере показано, как установить новый автономный экземпляр, который включает компонент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-246">The following example shows how to install a new stand-alone instance that includes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine, and Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Accept the License agreement to continue with Installation  
  
        IAcceptSQLServerLicenseTerms="True"
        ```  
  
    -   <span data-ttu-id="bb9b1-247">Установка компонентов подключения к данным</span><span class="sxs-lookup"><span data-stu-id="bb9b1-247">Installing connectivity components</span></span>  
  
         <span data-ttu-id="bb9b1-248">Следующий пример показывает, как установить компоненты подключения к данным:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-248">The following example shows how to install the connectivity components:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=Conn  
  
        ; Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True
        ```  
  
    -   <span data-ttu-id="bb9b1-249">Установка всех поддерживаемых компонентов</span><span class="sxs-lookup"><span data-stu-id="bb9b1-249">Installing all supported features</span></span>  
  
         <span data-ttu-id="bb9b1-250">Следующий пример показывает, как установить все поддерживаемые компоненты [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] в Server Core:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-250">The following example shows how to install all supported features of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE,FullText,Replication,AS,IS,Conn  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine (SQL), or Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; The name of the account that the Analysis Services service runs under.   
  
        ASSVCACCOUNT= "NT Service\MSSQLServerOLAPService"  
  
        ; Specifies the list of administrator accounts that need to be provisioned.   
  
        ASSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Specifies the server mode of the Analysis Services instance. Valid values are MULTIDIMENSIONAL, POWERPIVOT or TABULAR. ASSERVERMODE is case-sensitive. All values must be expressed in upper case.   
  
        ASSERVERMODE="MULTIDIMENSIONAL"  
  
        ; Optional value, which specifies the state of the TCP protocol for the ssNoVersion service. Supported values are: 0 to disable the TCP protocol, and 1 to enable the TCP protocol.  
  
        TCPENABLED=1  
  
        ;Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True"  
        ```  
  
     <span data-ttu-id="bb9b1-251">В следующей таблице показан процесс запуска установки при помощи файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-251">The following examples show how you can launch the Setup using a configuration file.</span></span>  
  
    -   <span data-ttu-id="bb9b1-252">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="bb9b1-252">Configuration file</span></span>  
  
         <span data-ttu-id="bb9b1-253">Ниже приведено несколько примеров использования файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-253">Following are some examples of how to use the configuration file:</span></span>  
  
        -   <span data-ttu-id="bb9b1-254">Указание файла конфигурации в командной строке:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-254">To specify the configuration file at the command prompt:</span></span>  
  
        ```cmd
        setup.exe /QS /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
        -   <span data-ttu-id="bb9b1-255">Указание паролей в командной строке, а не в файле конфигурации:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-255">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
        ```cmd
        setup.exe /QS /SQLSVCPASSWORD="************" /ASSVCPASSWORD="************"  /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
    -   <span data-ttu-id="bb9b1-256">DefaultSetup.ini</span><span class="sxs-lookup"><span data-stu-id="bb9b1-256">DefaultSetup.ini</span></span>  
  
         <span data-ttu-id="bb9b1-257">Если файл DefaultSetup.ini находится в папках \x86 и \x64 в корневой папке исходного носителя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , откройте этот файл и добавьте в него параметр *Features* .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-257">If you have the DefaultSetup.ini file in the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media, open the DefaultSetup.ini file, and then add the *Features* parameter to the file.</span></span>  
  
         <span data-ttu-id="bb9b1-258">Если файл DefaultSetup.ini не существует, создайте его и скопируйте в папки \x86 и \x64 корневой папки исходного носителя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-258">If the DefaultSetup.ini file does not exist, you can create it and copy it to the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media.</span></span>  
  
## <a name="configuring-remote-access-of-ssnoversion-running-on-server-core"></a><span data-ttu-id="bb9b1-259">Настройка удаленного доступа для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при работе на Server Core</span><span class="sxs-lookup"><span data-stu-id="bb9b1-259">Configuring Remote Access of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Running on Server Core</span></span>  
 <span data-ttu-id="bb9b1-260">Чтобы настроить удаленный доступ к экземпляру [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , который запускается в установке Server Core ОС [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)], выполните действия, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-260">Perform the actions described below to configure remote access of a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance that is running on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
### <a name="enable-remote-connections-on-the-instance-of-ssnoversion"></a><span data-ttu-id="bb9b1-261">Включение удаленных подключений на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b1-261">Enable remote connections on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="bb9b1-262">Чтобы разрешить удаленные соединения, выполните следующие инструкции для экземпляра Server Core в локальной программе SQLCMD.exe.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-262">To enable remote connections, use SQLCMD.exe locally and execute the following statements against the Server Core instance:</span></span>  
  
-   `EXEC sys.sp_configure N'remote access', N'1'`  
  
     `GO`  
  
-   `RECONFIGURE WITH OVERRIDE`  
  
     `GO`  
  
### <a name="enable-and-start-the-ssnoversion-browser-service"></a><span data-ttu-id="bb9b1-263">Включите и запустите службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b1-263">Enable and start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service</span></span>  
 <span data-ttu-id="bb9b1-264">По умолчанию эта служба отключена.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-264">By default, the Browser service is disabled.</span></span>  <span data-ttu-id="bb9b1-265">Если она отключена на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , работающем на Server Core, то для ее включения выполните следующую команду из командной строки:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-265">If it is disabled on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on Server Core, run the following command from the command prompt to enable it:</span></span>  
  
 `sc config SQLBROWSER start= auto`  
  
 <span data-ttu-id="bb9b1-266">После включения службы выполните следующую команду из командной строки, чтобы запустить службу:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-266">After it is enabled, run the following command from the command prompt to start the service:</span></span>  
  
 `net start SQLBROWSER`  
  
### <a name="create-exceptions-in-windows-firewall"></a><span data-ttu-id="bb9b1-267">Создание исключений в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="bb9b1-267">Create exceptions in Windows Firewall</span></span>  
 <span data-ttu-id="bb9b1-268">Чтобы создать исключения в брандмауэре Windows для доступа к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполните действия, описанные в разделе [Настройка брандмауэра Windows для разрешения доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-268">To create exceptions for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access in Windows Firewall, follow the steps specified in [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
### <a name="enable-tcpip-on-the-instance-of-ssnoversion"></a><span data-ttu-id="bb9b1-269">Включите поддержку TCP/IP на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b1-269">Enable TCP/IP on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="bb9b1-270">Протокол TCP/IP для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в Server Core можно включить через Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-270">The TCP/IP protocol can be enabled through Windows PowerShell for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on Server Core.</span></span> <span data-ttu-id="bb9b1-271">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-271">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="bb9b1-272">На компьютере, где запущена ОС [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, запустите диспетчер задач.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-272">On the computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, launch Task Manager.</span></span>  
  
2.  <span data-ttu-id="bb9b1-273">На вкладке **Приложения** нажмите **Создать задачу**.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-273">On the **Applications** tab, click **New Task**.</span></span>  
  
3.  <span data-ttu-id="bb9b1-274">В диалоговом окне **Создание новой задачи** введите **sqlps.exe** в поле **Открыть** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-274">In the **Create New Task** dialog box, type **sqlps.exe** in the **Open** field and then click **OK**.</span></span> <span data-ttu-id="bb9b1-275">Откроется окно \*\* [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell\*\* .</span><span class="sxs-lookup"><span data-stu-id="bb9b1-275">This opens the **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window.</span></span>  
  
4.  <span data-ttu-id="bb9b1-276">В окне **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** выполните следующий скрипт, чтобы включить протокол TCP/IP:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-276">In the **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window, run the following script to enable the TCP/IP protocol:</span></span>  
  
```powershell
$smo = 'Microsoft.SqlServer.Management.Smo.'  
$wmi = New-Object ($smo + 'Wmi.ManagedComputer')  
# Enable the TCP protocol on the default instance.  If the instance is named, replace MSSQLSERVER with the instance name in the following line.  
$uri = "ManagedComputer[@Name='" + (get-item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
$Tcp = $wmi.GetSmoObject($uri)  
$Tcp.IsEnabled = $true  
$Tcp.Alter()  
$Tcp  
```  
  
## <a name="uninstallation"></a><span data-ttu-id="bb9b1-277">Удаление</span><span class="sxs-lookup"><span data-stu-id="bb9b1-277">Uninstallation</span></span>  
 <span data-ttu-id="bb9b1-278">После входа на компьютер, где работает [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core с пакетом обновления 1 (SP1) или [!INCLUDE[win8srv](../../includes/win8srv-md.md)] , вы получите доступ к ограниченной среде с командной строкой администратора.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-278">After you log on to a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, you have a limited desktop environment with an Administrator command prompt.</span></span> <span data-ttu-id="bb9b1-279">В этой командной строке можно запустить процесс удаления экземпляра [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-279">You can use this command prompt to initiate uninstallation of an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="bb9b1-280">Чтобы удалить экземпляр [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], запустите удаление из командной строки — либо в полностью тихом режиме (параметр /Q), либо в простом тихом режиме (параметр /QS).</span><span class="sxs-lookup"><span data-stu-id="bb9b1-280">To uninstall an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], launch the uninstallation from the command prompt in full quiet mode by using the /Q parameter, or quiet simple mode by using the /QS parameter.</span></span> <span data-ttu-id="bb9b1-281">Если указан параметр /QS, то ход выполнения будет отображаться в пользовательском интерфейсе, но не потребует ввода.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-281">The /QS parameter shows progress through the UI, but does not accept any input.</span></span> <span data-ttu-id="bb9b1-282">Параметр /Q запускает тихий режим без пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-282">/Q runs in a quiet mode without any user interface.</span></span>  
  
 <span data-ttu-id="bb9b1-283">Удаление существующего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9b1-283">To uninstall an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```cmd
setup.exe /Q /Action=Uninstall /FEATURES=SQLEngine,AS,IS /INSTANCENAME=MSSQLSERVER  
```  
  
 <span data-ttu-id="bb9b1-284">Чтобы удалить именованный экземпляр, укажите его имя вместо имени MSSQLSERVER, указанного в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-284">To remove a named instance, specify the name of the instance instead of "MSSQLSERVER" in the preceding example.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bb9b1-285">Если окно командной строки было случайно закрыто, то его можно открыть снова, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-285">If you accidentally close the command prompt, you can start a new command prompt by following these steps:</span></span>  
> 
>  1.  <span data-ttu-id="bb9b1-286">Нажмите CTRL+SHIFT+ESC, чтобы отобразить диспетчер задач.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-286">Press Ctrl+Shift+Esc to display Task Manager.</span></span>  
> 2.  <span data-ttu-id="bb9b1-287">На вкладке **Приложения** нажмите **Создать задачу**.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-287">On the **Applications** tab, click **New Task**.</span></span>  
> 3.  <span data-ttu-id="bb9b1-288">В диалоговом окне **Создание новой задачи** введите **cmd** в поле **Открыть** [!INCLUDE[clickOK](../../includes/clickok-md.md)], а затем.</span><span class="sxs-lookup"><span data-stu-id="bb9b1-288">In the **Create New Task** dialog box, type **cmd** in the **Open** field and then [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9b1-289">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb9b1-289">See Also</span></span>  
 <span data-ttu-id="bb9b1-290">[Установка SQL Server 2014 с помощью файла конфигурации](install-sql-server-using-a-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="bb9b1-290">[Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md) </span></span>  
 <span data-ttu-id="bb9b1-291">[Установка SQL Server 2014 из командной строки](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="bb9b1-291">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="bb9b1-292">[Функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="bb9b1-292">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="bb9b1-293">[начало работы руководства по установке основных серверных компонентов](https://go.microsoft.com/fwlink/?LinkId=221422) </span><span class="sxs-lookup"><span data-stu-id="bb9b1-293">[Server Core Installation Option Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=221422) </span></span>  
 <span data-ttu-id="bb9b1-294">[Настройка установки Server Core: обзор](https://go.microsoft.com/fwlink/?LinkId=221423) </span><span class="sxs-lookup"><span data-stu-id="bb9b1-294">[Configuring a Server Core installation: Overview](https://go.microsoft.com/fwlink/?LinkId=221423) </span></span>  
 <span data-ttu-id="bb9b1-295">[Командлеты отказоустойчивого кластера в Windows PowerShell, перечисленные в фокусе задач](https://go.microsoft.com/fwlink/?LinkId=221419) </span><span class="sxs-lookup"><span data-stu-id="bb9b1-295">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://go.microsoft.com/fwlink/?LinkId=221419) </span></span>  
 [<span data-ttu-id="bb9b1-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters (Сопоставление команд Cluster.exe с командлетами Windows PowerShell для отказоустойчивых кластеров)</span><span class="sxs-lookup"><span data-stu-id="bb9b1-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters</span></span>](https://go.microsoft.com/fwlink/?LinkId=221421)  
