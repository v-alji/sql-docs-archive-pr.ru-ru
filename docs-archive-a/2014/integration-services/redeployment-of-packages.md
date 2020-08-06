---
title: Повторное развертывание пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- redeploying packages [Integration Services]
- deploying packages [Integration Services], redeploying
ms.assetid: 86806efb-8cf4-4f9d-9824-1152cb4c495c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c5286d406d96f62fc74eb619f7e7a6064fde2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729590"
---
# <a name="redeployment-of-packages"></a><span data-ttu-id="c9f4a-102">Повторное развертывание пакетов</span><span class="sxs-lookup"><span data-stu-id="c9f4a-102">Redeployment of Packages</span></span>
  <span data-ttu-id="c9f4a-103">После развертывания проекта может понадобится обновить или расширить функциональные возможности пакета и затем повторно развернуть проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-103">After a project is deployed, you may need to update or extend package functionality and then redeploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the updated packages.</span></span> <span data-ttu-id="c9f4a-104">В рамках процесса повторного развертывания пакетов необходимо просмотреть свойства конфигурации, включенные в программу развертывания.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-104">As part of the process of redeploying packages, you should review the configuration properties that are included in the deployment utility.</span></span> <span data-ttu-id="c9f4a-105">Например, можно запретить изменение конфигурации после повторного развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-105">For example, you may not want to allow configuration changes after the package is redeployed.</span></span>  
  
## <a name="process-for-redeployment"></a><span data-ttu-id="c9f4a-106">Процесс повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="c9f4a-106">Process for Redeployment</span></span>  
 <span data-ttu-id="c9f4a-107">После завершения обновления пакетов перестраивается проект, папка развертывания копируется на целевой компьютер и затем повторно запускается мастер установки пакета.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-107">After you finish updating the packages, you rebuild the project, copy the deployment folder to the target computer, and then rerun the Package Installation Wizard.</span></span>  
  
 <span data-ttu-id="c9f4a-108">При обновлении нескольких пакетов в проекте развертывание всего пакета может не понадобиться.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-108">If you update only a few packages in the project, you may not want to redeploy the entire project.</span></span> <span data-ttu-id="c9f4a-109">Для развертывания только нескольких пакетов можно создать новый проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , добавить обновленные пакеты в новый проект, затем скомпоновать и развернуть проект.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-109">To deploy only a few packages, you can create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add the updated packages to the new project, and then build and deploy the project.</span></span> <span data-ttu-id="c9f4a-110">Конфигурации пакетов автоматически копируются с пакетом при добавлении пакета в другой проект.</span><span class="sxs-lookup"><span data-stu-id="c9f4a-110">Package configurations are automatically copied with the package when you add the package to a different project.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c9f4a-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c9f4a-111">Related Tasks</span></span>  
 [<span data-ttu-id="c9f4a-112">Развертывание пакетов с помощью программы развертывания</span><span class="sxs-lookup"><span data-stu-id="c9f4a-112">Deploy Packages by Using the Deployment Utility</span></span>](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md)  
  
  
