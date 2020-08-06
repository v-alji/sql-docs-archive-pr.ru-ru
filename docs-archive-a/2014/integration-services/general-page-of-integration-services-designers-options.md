---
title: Страница "Общие" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Business_Intelligence_Designers.Data_Transformation_Designers.General
ms.assetid: d695690a-923b-4036-945e-7621e8651deb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59073ac29f95f1e64bd0a9382366e9539ce1408a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655848"
---
# <a name="general-page"></a><span data-ttu-id="f0f02-102">Страница «Общие»</span><span class="sxs-lookup"><span data-stu-id="f0f02-102">General Page</span></span>
  <span data-ttu-id="f0f02-103">Страница **Общие** страницы **Конструкторы служб Integration Services** диалогового окна **Параметры** позволяет указать параметры загрузки, отображения и обновления пакетов.</span><span class="sxs-lookup"><span data-stu-id="f0f02-103">Use the **General** page of the **Integration Services Designers** page in the **Options** dialog box to specify the options for loading, displaying, and upgrading packages.</span></span>  
  
 <span data-ttu-id="f0f02-104">Чтобы открыть страницу **Общие** , в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]в меню **Сервис** щелкните **Параметры**, раскройте **Конструкторы бизнес-аналитики**и выберите **Конструкторы служб Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="f0f02-104">To open the **General** page, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Tools** menu, click **Options**, expand **Business Intelligence Designers**, and select **Integration Services Designers**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0f02-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0f02-105">Options</span></span>  
 <span data-ttu-id="f0f02-106">**Проверка цифровой подписи при загрузке пакета**</span><span class="sxs-lookup"><span data-stu-id="f0f02-106">**Check digital signature when loading a package**</span></span>  
 <span data-ttu-id="f0f02-107">Установите этот флажок, чтобы службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] проверяли цифровую подпись при загрузке пакета</span><span class="sxs-lookup"><span data-stu-id="f0f02-107">Select to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] check the digital signature when loading a package.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f0f02-108">проверяют только наличие цифровой подписи, ее правильность и надежность источника.</span><span class="sxs-lookup"><span data-stu-id="f0f02-108">will only check whether the digital signature is present, is valid, and is from a trusted source.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f0f02-109">не проверяют, изменялся ли пакет с момента его подписания.</span><span class="sxs-lookup"><span data-stu-id="f0f02-109">will not check whether the package has been changed since the package was signed.</span></span>  
  
 <span data-ttu-id="f0f02-110">Если установлено значение реестра **BlockedSignatureStates** , оно переопределяет параметр **Проверять цифровую подпись при загрузке пакета** .</span><span class="sxs-lookup"><span data-stu-id="f0f02-110">If you set the **BlockedSignatureStates** registry value, this registry value overrides the **Check digital signature when loading a package** option.</span></span> <span data-ttu-id="f0f02-111">Дополнительные сведения см. в разделе [Реализация политики подписывания путем задания параметра реестра](implement-a-signing-policy-by-setting-a-registry-value.md).</span><span class="sxs-lookup"><span data-stu-id="f0f02-111">For more information, see [Implement a Signing Policy by Setting a Registry Value](implement-a-signing-policy-by-setting-a-registry-value.md).</span></span>  
  
 <span data-ttu-id="f0f02-112">Дополнительные сведения о цифровых сертификатах и пакетах см. в разделе [Определение источника пакетов с помощью цифровых подписей](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="f0f02-112">For more information about digital certificates and packages, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
 <span data-ttu-id="f0f02-113">**Показывать предупреждение, если пакет не подписан**</span><span class="sxs-lookup"><span data-stu-id="f0f02-113">**Show warning if package is unsigned**</span></span>  
 <span data-ttu-id="f0f02-114">Выберите этот параметр, чтобы отображать предупреждение при загрузке неподписанного пакета.</span><span class="sxs-lookup"><span data-stu-id="f0f02-114">Select to display a warning when loading a package that is not signed.</span></span>  
  
 <span data-ttu-id="f0f02-115">**Отобразить метки элементов управления очередностью**</span><span class="sxs-lookup"><span data-stu-id="f0f02-115">**Show precedence constraint labels**</span></span>  
 <span data-ttu-id="f0f02-116">Выберите метку "Успешно", "Ошибка" или "Завершение" для отображения объектов управления очередностью при просмотре пакетов в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0f02-116">Select which label-Success, Failure, or Completion-to display on precedence constraints when viewing packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f0f02-117">**Язык сценария**</span><span class="sxs-lookup"><span data-stu-id="f0f02-117">**Scripting language**</span></span>  
 <span data-ttu-id="f0f02-118">Выберите значение по умолчанию для языка скрипта новых задач «Скрипт» и компонентов скрипта.</span><span class="sxs-lookup"><span data-stu-id="f0f02-118">Select the default scripting language for new Script tasks and Script components.</span></span>  
  
 <span data-ttu-id="f0f02-119">**Обновить строки соединения для использования новых имен поставщиков**</span><span class="sxs-lookup"><span data-stu-id="f0f02-119">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="f0f02-120">При открытии или обновлении пакетов служб [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] обновите строки подключения, чтобы использовать в них принятые в текущем выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]имена следующих поставщиков:</span><span class="sxs-lookup"><span data-stu-id="f0f02-120">When opening or upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, update connection strings to use the names for the following providers, for the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="f0f02-121">Поставщик OLE DB</span><span class="sxs-lookup"><span data-stu-id="f0f02-121">OLE DB provider</span></span>  
  
-   <span data-ttu-id="f0f02-122">Собственный клиент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f02-122">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client</span></span>  
  
 <span data-ttu-id="f0f02-123">Мастер обновления пакетов [!INCLUDE[ssIS](../includes/ssis-md.md)] обновляет только те строки подключения, которые хранятся в диспетчерах соединений.</span><span class="sxs-lookup"><span data-stu-id="f0f02-123">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="f0f02-124">Мастер не обновляет строки соединения, которые формируются динамически с помощью языка выражений служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] или программно в задаче «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="f0f02-124">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="f0f02-125">**Создать новый идентификатор пакета**</span><span class="sxs-lookup"><span data-stu-id="f0f02-125">**Create new package ID**</span></span>  
 <span data-ttu-id="f0f02-126">При обновлении пакетов служб [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] создает новые идентификаторы пакетов для обновленных версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="f0f02-126">When upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, create new package IDs for the upgraded versions of the packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f02-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0f02-127">See Also</span></span>  
 <span data-ttu-id="f0f02-128">[Общие сведения о безопасности (службы Integration Services)](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="f0f02-128">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="f0f02-129">Расширение пакетов с помощью сценариев</span><span class="sxs-lookup"><span data-stu-id="f0f02-129">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
  
  
