---
title: Версии SQL Server на разных языках | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 20b99363-0490-4aa3-9a3d-262f827d81e8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646ffaed1e4b709c2c26030379f0a7f223f221e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730037"
---
# <a name="local-language-versions-in-sql-server"></a><span data-ttu-id="a6dc6-102">Версии SQL Server на местных языках</span><span class="sxs-lookup"><span data-stu-id="a6dc6-102">Local Language Versions in SQL Server</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a6dc6-103">поддерживает все языки, поддерживаемые операционными системами Windows.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-103">supports all languages that are supported by Windows operating systems.</span></span>  
  
## <a name="cross-language-support"></a><span data-ttu-id="a6dc6-104">Поддержка версий на разных языках</span><span class="sxs-lookup"><span data-stu-id="a6dc6-104">Cross-Language Support</span></span>  
  
-   <span data-ttu-id="a6dc6-105">Английская версия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживается на всех локализованных версиях операционных систем.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-105">The English-language version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is supported on all localized versions of operating systems.</span></span>  
  
-   <span data-ttu-id="a6dc6-106">Локализованные версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживаются в локализованных операционных системах с соответствующими языками или в версиях поддерживаемых операционных систем для английского языка с пакетом многоязыкового пользовательского интерфейса Windows (MUI).</span><span class="sxs-lookup"><span data-stu-id="a6dc6-106">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on localized operating systems with the corresponding language or on English-language versions of supported operating systems by using the Windows Multilingual User Interface Pack (MUI) settings.</span></span> <span data-ttu-id="a6dc6-107">Дополнительные сведения см. в разделе [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span><span class="sxs-lookup"><span data-stu-id="a6dc6-107">For more information, see [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span></span>  
  
-   <span data-ttu-id="a6dc6-108">Локализованные версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут быть обновлены только до локализованных версий на том же языке. Они не могут быть обновлены до версии на английском языке.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-108">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can only be upgraded to localized versions of the same language, and cannot be upgraded to the English-language version.</span></span>  
  
-   <span data-ttu-id="a6dc6-109">Локализованные версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут быть также установлены параллельно с англоязычными экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6dc6-109">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can also be installed side by side with English-language instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="configure-operating-system-to-support-localized-versions"></a><a name="BK_ConfigureOS"></a> <span data-ttu-id="a6dc6-110">Configure Operating System to Support Localized Versions</span><span class="sxs-lookup"><span data-stu-id="a6dc6-110">Configure Operating System to Support Localized Versions</span></span>  
 <span data-ttu-id="a6dc6-111">Локализованные версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживаются в английских версиях поддерживаемых операционных систем с помощью пакета многоязыкового пользовательского интерфейса Windows.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-111">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on English-language versions of supported operating systems through the use of Windows Multilingual User Interface Pack (MUI) settings.</span></span>  
  
 <span data-ttu-id="a6dc6-112">Однако перед установкой локализованной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на сервер, работающий под управлением англоязычной версии операционной системы с установленным пакетом многоязыкового пользовательского интерфейса, в котором выбран другой язык, необходимо проверить некоторые настройки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-112">However, you must verify certain operating system settings before installing a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a server that is running an English-language operating system with a non-English MUI setting.</span></span> <span data-ttu-id="a6dc6-113">Необходимо убедиться, что следующие настройки операционной системы соответствуют языку локализации устанавливаемой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a6dc6-113">You need to verify that the following operating system settings match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed:</span></span>  
  
-   <span data-ttu-id="a6dc6-114">Настройки пользовательского интерфейса операционной системы</span><span class="sxs-lookup"><span data-stu-id="a6dc6-114">The operating system user interface setting</span></span>  
  
-   <span data-ttu-id="a6dc6-115">Пользовательские настройки локали операционной системы</span><span class="sxs-lookup"><span data-stu-id="a6dc6-115">The operating system user locale setting</span></span>  
  
-   <span data-ttu-id="a6dc6-116">Настройки локали системы</span><span class="sxs-lookup"><span data-stu-id="a6dc6-116">The system locale setting</span></span>  
  
 <span data-ttu-id="a6dc6-117">Если настройки не соответствуют языку локализации устанавливаемой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используйте следующие процедуры, чтобы правильно установить эти параметры операционной системы.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-117">If the settings do not match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed, then use the following procedures to correctly set these operating system settings.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a6dc6-118">Установка нескольких экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с разными языками на одном компьютере не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-118">Installations of different language versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances on the same computer are not supported.</span></span>  
  
#### <a name="to-change-the-operating-system-user-interface-setting"></a><span data-ttu-id="a6dc6-119">Изменение настройки пользовательского интерфейса операционной системы</span><span class="sxs-lookup"><span data-stu-id="a6dc6-119">To change the operating system user interface setting</span></span>  
  
1.  <span data-ttu-id="a6dc6-120">При необходимости установите интерфейс MUI операционной системы, соответствующий локализованным версиям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6dc6-120">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6dc6-121">На панели управления откройте **Язык и региональные стандарты**.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-121">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="a6dc6-122">На закладке **Языки** на панели **Язык, используемый в меню и диалоговых окнах**выберите значение из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-122">On the **Languages** tab, for **Language used in menus and dialogs**, select a value from the list.</span></span>  
  
     <span data-ttu-id="a6dc6-123">Этот параметр влияет на язык интерфейса пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], поэтому он должен совпадать с версией локализации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6dc6-123">This setting will affect the user interface language of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so it must match your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="a6dc6-124">Нажмите кнопку **Применить** , чтобы подтвердить изменения, а затем **ОК** , чтобы закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-124">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-operating-system-user-locale-setting"></a><span data-ttu-id="a6dc6-125">Изменение настройки локали операционной системы</span><span class="sxs-lookup"><span data-stu-id="a6dc6-125">To change the operating system user locale setting</span></span>  
  
1.  <span data-ttu-id="a6dc6-126">При необходимости установите интерфейс MUI операционной системы, соответствующий локализованным версиям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6dc6-126">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6dc6-127">На панели управления откройте **Язык и региональные стандарты**.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-127">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="a6dc6-128">На вкладке **Региональные параметры** выберите значение из раскрывающегося списка в области **Языковые стандарты и форматы**.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-128">On the **Regional Options** tab, for **Select an item to match its preferences**, select a value from the list.</span></span>  
  
     <span data-ttu-id="a6dc6-129">Этот параметр повлияет на форматирование данных, характерное для страны.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-129">This setting will affect culture-specific data formatting.</span></span>  
  
4.  <span data-ttu-id="a6dc6-130">Нажмите кнопку **Применить** , чтобы подтвердить изменения, а затем **ОК** , чтобы закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-130">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-system-locale-setting"></a><span data-ttu-id="a6dc6-131">Изменение настройки локали системы</span><span class="sxs-lookup"><span data-stu-id="a6dc6-131">To change the system locale setting</span></span>  
  
1.  <span data-ttu-id="a6dc6-132">При необходимости установите интерфейс MUI операционной системы, соответствующий локализованным версиям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6dc6-132">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6dc6-133">На панели управления откройте **Язык и региональные стандарты**.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-133">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="a6dc6-134">На вкладке **Дополнительно** в области **Язык программ, не поддерживающих Юникод**выберите значение из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-134">On the **Advanced** tab, for **Select a language to match the language version of the non-Unicode programs you want to use**, select a value from the list.</span></span>  
  
     <span data-ttu-id="a6dc6-135">Эта настройка дает возможность программе установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выбрать наилучшие параметры сортировки по умолчанию для установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6dc6-135">This setting will allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to choose the best default collation for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
4.  <span data-ttu-id="a6dc6-136">Нажмите кнопку **Применить** , чтобы подтвердить изменения, а затем **ОК** , чтобы закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="a6dc6-136">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dc6-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6dc6-137">See Also</span></span>  
 <span data-ttu-id="a6dc6-138">[Требования к оборудованию и программному обеспечению для установки SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a6dc6-138">[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 [<span data-ttu-id="a6dc6-139">Установка SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a6dc6-139">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
