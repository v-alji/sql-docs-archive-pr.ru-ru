---
title: Диалоговое окно «преобразовать в модель развертывания пакета» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.bids.converttolegacydeployment.f1
ms.assetid: 9e60a34a-10f7-48d1-966f-b3ff236ab4b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b52932ad26f8cebd2e67b0025f4b881241119f6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665058"
---
# <a name="convert-to-package-deployment-model-dialog-box"></a><span data-ttu-id="e28d7-102">Преобразовать в модель диалоговое окно "пакет развертывания"</span><span class="sxs-lookup"><span data-stu-id="e28d7-102">Convert to Package Deployment Model Dialog Box</span></span>
  <span data-ttu-id="e28d7-103">С помощью команды **Преобразовать в модель развертывания пакетов** можно выполнить преобразование пакета в модель развертывания пакетов после проверки проекта и каждого пакета в проекте на совместимость с данной моделью.</span><span class="sxs-lookup"><span data-stu-id="e28d7-103">The **Convert to Package Deployment Model** command allows you to convert a package to the package deployment model after checking the project and each package in the project for compatibility with that model.</span></span> <span data-ttu-id="e28d7-104">Если пакет использует специальные функции в модели развертывания проекта, такие как параметры, то пакет невозможно преобразовать.</span><span class="sxs-lookup"><span data-stu-id="e28d7-104">If a package uses features unique to the project deployment model, such as parameters, then the package cannot be converted.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="e28d7-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="e28d7-105">Task List</span></span>  
 <span data-ttu-id="e28d7-106">Преобразование пакета в модель развертывания пакетов выполняется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="e28d7-106">Converting a package to the package deployment model requires two steps.</span></span>  
  
1.  <span data-ttu-id="e28d7-107">При выборе команды **Преобразовать в модель развертывания пакетов** из меню **Проект** выполняется проверка проекта и каждого пакета на совместимость с этой моделью.</span><span class="sxs-lookup"><span data-stu-id="e28d7-107">When you select the **Convert to Package Deployment Model** command from the **Project** menu, the project and each package are checked for compatibility with this model.</span></span> <span data-ttu-id="e28d7-108">Результаты отображаются в таблице **Результаты** .</span><span class="sxs-lookup"><span data-stu-id="e28d7-108">The results are displayed in the **Results** table.</span></span>  
  
     <span data-ttu-id="e28d7-109">Если проект или пакеты не прошли проверку на совместимость, щелкните **Ошибка** в столбце **Результат** для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="e28d7-109">If the project or a package fails the compatibility test, click **Failed** in the **Result** column for more information.</span></span> <span data-ttu-id="e28d7-110">Нажмите кнопку **Сохранить отчет** для сохранения копии этих сведений в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e28d7-110">Click **Save Report** to save a copy of this information to a text file.</span></span>  
  
2.  <span data-ttu-id="e28d7-111">Если проект и все пакеты прошли испытание на совместимость, нажмите кнопку **ОК** для преобразования пакета.</span><span class="sxs-lookup"><span data-stu-id="e28d7-111">If the project and all packages pass the compatibility test, then click **OK** to convert the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e28d7-112">Для преобразования проекта в модель развертывания проектов воспользуйтесь **Мастером преобразования проекта служб Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="e28d7-112">To convert a project to the project deployment model, use the **Integration Services Project Conversion Wizard**.</span></span> <span data-ttu-id="e28d7-113">Дополнительные сведения см. в статье [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e28d7-113">For more information, see [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28d7-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="e28d7-114">See Also</span></span>  
 <span data-ttu-id="e28d7-115">[Развертывание проектов и пакетов](packages/deploy-integration-services-ssis-projects-and-packages.md) </span><span class="sxs-lookup"><span data-stu-id="e28d7-115">[Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span></span>  
 <span data-ttu-id="e28d7-116">[Развертывание пакетов &#40;&#41;SSIS](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="e28d7-116">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="e28d7-117">Мастером преобразования проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e28d7-117">Integration Services Project Conversion Wizard</span></span>](../../2014/integration-services/integration-services-project-conversion-wizard.md)  
  
  
