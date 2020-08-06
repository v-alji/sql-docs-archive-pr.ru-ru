---
title: Указание целевого объекта установки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- installation targets [Analysis Services]
- Analysis Services deployments, installation targets
- Analysis Services Deployment Wizard, installation targets
- deploying [Analysis Services], installation targets
- modifying installation targets
ms.assetid: cb706817-6f63-4771-92c3-b70030bbce3d
author: minewiskan
ms.author: owend
ms.openlocfilehash: e830fc353898e3ec835b338e84765a0cad0de43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665156"
---
# <a name="specifying-the-installation-target"></a><span data-ttu-id="ff716-102">Указание целевого объекта установки</span><span class="sxs-lookup"><span data-stu-id="ff716-102">Specifying the Installation Target</span></span>
  <span data-ttu-id="ff716-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]Мастер развертывания считывает сведения о целевом объекте установки из \<*project name*> файла deploymenttargets.</span><span class="sxs-lookup"><span data-stu-id="ff716-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="ff716-104">создает этот файл при сборке [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="ff716-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="ff716-105">использует базу данных и сервер, указанные на странице **развертывание** *\<project name>* диалогового окна **страницы свойств** , для создания \<*project name*> файла TARGETS.</span><span class="sxs-lookup"><span data-stu-id="ff716-105">uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.</span></span>  
  
## <a name="modifying-the-installation-target-for-deployment"></a><span data-ttu-id="ff716-106">Измерение целевого объекта установки для развертывания</span><span class="sxs-lookup"><span data-stu-id="ff716-106">Modifying the Installation Target for Deployment</span></span>  
 <span data-ttu-id="ff716-107">В некоторых ситуациях может быть необходимо развернуть проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в базу данных или экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , отличающийся от указанного на странице **Развертывание** .</span><span class="sxs-lookup"><span data-stu-id="ff716-107">In some situations, you may need to deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that is different than the one specified on the **Deployment** page.</span></span> <span data-ttu-id="ff716-108">Например может быть необходимо развернуть проект на сервер для тестирования перед развертыванием, а затем развернуть его на производственный сервер после окончания тестирования.</span><span class="sxs-lookup"><span data-stu-id="ff716-108">For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished.</span></span> <span data-ttu-id="ff716-109">Может также быть необходимо развернуть завершенный и протестированный проект на несколько производственных серверов в кластере балансирования сетевой нагрузки, или на промежуточный сервер и производственный сервер.</span><span class="sxs-lookup"><span data-stu-id="ff716-109">You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.</span></span>  
  
 <span data-ttu-id="ff716-110">Чтобы развернуть проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в другую базу данных или экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , можно изменить целевой объект установки во входном файле, используя один из методов, описанный в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="ff716-110">To deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a different database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you can change the installation target in the input file by using one of the methods described in the following procedure.</span></span>  
  
#### <a name="to-change-the-installation-target-after-the-input-files-have-been-generated"></a><span data-ttu-id="ff716-111">Изменение целевого объекта установки после формирования входных файлов</span><span class="sxs-lookup"><span data-stu-id="ff716-111">To change the installation target after the input files have been generated</span></span>  
  
-   <span data-ttu-id="ff716-112">Запустите мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="ff716-112">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="ff716-113">На странице **Целевой объект установки** укажите новое место назначения для экземпляра и базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff716-113">On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database.</span></span>  
  
     <span data-ttu-id="ff716-114">-или-</span><span class="sxs-lookup"><span data-stu-id="ff716-114">-or-</span></span>  
  
-   <span data-ttu-id="ff716-115">Запустите мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] из командной строки и настройте его на работу в режиме файла ответов.</span><span class="sxs-lookup"><span data-stu-id="ff716-115">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="ff716-116">Дополнительные сведения о режиме файла ответов см. в разделе [Запуск мастера развертывания служб Analysis Services](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ff716-116">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="ff716-117">-или-</span><span class="sxs-lookup"><span data-stu-id="ff716-117">-or-</span></span>  
  
-   <span data-ttu-id="ff716-118">Измените \<*project name*> файл deploymenttargets с помощью любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="ff716-118">Modify the \<*project name*>.deploymenttargets file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff716-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff716-119">See Also</span></span>  
 <span data-ttu-id="ff716-120">[Указание параметров развертывания секций и ролей](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="ff716-120">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 <span data-ttu-id="ff716-121">[Указание параметров конфигурации для развертывания решения](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ff716-121">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="ff716-122">Указание параметров обработки</span><span class="sxs-lookup"><span data-stu-id="ff716-122">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
