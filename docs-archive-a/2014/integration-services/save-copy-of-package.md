---
title: Сохранить копию пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.savecopyas.f1
helpviewer_keywords:
- Save Copy of Package dialog box
ms.assetid: 7b44c0d7-d8fa-4491-8836-0899f621d3a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f0a685d8b38299e1ba1d03c4ec8c1052cc957dbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738516"
---
# <a name="save-copy-of-package"></a><span data-ttu-id="a97ea-102">Сохранение копии пакета</span><span class="sxs-lookup"><span data-stu-id="a97ea-102">Save Copy of Package</span></span>
  <span data-ttu-id="a97ea-103">Используйте диалоговое окно **Сохранение копии пакета** , доступное в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], чтобы сохранить копию пакета служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] из среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] в другое местоположение и в случае необходимости изменить уровень защиты пакета.</span><span class="sxs-lookup"><span data-stu-id="a97ea-103">Use the **Save Copy of Package** dialog box, available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], to save a copy of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to a different location and, optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a97ea-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="a97ea-104">Options</span></span>  
 <span data-ttu-id="a97ea-105">**Размещение пакета**</span><span class="sxs-lookup"><span data-stu-id="a97ea-105">**Package location**</span></span>  
 <span data-ttu-id="a97ea-106">Выберите тип места хранения, в котором должна быть сохранена копия пакета.</span><span class="sxs-lookup"><span data-stu-id="a97ea-106">Select the type of storage location in which to save the package copy.</span></span> <span data-ttu-id="a97ea-107">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="a97ea-107">The following options are available:</span></span>  
  
 <span data-ttu-id="a97ea-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a97ea-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="a97ea-109">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="a97ea-109">**File System**</span></span>  
  
 <span data-ttu-id="a97ea-110">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="a97ea-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="a97ea-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="a97ea-111">**Server**</span></span>  
 <span data-ttu-id="a97ea-112">Введите имя сервера или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="a97ea-112">Type a server name or select a server from the list.</span></span> <span data-ttu-id="a97ea-113">Этот параметр доступен, только если в качестве места хранения указан **SQL Server** или **Хранилище пакетов служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="a97ea-113">This option is available only if the storage location is **SQL Server** or **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="a97ea-114">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="a97ea-114">**Authentication**</span></span>  
 <span data-ttu-id="a97ea-115">Выберите проверку подлинности Windows или проверку подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a97ea-115">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="a97ea-116">Этот параметр доступен, только если в качестве места хранения указан [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a97ea-116">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a97ea-117">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="a97ea-117">Whenever possible use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a97ea-118">**Тип проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="a97ea-118">**Authentication type**</span></span>  
 <span data-ttu-id="a97ea-119">Выберите тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a97ea-119">Select an authentication type.</span></span>  
  
 <span data-ttu-id="a97ea-120">**User name**</span><span class="sxs-lookup"><span data-stu-id="a97ea-120">**User name**</span></span>  
 <span data-ttu-id="a97ea-121">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="a97ea-121">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="a97ea-122">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="a97ea-122">**Password**</span></span>  
 <span data-ttu-id="a97ea-123">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="a97ea-123">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="a97ea-124">**Путь пакета**</span><span class="sxs-lookup"><span data-stu-id="a97ea-124">**Package path**</span></span>  
 <span data-ttu-id="a97ea-125">Введите путь к пакету или нажмите кнопку обзора **(...)** и найдите папку, в которой будет сохранен пакет.</span><span class="sxs-lookup"><span data-stu-id="a97ea-125">Type the package path, or click the browse **(...)** button and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="a97ea-126">**Уровень защиты**</span><span class="sxs-lookup"><span data-stu-id="a97ea-126">**Protection level**</span></span>  
 <span data-ttu-id="a97ea-127">Нажмите кнопку обзора **(...)** и обновите уровень защиты в диалоговом окне **уровень защиты пакета** .</span><span class="sxs-lookup"><span data-stu-id="a97ea-127">Click the browse **(...)** button and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="a97ea-128">Дополнительные сведения см. в разделе [Диалоговое окно уровня защиты пакета и проекта](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="a97ea-128">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97ea-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="a97ea-129">See Also</span></span>  
 <span data-ttu-id="a97ea-130">[Справочник по пользовательскому интерфейсу диалогового окна "Импорт пакета"](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a97ea-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="a97ea-131">[Справочник по пользовательскому интерфейсу диалогового окна экспорта пакета](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a97ea-131">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="a97ea-132">[Сохранение пакетов](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a97ea-132">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="a97ea-133">Импорт и экспорт пакетов (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="a97ea-133">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
