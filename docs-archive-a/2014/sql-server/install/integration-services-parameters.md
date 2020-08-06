---
title: Параметры Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, parameters
ms.assetid: b1bb3ea3-8097-4e76-b9c2-78a0f46a23bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 76a5ebe7018fdc58f02a4d2454d40f172c752c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749624"
---
# <a name="integration-services-parameters"></a><span data-ttu-id="dd2cb-102">Параметры служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="dd2cb-102">Integration Services Parameters</span></span>
  <span data-ttu-id="dd2cb-103">Для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] можно выполнить анализ [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] пакетов на компьютере или [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] файлов пакета в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-103">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can decide to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer, or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package files in the file system.</span></span> <span data-ttu-id="dd2cb-104">При анализе файлов в файловой системе необходимо указать путь к папке, содержащей пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd2cb-104">If you analyze files in the file system, provide a path to the folder that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd2cb-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="dd2cb-105">Options</span></span>  
 <span data-ttu-id="dd2cb-106">**Анализировать пакеты служб SSIS на компьютере**</span><span class="sxs-lookup"><span data-stu-id="dd2cb-106">**Analyze SSIS packages on Computer**</span></span>  
 <span data-ttu-id="dd2cb-107">Выберите этот параметр для анализа пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-107">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer.</span></span> <span data-ttu-id="dd2cb-108">По умолчанию этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-108">By default, this option is selected.</span></span>  
  
 <span data-ttu-id="dd2cb-109">**Анализировать файлы пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="dd2cb-109">**Analyze SSIS package files**</span></span>  
 <span data-ttu-id="dd2cb-110">Выберите этот параметр для анализа пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-110">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages in the file system.</span></span>  
  
 <span data-ttu-id="dd2cb-111">**Путь к пакетам служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="dd2cb-111">**Path to SSIS packages**</span></span>  
 <span data-ttu-id="dd2cb-112">Укажите UNC-путь или локальный адрес, по которому размещены пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd2cb-112">Locate a UNC or local path that holds your [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="dd2cb-113">Имена файлов включать не нужно.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-113">You do not have to include file names.</span></span> <span data-ttu-id="dd2cb-114">Если указанный путь недоступен, вы не сможете нажать кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-114">If the path you have entered cannot be accessed, you cannot click **Next**.</span></span> <span data-ttu-id="dd2cb-115">По умолчанию путь пустой.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-115">By default, the path is blank.</span></span> <span data-ttu-id="dd2cb-116">Это поле доступно только при выборе пункт **Анализ файлов пакетов служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="dd2cb-116">This field is enabled only when you select **Analyze SSIS package files**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2cb-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd2cb-117">See Also</span></span>  
 <span data-ttu-id="dd2cb-118">[Работа с советником по переходу](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="dd2cb-118">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="dd2cb-119">Справочник по пользовательскому интерфейсу помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="dd2cb-119">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
