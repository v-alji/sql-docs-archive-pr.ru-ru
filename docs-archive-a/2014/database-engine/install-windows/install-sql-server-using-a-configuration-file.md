---
title: Установка SQL Server 2014 с помощью файла конфигурации | Документация Майкрософт
ms.custom: ''
ms.date: 01/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: a832153a-6775-4bed-83f0-55790766d885
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a2f09ad6253762fe5b525f6c918931f4806c84c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729757"
---
# <a name="install-sql-server-2014-using-a-configuration-file"></a><span data-ttu-id="e587b-102">установить SQL Server 2014 с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e587b-102">Install SQL Server 2014 Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e587b-103">Программа установки предоставляет возможность создать файл конфигурации на основе системных значений по умолчанию и значений, вводимых во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e587b-103">Setup provides the ability to generate a configuration file based upon the system default and run-time inputs.</span></span> <span data-ttu-id="e587b-104">Файл конфигурации может быть использован для развертывания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на всем предприятии с одной и той же конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="e587b-104">You can use the configuration file to deploy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] throughout the enterprise with the same configuration.</span></span> <span data-ttu-id="e587b-105">Стандартизировать установки в ручном режиме на территории предприятия также можно, создав пакетный файл, запускающий файл Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="e587b-105">You can also standardize manual installations throughout the enterprise, by creating a batch file that launches Setup.exe.</span></span>  
  
 <span data-ttu-id="e587b-106">Программа установки поддерживает использование файлов конфигурации только через командную строку.</span><span class="sxs-lookup"><span data-stu-id="e587b-106">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="e587b-107">Порядок обработки параметров при использовании файла конфигурации описывается ниже.</span><span class="sxs-lookup"><span data-stu-id="e587b-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="e587b-108">Файл конфигурации перезаписывает значения по умолчанию в пакете.</span><span class="sxs-lookup"><span data-stu-id="e587b-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="e587b-109">Значения командной строки перезаписывают значения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e587b-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="e587b-110">Файл конфигурации может быть использован для нахождения параметров и значений для каждой установки.</span><span class="sxs-lookup"><span data-stu-id="e587b-110">The configuration file can be used to track the parameters and values for each installation.</span></span> <span data-ttu-id="e587b-111">В связи с этим файл конфигурации может быть полезен при проверке и аудите установок.</span><span class="sxs-lookup"><span data-stu-id="e587b-111">This makes the configuration file useful for verifying and auditing the installations.</span></span>  
  
## <a name="configuration-file-structure"></a><span data-ttu-id="e587b-112">Структура файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e587b-112">Configuration File Structure</span></span>  
 <span data-ttu-id="e587b-113">Файл ConfigurationFile.ini — это текстовый файл с параметрами (пара «имя-значение») и комментариями с описанием.</span><span class="sxs-lookup"><span data-stu-id="e587b-113">The ConfigurationFile.ini file is a text file with parameters (name/value pair) and descriptive comments.</span></span>  
  
 <span data-ttu-id="e587b-114">Пример файла ConfigurationFile.ini:</span><span class="sxs-lookup"><span data-stu-id="e587b-114">The following is an example of a ConfigurationFile.ini file:</span></span>  
  
```  
; Microsoft SQL Server Configuration file  
[OPTIONS]  
; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE.   
; This is a required parameter.   
ACTION="Install"  
; Specifies features to install, uninstall, or upgrade.   
; The list of top-level features include SQL, AS, RS, IS, and Tools.   
; The SQL feature will install the database engine, replication, and full-text.   
; The Tools feature will install Management Tools, Books online,   
; SQL Server Data Tools, and other shared components.   
FEATURES=SQL,Tools  
```  
  
#### <a name="how-to-generate-a-configuration-file"></a><span data-ttu-id="e587b-115">Создание файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e587b-115">How to generate a configuration file</span></span>  
  
1.  <span data-ttu-id="e587b-116">Вставьте установочный носитель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e587b-116">Insert the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="e587b-117">В корневой папке дважды щелкните файл Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="e587b-117">From the root folder, double-click Setup.exe.</span></span> <span data-ttu-id="e587b-118">Чтобы выполнить установку из общей сетевой папки, перейдите в корневую папку общего ресурса и дважды щелкните файл setup.exe.</span><span class="sxs-lookup"><span data-stu-id="e587b-118">To install from a network share, locate the root folder on the share, and then double-click Setup.exe.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e587b-119">Express Edition не создает файл конфигурации автоматически.</span><span class="sxs-lookup"><span data-stu-id="e587b-119">Express Edition setup does not create a configuration file automatically.</span></span> <span data-ttu-id="e587b-120">Следующая команда запустит установку и создаст файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e587b-120">The following command will start  setup and create a configuration file.</span></span>  
    >   
    >  <span data-ttu-id="e587b-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span><span class="sxs-lookup"><span data-stu-id="e587b-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span></span>  
  
2.  <span data-ttu-id="e587b-122">Следуйте указаниям мастера до страницы **Все готово для установки** .</span><span class="sxs-lookup"><span data-stu-id="e587b-122">Follow the wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="e587b-123">Путь к файлу конфигурации указывается на странице **Все готово для установки** в разделе пути файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e587b-123">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span> <span data-ttu-id="e587b-124">Дополнительные сведения об установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [install SQL Server 2014 мастера установки &#40;&#41;установки ](install-sql-server-from-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="e587b-124">For more information about how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
3.  <span data-ttu-id="e587b-125">Отмените установку, не завершая ее, чтобы создать INI-файл.</span><span class="sxs-lookup"><span data-stu-id="e587b-125">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e587b-126">Инфраструктура программы установки запишет все соответствующие параметры для запущенных действий (за исключением конфиденциальных данных, например паролей).</span><span class="sxs-lookup"><span data-stu-id="e587b-126">The setup infrastructure writes out all the appropriate parameters for the actions that were run, with the exception of sensitive information such as passwords.</span></span> <span data-ttu-id="e587b-127">Параметр /IAcceptSQLServerLicenseTerms также не записывается в файл конфигурации и требует или изменения файла конфигурации, или указания значения в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e587b-127">The /IAcceptSQLServerLicenseTerms parameter is also not written out to the configuration file and requires either a modification of the configuration file or a value to be supplied at the command prompt.</span></span> <span data-ttu-id="e587b-128">Дополнительные сведения см. в статье [Установка SQL Server 2014 из командной строки](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="e587b-128">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="e587b-129">Также включается значение для логических параметров, для которых значения обычно не указываются через командную строку.</span><span class="sxs-lookup"><span data-stu-id="e587b-129">In addition, a value is included for Boolean parameters where a value is usually not supplied through the command prompt.</span></span>  
  
## <a name="using-the-configuration-file-to-install-ssnoversion"></a><span data-ttu-id="e587b-130">Использование файла конфигурации для установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e587b-130">Using the Configuration File to Install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="e587b-131">Файл конфигурации можно использовать только при установке из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e587b-131">You can only use the configuration file on command-line installations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e587b-132">Если необходимо изменить файл конфигурации, рекомендуется создать копию и работать с ней.</span><span class="sxs-lookup"><span data-stu-id="e587b-132">If you need to make changes to the configuration file, we recommend that you make a copy and work with the copy.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-install-a-stand-alone-ssnoversion-instance"></a><span data-ttu-id="e587b-133">Использование файла конфигурации для установки изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e587b-133">How to use a configuration file to install a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance</span></span>  
  
-   <span data-ttu-id="e587b-134">Запустите установку через командную строку и предоставьте файл ConfigurationFile.ini с помощью параметра *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="e587b-134">Run the installation through the command prompt and supply the ConfigurationFile.ini using the *ConfigurationFile* parameter.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-prepare-and-complete-an-image-of-a-stand-alone-ssnoversion-instance-sysprep"></a><span data-ttu-id="e587b-135">Использование файла конфигурации для подготовки и завершения создания образа изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SysPrep)</span><span class="sxs-lookup"><span data-stu-id="e587b-135">How to use a configuration file to prepare and complete an image of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (SysPrep)</span></span>  
  
1.  <span data-ttu-id="e587b-136">Подготовка одного или нескольких экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и настройка их на одном и том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="e587b-136">To prepare one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and configure them on the same machine.</span></span>  
  
    -   <span data-ttu-id="e587b-137">Запустите **Подготовка образа изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** на странице **Дополнительно** центра установки и сохраните файл конфигурации подготовки образа.</span><span class="sxs-lookup"><span data-stu-id="e587b-137">Run **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="e587b-138">Используйте тот же файл конфигурации подготовки образа как шаблон для подготовки дополнительных экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e587b-138">Use the same prepare image configuration file as a template to prepare more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="e587b-139">Запустите **Завершение образа подготовленного изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** со страницы **Дополнительно** центра установки для настройки подготовленных экземпляров на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="e587b-139">Run **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center to configure a prepared instances on the machine.</span></span>  
  
2.  <span data-ttu-id="e587b-140">Подготовка образа операционной системы, включая ненастроенный подготовленный экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], с помощью средства Windows SysPrep.</span><span class="sxs-lookup"><span data-stu-id="e587b-140">To prepare an image of the operating system including an unconfigured prepared instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], using Windows SysPrep tool.</span></span>  
  
    -   <span data-ttu-id="e587b-141">Запустите **Подготовка образа изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** со страницы "Дополнительно" центра установки и сохраните файл конфигурации подготовки образа.</span><span class="sxs-lookup"><span data-stu-id="e587b-141">Run the **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the Advanced page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="e587b-142">Запустите **Завершение образа подготовленного изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** со страницы **Дополнительно** центра установки, но отмените процесс на странице **Все готово к завершению образа** после сохранения готового файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e587b-142">Run the **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center, but cancel it on the **Ready to Complete** page after capturing the complete configuration file.</span></span>  
  
    -   <span data-ttu-id="e587b-143">Готовый файл конфигурации можно сохранить в образе Windows для автоматизации настройки подготовленных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e587b-143">The complete image configuration file can be stored with the Windows image for automating the configuration of the prepared instances.</span></span>  
  
#### <a name="how-to-install-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="e587b-144">Установка отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e587b-144">How to install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="e587b-145">Вариант интегрированной установки (создайте на узле отказоустойчивого кластера из одного узла, а для добавления дополнительных узлов выполните на них операцию AddNode):</span><span class="sxs-lookup"><span data-stu-id="e587b-145">Integrated Install option (create a single node failover cluster on a node and for additional nodes, run AddNode on them):</span></span>  
  
    -   <span data-ttu-id="e587b-146">Выберите параметр «Установить отказоустойчивый кластер» и сохраните файл конфигурации, в котором перечисляются все параметры установки.</span><span class="sxs-lookup"><span data-stu-id="e587b-146">Run the "Install a Failover Cluster" option and capture the configuration file that lists all the installation settings.</span></span>  
  
    -   <span data-ttu-id="e587b-147">Запустите установку отказоустойчивого кластера из командной строки, указав параметр *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="e587b-147">Run the command-line failover cluster install by supplying the *ConfigurationFile* parameter.</span></span>  
  
    -   <span data-ttu-id="e587b-148">На дополнительном добавляемом узле следует запустить действие добавления узла, чтобы сохранить файл ConfigurationFile.ini, применяемый к существующему отказоустойчивому кластеру.</span><span class="sxs-lookup"><span data-stu-id="e587b-148">On an additional node to be added, run AddNode to capture the ConfigurationFile.ini file applicable to the existing failover cluster.</span></span>  
  
    -   <span data-ttu-id="e587b-149">Запустите действие добавления узла через командную строку на всех дополнительных узлах, которые будут присоединены к отказоустойчивому кластеру, предоставив тот же файл конфигурации с помощью параметра ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="e587b-149">Run the command-line AddNode on all the additional nodes that will join the failover cluster, by supplying the same configuration file using the ConfigurationFile parameter.</span></span>  
  
2.  <span data-ttu-id="e587b-150">Параметр расширенной установки (подготовка отказоустойчивого кластера на всех узлах отказоустойчивого кластера, затем после подготовки всех узлов — завершение создания кластера на узле, которому принадлежит общий диск).</span><span class="sxs-lookup"><span data-stu-id="e587b-150">Advanced install option (prepare failover cluster on all failover cluster nodes, then, after preparing all the nodes, run complete on the node that owns the shared disk):</span></span>  
  
    -   <span data-ttu-id="e587b-151">Запустите действие **Подготовка** на одном из узлов и сохраните файл ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="e587b-151">Run **Prepare** on one of the nodes, and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="e587b-152">Предоставьте тот же файл ConfigurationFile.ini на всех узлах, которые будут подготовлены для отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="e587b-152">Supply the same ConfigurationFile.ini file to Setup on all the nodes that will be prepared for the failover cluster.</span></span>  
  
    -   <span data-ttu-id="e587b-153">После подготовки всех узлов выполните операцию завершения создания отказоустойчивого кластера на узле, которому принадлежит общий диск, и сохраните файл ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="e587b-153">After all the nodes have been prepared, run a complete failover cluster operation on the node that owns the shared disk and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="e587b-154">После этого можно предоставить данный файл ConfigurationFile.ini, чтобы завершить создание отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="e587b-154">You can then supply this ConfigurationFile.ini file to complete the failover cluster.</span></span>  
  
#### <a name="how-to-add-or-remove-a-node-to-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="e587b-155">Добавление или удаление узла из отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e587b-155">How to add or remove a node to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
-   <span data-ttu-id="e587b-156">Если существует файл конфигурации, который ранее использовался для добавления или удаления узла из отказоустойчивого кластера, его можно повторно использовать для добавления или удаления дополнительных узлов.</span><span class="sxs-lookup"><span data-stu-id="e587b-156">If you have a configuration file that was previously used to add a node to or remove a node from a failover cluster, you can reuse that same file to add or remove additional nodes.</span></span>  
  
#### <a name="how-to-upgrade-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="e587b-157">Обновление отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e587b-157">How to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="e587b-158">Выполните обновление на пассивном узле и сохраните файл ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="e587b-158">Run upgrade on the passive node and capture the ConfigurationFile.ini file.</span></span> <span data-ttu-id="e587b-159">Это можно сделать, не только выполнив реальное обновление, но и отменив его в конце (не выполняя реальное обновление).</span><span class="sxs-lookup"><span data-stu-id="e587b-159">You can do this either by performing the actual upgrade, or exiting at the end without doing the actual upgrade.</span></span>  
  
2.  <span data-ttu-id="e587b-160">Файл ConfigurationFile.ini необходимо предоставить на дополнительных обновляемых узлах, чтобы завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="e587b-160">On all the additional nodes to be upgraded, supply the ConfigurationFile.ini file to complete the process.</span></span>  
  
## <a name="sample-syntax"></a><span data-ttu-id="e587b-161">Образец синтаксиса</span><span class="sxs-lookup"><span data-stu-id="e587b-161">Sample Syntax</span></span>  
 <span data-ttu-id="e587b-162">Ниже приведено несколько примеров использования файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e587b-162">Following are some examples on how to use the configuration file:</span></span>  
  
-   <span data-ttu-id="e587b-163">Указание файла конфигурации в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e587b-163">To specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /ConfigurationFile=MyConfigurationFile.INI  
```  
  
-   <span data-ttu-id="e587b-164">Указание паролей в командной строке, а не в файле конфигурации:</span><span class="sxs-lookup"><span data-stu-id="e587b-164">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
```  
Setup.exe /SQLSVCPASSWORD="************" /AGTSVCPASSWORD="************" /ASSVCPASSWORD="************" /ISSVCPASSWORD="************" /RSSVCPASSWORD="************" /ConfigurationFile=MyConfigurationFile.INI  
```  
  
## <a name="see-also"></a><span data-ttu-id="e587b-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="e587b-165">See Also</span></span>  
 <span data-ttu-id="e587b-166">[Установка SQL Server 2014 из командной строки](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="e587b-166">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="e587b-167">[Установка отказоустойчивого кластера SQL Server](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span><span class="sxs-lookup"><span data-stu-id="e587b-167">[SQL Server Failover Cluster Installation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span></span>  
 [<span data-ttu-id="e587b-168">Обновление отказоустойчивого кластера SQL Server</span><span class="sxs-lookup"><span data-stu-id="e587b-168">Upgrade a SQL Server Failover Cluster</span></span>](../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
