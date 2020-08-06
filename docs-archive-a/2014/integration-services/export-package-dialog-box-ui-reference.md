---
title: Справочник по пользовательскому интерфейсу диалогового окна экспорта пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752296"
---
# <a name="export-package-dialog-box-ui-reference"></a><span data-ttu-id="3a33c-102">Диалоговое окно «Экспорт пакета» справочника по пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="3a33c-102">Export Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="3a33c-103">Диалоговое окно **Экспорт пакета** , доступное в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], используется для экспорта пакета служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в другое место и, при необходимости, изменения уровня защиты пакета.</span><span class="sxs-lookup"><span data-stu-id="3a33c-103">Use the **Export Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to export a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package to a different location and optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3a33c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a33c-104">Options</span></span>  
 <span data-ttu-id="3a33c-105">**Размещение пакета**</span><span class="sxs-lookup"><span data-stu-id="3a33c-105">**Package location**</span></span>  
 <span data-ttu-id="3a33c-106">Выберите тип хранилища для экспорта пакета.</span><span class="sxs-lookup"><span data-stu-id="3a33c-106">Select the type of storage to export the package to.</span></span> <span data-ttu-id="3a33c-107">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="3a33c-107">The following options are available:</span></span>  
  
 <span data-ttu-id="3a33c-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3a33c-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="3a33c-109">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="3a33c-109">**File System**</span></span>  
  
 <span data-ttu-id="3a33c-110">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="3a33c-110">**SSIS Package Storage**</span></span>  
  
 <span data-ttu-id="3a33c-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="3a33c-111">**Server**</span></span>  
 <span data-ttu-id="3a33c-112">Введите имя сервера или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="3a33c-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="3a33c-113">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="3a33c-113">**Authentication**</span></span>  
 <span data-ttu-id="3a33c-114">Выберите проверку подлинности Windows или проверку подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a33c-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="3a33c-115">Этот параметр доступен, только если в качестве места хранения указан [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a33c-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a33c-116">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="3a33c-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="3a33c-117">**Тип проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="3a33c-117">**Authentication type**</span></span>  
 <span data-ttu-id="3a33c-118">Выберите тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3a33c-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="3a33c-119">**User name**</span><span class="sxs-lookup"><span data-stu-id="3a33c-119">**User name**</span></span>  
 <span data-ttu-id="3a33c-120">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a33c-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="3a33c-121">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="3a33c-121">**Password**</span></span>  
 <span data-ttu-id="3a33c-122">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите пароль.</span><span class="sxs-lookup"><span data-stu-id="3a33c-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="3a33c-123">**Путь пакета**</span><span class="sxs-lookup"><span data-stu-id="3a33c-123">**Package path**</span></span>  
 <span data-ttu-id="3a33c-124">Введите путь модуля или нажмите кнопку обзора **(...)** и выберите папку, в которой должен быть сохранен пакет.</span><span class="sxs-lookup"><span data-stu-id="3a33c-124">Type the package path, or click the browse button **(...)** and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="3a33c-125">**Уровень защиты**</span><span class="sxs-lookup"><span data-stu-id="3a33c-125">**Protection level**</span></span>  
 <span data-ttu-id="3a33c-126">Нажмите кнопку обзора **(...)** и обновите уровень защиты в диалоговом окне **Уровень защиты пакета**.</span><span class="sxs-lookup"><span data-stu-id="3a33c-126">Click the browse button **(...)** and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="3a33c-127">Дополнительные сведения см. в разделе [Диалоговое окно уровня защиты пакета и проекта](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3a33c-127">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a33c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a33c-128">See Also</span></span>  
 <span data-ttu-id="3a33c-129">[Сохранить копию пакета](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="3a33c-129">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="3a33c-130">[Справочник по пользовательскому интерфейсу диалогового окна "Импорт пакета"](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3a33c-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="3a33c-131">[Сохранение пакетов](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3a33c-131">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="3a33c-132">Импорт и экспорт пакетов (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="3a33c-132">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
