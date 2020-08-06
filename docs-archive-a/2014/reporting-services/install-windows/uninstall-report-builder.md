---
title: Удаление изолированной версии построитель отчетов (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 009538c6-4941-4393-b14b-9144cffdbdaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cda13248d1aa14ee3d57a951872d3ad8ded17da9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666961"
---
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="751ad-102">Удаление изолированной версии построителя отчетов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="751ad-102">Uninstall the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="751ad-103">Изолированную версию построителя отчетов можно удалить с помощью панели управления или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="751ad-103">You can uninstall the stand-alone version of Report Builder from the control panel or the command line.</span></span> <span data-ttu-id="751ad-104">Удалить версию [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] построителя отчетов невозможно без удаления служб [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="751ad-104">You cannot uninstall the [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] version of Report Builder without uninstalling [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="751ad-105">Удаление построителя отчетов из командной строки использует синтаксис, совпадающий с синтаксисом, используемым при установке построителя отчетов, за исключением того, что необходимо использовать параметр /x вместо параметра /i.</span><span class="sxs-lookup"><span data-stu-id="751ad-105">Uninstalling Report Builder from the command line uses syntax that is identical to the syntax you use to install Report Builder, except you use the /x option instead of the /i option.</span></span> <span data-ttu-id="751ad-106">Командная строка, предназначенная для удаления, может включать параметр /quiet и другие стандартные параметры.</span><span class="sxs-lookup"><span data-stu-id="751ad-106">Command lines for uninstalling can also include the /quiet option and other standard options.</span></span> <span data-ttu-id="751ad-107">Если пакет установщика Windows для построителя отчетов (ReportBuilder3_x86.msi) был удален, то для удаления построителя отчетов пользоваться командной строкой будет неудобно.</span><span class="sxs-lookup"><span data-stu-id="751ad-107">If the Report Builder Windows Installer Package (ReportBuilder3_x86.msi) has been removed, you cannot use the command line easily to uninstall Report Builder.</span></span> <span data-ttu-id="751ad-108">Дополнительные сведения о возможности удаления построителя отчетов при помощи его идентификатора GUID см. в документации по программе msiexec в библиотеке msdn.</span><span class="sxs-lookup"><span data-stu-id="751ad-108">To learn more about how you might be able to remove Report Builder by using its GUID, see the documentation for the msiexec program in the msdn library.</span></span>  
  
 <span data-ttu-id="751ad-109">Если папки, используемые построителем отчетов, содержат пользовательские файлы, то при удалении построителя отчетов эти папки и файлы сохраняются.</span><span class="sxs-lookup"><span data-stu-id="751ad-109">If folders used by Report Builder include custom files, the folders and the files are preserved when Report Builder is removed.</span></span> <span data-ttu-id="751ad-110">Удаляются только файлы построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="751ad-110">Only the Report Builder files are removed.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a><span data-ttu-id="751ad-111">Удаление построителя отчетов с панели управления</span><span class="sxs-lookup"><span data-stu-id="751ad-111">To uninstall Report Builder from the control panel</span></span>  
  
1.  <span data-ttu-id="751ad-112">В меню **Пуск** выберите пункт **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="751ad-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="751ad-113">На панели управления щелкните элемент **Программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="751ad-113">In the Control Panel, click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="751ad-114">Найдите построитель отчетов «  » в списке Имя и щелкните его.</span><span class="sxs-lookup"><span data-stu-id="751ad-114">Locate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Builder in the **Name** list and click it.</span></span>  
  
4.  <span data-ttu-id="751ad-115">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="751ad-115">Click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="751ad-116">Если понадобится подтвердить удаление построителя отчетов, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="751ad-116">If prompted to confirm the uninstall of Report Builder, click **Yes**.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a><span data-ttu-id="751ad-117">Удаление построителя отчетов из командной строки</span><span class="sxs-lookup"><span data-stu-id="751ad-117">To uninstall Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="751ad-118">В меню **Пуск** выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="751ad-118">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="751ad-119">В текстовом поле **Открыть** введите`cmd.`</span><span class="sxs-lookup"><span data-stu-id="751ad-119">In the **Open** text box, type `cmd.`</span></span>  
  
3.  <span data-ttu-id="751ad-120">В окне командной строки перейдите к папке, содержащей файл ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="751ad-120">In the command prompt window, navigate to the folder with ReportBuilder3_x86.msi.</span></span>  
  
4.  <span data-ttu-id="751ad-121">Введите следующую обычную командную строку:</span><span class="sxs-lookup"><span data-stu-id="751ad-121">Type a basic command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 <span data-ttu-id="751ad-122">При необходимости включения ведения журнала используйте следующую командную строку:</span><span class="sxs-lookup"><span data-stu-id="751ad-122">If you can to include logging, use a command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  <span data-ttu-id="751ad-123">Нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="751ad-123">Press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751ad-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="751ad-124">See Also</span></span>  
 <span data-ttu-id="751ad-125">[Поддержка установки, удаления и построитель отчетов](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="751ad-125">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="751ad-126">Установите изолированную версию построитель отчетов &#40;построитель отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="751ad-126">Install the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
