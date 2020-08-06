---
title: Установка или изменение уровня защиты пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- passwords [Integration Services]
- packages [Integration Services],security
- security [Integration Services],protection levels
- protection level for packages [Integration Services]
ms.assetid: 904a5580-82ba-4a26-b0c5-d1c989975f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da8e63028498097b4321e4ef1383fbc8aa5845b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750024"
---
# <a name="set-or-change-the-protection-level-of-packages"></a><span data-ttu-id="36d30-102">Установка и изменение уровня защиты пакетов</span><span class="sxs-lookup"><span data-stu-id="36d30-102">Set or Change the Protection Level of Packages</span></span>
  <span data-ttu-id="36d30-103">Для управления доступом к содержимому пакетов и конфиденциальным данным в них, таким как пароли, необходимо задать значение свойства `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="36d30-103">To control access to the contents of packages and to the sensitive values that they contain, such as passwords, set the value of the `ProtectionLevel` property.</span></span> <span data-ttu-id="36d30-104">Пакеты, которые содержатся в проекте, должны обладать тем же уровнем защиты, что и сам проект. Это необходимо для создания проекта.</span><span class="sxs-lookup"><span data-stu-id="36d30-104">The packages contained in a project need to have the same protection level as the project, to build the project.</span></span> <span data-ttu-id="36d30-105">При изменении настройки свойства `ProtectionLevel` в проекте потребуется вручную обновить настройку свойства для пакетов.</span><span class="sxs-lookup"><span data-stu-id="36d30-105">If you change the `ProtectionLevel` property setting on the project, you need to manually update the property setting for the packages.</span></span>  
  
 <span data-ttu-id="36d30-106">Сведения о том, как определить `ProtectionLevel` Параметры, подходящие для пакетов на разных этапах жизненного цикла пакета, см. в разделе [Управление доступом для конфиденциальных данных в пакетах](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="36d30-106">For information about how to determine the `ProtectionLevel` settings that are appropriate for your packages at different stages in the package life cycle, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span> <span data-ttu-id="36d30-107">Общие сведения о средствах безопасности в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] см. в разделе [Общие сведения о безопасности (службы Integration Services)](security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="36d30-107">For an overview of security features in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], see [Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span></span>  
  
 <span data-ttu-id="36d30-108">В приведенной в данном разделе процедуре описано использование [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] или средства командной dtutil для изменения свойства `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="36d30-108">The procedures in this topic describe how to use either [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or the dtutil command prompt utility to change the `ProtectionLevel` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36d30-109">В дополнение к приведенной в этом разделе процедуре можно, как правило, задать или изменить свойство пакета `ProtectionLevel` при импорте или экспорте пакета.</span><span class="sxs-lookup"><span data-stu-id="36d30-109">In addition to the procedures in this topic, you can typically set or change the `ProtectionLevel` property of a package when you import or export the package.</span></span> <span data-ttu-id="36d30-110">Если сохранение пакета производится с помощью мастера импорта и экспорта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], то можно также изменить свойство `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="36d30-110">You can also change the `ProtectionLevel` property of a package when you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to save a package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-a-package-in-sql-server-data-tools"></a><span data-ttu-id="36d30-111">Установка или изменение уровня защиты пакета в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="36d30-111">To set or change the protection level of a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="36d30-112">Проверьте доступные значения `ProtectionLevel` свойства в разделе [Настройка уровня защиты пакетов](security/access-control-for-sensitive-data-in-packages.md)и определите соответствующее значение для пакета.</span><span class="sxs-lookup"><span data-stu-id="36d30-112">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="36d30-113">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет.</span><span class="sxs-lookup"><span data-stu-id="36d30-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package.</span></span>  
  
3.  <span data-ttu-id="36d30-114">Откройте пакет в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36d30-114">Open the package in the [!INCLUDE[ssIS](../includes/ssis-md.md)] designer.</span></span>  
  
4.  <span data-ttu-id="36d30-115">Если свойства пакета не отображаются в окне свойств, щелкните область конструктора.</span><span class="sxs-lookup"><span data-stu-id="36d30-115">If the Properties window does not show the properties of the package, click the design surface.</span></span>  
  
5.  <span data-ttu-id="36d30-116">В окно свойств в группе **Безопасность** выберите соответствующее значение для `ProtectionLevel` Свойства.</span><span class="sxs-lookup"><span data-stu-id="36d30-116">In the Properties window, in the **Security** group, select the appropriate value for the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="36d30-117">Если выбран уровень защиты, для которого требуется пароль, введите пароль в качестве значения свойства **PackagePassword** .</span><span class="sxs-lookup"><span data-stu-id="36d30-117">If you select a protection level that requires a password, enter the password as the value of the **PackagePassword** property.</span></span>  
  
6.  <span data-ttu-id="36d30-118">Чтобы сохранить пакет, в меню **Файл** выберите пункт **Сохранить выбранные элементы** .</span><span class="sxs-lookup"><span data-stu-id="36d30-118">On the **File** menu, select **Save Selected Items** to save the modified package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-packages-at-the-command-prompt"></a><span data-ttu-id="36d30-119">Установка или изменение уровня защиты пакетов в командной строке</span><span class="sxs-lookup"><span data-stu-id="36d30-119">To set or change the protection level of packages at the command prompt</span></span>  
  
1.  <span data-ttu-id="36d30-120">Проверьте доступные значения `ProtectionLevel` свойства в разделе [Настройка уровня защиты пакетов](security/access-control-for-sensitive-data-in-packages.md)и определите соответствующее значение для пакета.</span><span class="sxs-lookup"><span data-stu-id="36d30-120">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="36d30-121">Проверьте сопоставления для `Encrypt` параметра в разделе [программа dtutil](dtutil-utility.md)и определите соответствующее целое число, которое будет использоваться в качестве значения выбранного `ProtectionLevel` Свойства.</span><span class="sxs-lookup"><span data-stu-id="36d30-121">Review the mappings for the `Encrypt` option in the topic, [dtutil Utility](dtutil-utility.md), and determine the appropriate integer to use as the value of the selected `ProtectionLevel` property.</span></span>  
  
3.  <span data-ttu-id="36d30-122">Откройте окно командной строки и</span><span class="sxs-lookup"><span data-stu-id="36d30-122">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="36d30-123">В командной строке перейдите к папке с пакетом или пакетами, для которых требуется задать свойство `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="36d30-123">At the command prompt, navigate to the folder that contains the package or packages for which you want to set the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="36d30-124">В примерах синтаксиса в следующем шаге предполагается, что эта папка является текущей папкой.</span><span class="sxs-lookup"><span data-stu-id="36d30-124">The syntax examples shown in the following step assume that this folder is the current folder.</span></span>  
  
5.  <span data-ttu-id="36d30-125">Установите или измените уровень защиты пакета или пакетов при помощи команды, подобно показанной в одном из следующих примеров.</span><span class="sxs-lookup"><span data-stu-id="36d30-125">Set or change the protection level of the package or packages by using a command similar to the one of the following examples:</span></span>  
  
    -   <span data-ttu-id="36d30-126">Следующая команда задает свойство `ProtectionLevel` отдельного пакета в файловой системе равным уровню 2 – «Шифровать конфиденциальные данные паролем» с паролем «strongpassword»:</span><span class="sxs-lookup"><span data-stu-id="36d30-126">The following command sets the `ProtectionLevel` property of an individual package in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `dtutil.exe /file "C:\Package.dtsx" /encrypt file;"C:\Package.dtsx";2;strongpassword`  
  
    -   <span data-ttu-id="36d30-127">Следующая команда задает свойство `ProtectionLevel` всех пакетов в определенной папке файловой системы равным уровню 2 – «Шифровать конфиденциальные данные паролем» с паролем «strongpassword»:</span><span class="sxs-lookup"><span data-stu-id="36d30-127">The following command sets the `ProtectionLevel` property of all packages in a particular folder in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `for %f in (*.dtsx) do dtutil.exe /file %f /encrypt file;%f;2;strongpassword`  
  
         <span data-ttu-id="36d30-128">Если подобную команду использовать в пакетном файле, то в него необходимо включить заполнитель «%f» в виде «%%f».</span><span class="sxs-lookup"><span data-stu-id="36d30-128">If you use a similar command in a batch file, enter the file placeholder, "%f", as "%%f" in the batch file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d30-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="36d30-129">See Also</span></span>  
 [<span data-ttu-id="36d30-130">Программа dtutil</span><span class="sxs-lookup"><span data-stu-id="36d30-130">dtutil Utility</span></span>](dtutil-utility.md)  
  
  
