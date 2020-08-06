---
title: Справочник по пользовательскому интерфейсу диалогового окна "Импорт пакета" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.importpackage.f1
helpviewer_keywords:
- Import Package dialog box
ms.assetid: 0e5fb127-c7ff-4dfa-b90e-d9bcf0ce763b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff20bf8eb221778465a26944280d53b6aab07601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664413"
---
# <a name="import-package-dialog-box-ui-reference"></a><span data-ttu-id="3d408-102">Диалоговое окно «Импорт пакета» справочника по пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="3d408-102">Import Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="3d408-103">Диалоговое окно **Импорт пакета** , доступное в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], позволяет импортировать пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и задавать или изменять уровень защиты пакета.</span><span class="sxs-lookup"><span data-stu-id="3d408-103">Use the **Import Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to import a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and to set or modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3d408-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d408-104">Options</span></span>  
 <span data-ttu-id="3d408-105">**Размещение пакета**</span><span class="sxs-lookup"><span data-stu-id="3d408-105">**Package location**</span></span>  
 <span data-ttu-id="3d408-106">Выберите тип места хранения, в которое импортировать пакет.</span><span class="sxs-lookup"><span data-stu-id="3d408-106">Select the type of storage location to import the package to.</span></span> <span data-ttu-id="3d408-107">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="3d408-107">The following options are available:</span></span>  
  
 <span data-ttu-id="3d408-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3d408-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="3d408-109">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="3d408-109">**File System**</span></span>  
  
 <span data-ttu-id="3d408-110">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="3d408-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="3d408-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="3d408-111">**Server**</span></span>  
 <span data-ttu-id="3d408-112">Введите имя сервера или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="3d408-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="3d408-113">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="3d408-113">**Authentication**</span></span>  
 <span data-ttu-id="3d408-114">Выберите проверку подлинности Windows или проверку подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d408-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="3d408-115">Этот параметр доступен, только если в качестве места хранения указан [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d408-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3d408-116">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="3d408-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="3d408-117">**Тип проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="3d408-117">**Authentication type**</span></span>  
 <span data-ttu-id="3d408-118">Выберите тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3d408-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="3d408-119">**User name**</span><span class="sxs-lookup"><span data-stu-id="3d408-119">**User name**</span></span>  
 <span data-ttu-id="3d408-120">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d408-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="3d408-121">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="3d408-121">**Password**</span></span>  
 <span data-ttu-id="3d408-122">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="3d408-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="3d408-123">**Путь пакета**</span><span class="sxs-lookup"><span data-stu-id="3d408-123">**Package path**</span></span>  
 <span data-ttu-id="3d408-124">Введите путь к пакету или нажмите кнопку просмотра **(…)** и определите местоположение пакета.</span><span class="sxs-lookup"><span data-stu-id="3d408-124">Type the package path, or click the browse button **(...)** and locate the package.</span></span>  
  
 <span data-ttu-id="3d408-125">**Имя пакета**</span><span class="sxs-lookup"><span data-stu-id="3d408-125">**Package name**</span></span>  
 <span data-ttu-id="3d408-126">При необходимости переименуйте пакет.</span><span class="sxs-lookup"><span data-stu-id="3d408-126">Optionally, rename the package.</span></span> <span data-ttu-id="3d408-127">По умолчанию это имя импортируемого пакета.</span><span class="sxs-lookup"><span data-stu-id="3d408-127">The default name is the name of the package to import.</span></span>  
  
 <span data-ttu-id="3d408-128">**Уровень защиты**</span><span class="sxs-lookup"><span data-stu-id="3d408-128">**Protection level**</span></span>  
 <span data-ttu-id="3d408-129">Щелкните кнопку просмотра **(…)** и измените уровень защиты в диалоговом окне **Уровень защиты пакета**.</span><span class="sxs-lookup"><span data-stu-id="3d408-129">Click the browse button **(...)** and, in the **Package Protection Level** dialog box, update the protection level.</span></span> <span data-ttu-id="3d408-130">Дополнительные сведения см. в разделе [Диалоговое окно уровня защиты пакета и проекта](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3d408-130">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d408-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d408-131">See Also</span></span>  
 <span data-ttu-id="3d408-132">[Сохранить копию пакета](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="3d408-132">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="3d408-133">[Справочник по пользовательскому интерфейсу диалогового окна экспорта пакета](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3d408-133">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="3d408-134">[Сохранение пакетов](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3d408-134">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="3d408-135">Импорт и экспорт пакетов (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="3d408-135">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
