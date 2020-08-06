---
title: Несовместимые параметры сортировки ядро СУБД сервера (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668048"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a><span data-ttu-id="fdf5d-102">Несовместимые параметры сортировки сервера компонента Database Engine (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="fdf5d-102">Incompatible Database Engine Server Collation (Upgrade Advisor)</span></span>
  <span data-ttu-id="fdf5d-103">Обнаружено, что советник по переходу [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] использует экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , который настроен для использования несовместимых параметров сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
||  
|-|  
|<span data-ttu-id="fdf5d-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="fdf5d-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="fdf5d-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="fdf5d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fdf5d-106">Description</span></span>  
 <span data-ttu-id="fdf5d-107">Обнаружено, что советник по переходу [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] использует экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , который настроен для использования несовместимых параметров сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="fdf5d-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]В режиме интеграции с SharePoint используется архитектура общих служб SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode utilizes the SharePoint shared services architecture.</span></span> <span data-ttu-id="fdf5d-109">SharePoint не поддерживает компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], в котором задан учет регистра, параметры сортировки сервера или двоичные параметры сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-109">SharePoint does not support [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configured for case sensitive or server collations or binary server collations.</span></span> <span data-ttu-id="fdf5d-110">В число несовместимых параметров сортировки входят те, которые по умолчанию учитывают регистр символов или являются двоичными, а также базовые параметры сортировки, которые по умолчанию являются совместимыми, но в них были заданы любые из следующих обозначений параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-110">Incompatible collations include collations that are by default case sensitive or binary and a base collation that by default is compatible but has been configured with any of the following collation designators:</span></span>  
  
-   <span data-ttu-id="fdf5d-111">**Двоичный**</span><span class="sxs-lookup"><span data-stu-id="fdf5d-111">**Binary**</span></span>  
  
-   <span data-ttu-id="fdf5d-112">**С учетом регистра**</span><span class="sxs-lookup"><span data-stu-id="fdf5d-112">**Case-sensitive**</span></span>  
  
-   <span data-ttu-id="fdf5d-113">**Двоичные по кодовым точкам**</span><span class="sxs-lookup"><span data-stu-id="fdf5d-113">**Binary-codepoint**</span></span>  
  
 <span data-ttu-id="fdf5d-114">Поскольку текущие параметры сортировки сервера компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] несовместимы, обновление заблокировано.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-114">Because the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation is incompatible, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fdf5d-115">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="fdf5d-115">Corrective Action</span></span>  
 <span data-ttu-id="fdf5d-116">Свойство параметров сортировки сервера компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation property cannot be changed.</span></span> <span data-ttu-id="fdf5d-117">Выполнить обновление служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] невозможно.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-117">You will not be able to complete an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="fdf5d-118">Необходимо перенести установку служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] на другой сервер, на котором используются совместимые параметры сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="fdf5d-118">You will need to migrate your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new server which is using a compatible server collation.</span></span> <span data-ttu-id="fdf5d-119">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="fdf5d-119">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="fdf5d-120">Обновление и перенос служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fdf5d-120">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [<span data-ttu-id="fdf5d-121">Выбор параметров сортировки SQL Server</span><span class="sxs-lookup"><span data-stu-id="fdf5d-121">Selecting a SQL Server Collation</span></span>](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
