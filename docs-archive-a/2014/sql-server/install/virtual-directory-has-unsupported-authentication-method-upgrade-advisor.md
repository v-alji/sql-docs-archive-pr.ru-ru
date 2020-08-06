---
title: Виртуальный каталог имеет неподдерживаемый метод проверки подлинности (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 216eca6f-9a66-42e1-aa54-dcf99cec9f7d
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 67b1c027b8ed020f65fdea7c093f6d5454f02c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659120"
---
# <a name="virtual-directory-has-unsupported-authentication-method-upgrade-advisor"></a><span data-ttu-id="6f086-102">Виртуальный каталог использует неподдерживаемый метод проверки подлинности (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="6f086-102">Virtual directory has unsupported authentication method (Upgrade Advisor)</span></span>
  <span data-ttu-id="6f086-103">Помощник по обновлению обнаружил неподдерживаемый метод проверки подлинности в виртуальном каталоге диспетчера отчетов или сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="6f086-103">Upgrade Advisor detected an unsupported authentication method on the Report Manager or report server virtual directory.</span></span> <span data-ttu-id="6f086-104">Обновлением не поддерживаются следующие методы проверки подлинности: анонимный доступ, дайджест-проверка подлинности и .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="6f086-104">Authentication methods that are not supported by upgrade include Anonymous, Digest, and .NET Passport.</span></span>  
  
||  
|-|  
|<span data-ttu-id="6f086-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="6f086-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="6f086-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="6f086-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="6f086-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6f086-107">Description</span></span>  
 <span data-ttu-id="6f086-108">Программа установки не может обновить установку служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], где используется один из следующих методов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6f086-108">Setup cannot upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that uses one of the following authentication methods</span></span>  
  
-   <span data-ttu-id="6f086-109">Анонимный</span><span class="sxs-lookup"><span data-stu-id="6f086-109">Anonymous</span></span>  
  
-   <span data-ttu-id="6f086-110">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="6f086-110">Digest</span></span>  
  
-   <span data-ttu-id="6f086-111">Пароль .NET</span><span class="sxs-lookup"><span data-stu-id="6f086-111">.NET Passport</span></span>  
  
 <span data-ttu-id="6f086-112">Чтобы продолжить установку, либо измените метод проверки подлинности, заданный в виртуальных каталогах IIS служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], либо выполните миграцию установки.</span><span class="sxs-lookup"><span data-stu-id="6f086-112">To continue, you can either modify the Authentication method that is specified for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories in Internet Information Services (IIS), or you can migrate your installation.</span></span> <span data-ttu-id="6f086-113">Дополнительные сведения о миграции установки см. в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f086-113">For more information about migrating your installation, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6f086-114">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="6f086-114">Corrective Action</span></span>  
 <span data-ttu-id="6f086-115">Чтобы продолжить обновление, измените метод проверки подлинности в службах IIS для виртуальных каталогов ReportServer и Reports.</span><span class="sxs-lookup"><span data-stu-id="6f086-115">To continue with upgrade, modify the Authentication method in IIS for the ReportServer and Reports virtual directories.</span></span> <span data-ttu-id="6f086-116">Дополнительные сведения об изменении методов проверки подлинности в службах IIS см. в документации по службам IIS.</span><span class="sxs-lookup"><span data-stu-id="6f086-116">For more information about modifying Authentication methods in IIS, see the IIS documentation.</span></span> <span data-ttu-id="6f086-117">После изменения метода проверки подлинности для виртуальных директорий служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] повторно запустите помощник по обновлению, чтобы убедиться в отсутствии проблем обновления.</span><span class="sxs-lookup"><span data-stu-id="6f086-117">After you modify the Authentication method for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories, re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f086-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f086-118">See Also</span></span>  
 [<span data-ttu-id="6f086-119">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="6f086-119">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
