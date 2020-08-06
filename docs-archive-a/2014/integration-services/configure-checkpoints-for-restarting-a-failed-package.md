---
title: Настройка контрольных точек для перезапуска непройденного пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736662"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a><span data-ttu-id="6712e-102">Настройка контрольных точек для повторного запуска пакета, завершившегося с ошибкой</span><span class="sxs-lookup"><span data-stu-id="6712e-102">Configure Checkpoints for Restarting a Failed Package</span></span>
  <span data-ttu-id="6712e-103">Устанавливая свойства, влияющие на контрольные точки, можно настроить пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] таким образом, чтобы они перезапускались с точки сбоя вместо выполнения всего пакета с начала.</span><span class="sxs-lookup"><span data-stu-id="6712e-103">You configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to restart from a point of failure, instead of rerunning the entire package, by setting the properties that apply to checkpoints.</span></span>  
  
### <a name="to-configure-a-package-to-restart"></a><span data-ttu-id="6712e-104">Настройка пакета для перезапуска</span><span class="sxs-lookup"><span data-stu-id="6712e-104">To configure a package to restart</span></span>  
  
1.  <span data-ttu-id="6712e-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет, который нужно настроить.</span><span class="sxs-lookup"><span data-stu-id="6712e-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure.</span></span>  
  
2.  <span data-ttu-id="6712e-106">Чтобы открыть пакет, дважды щелкните его в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="6712e-106">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6712e-107">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="6712e-107">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="6712e-108">Щелкните правой кнопкой мыши в области конструктора потока управления и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6712e-108">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="6712e-109">Задайте для свойства SaveCheckpoints значение `True` .</span><span class="sxs-lookup"><span data-stu-id="6712e-109">Set the SaveCheckpoints property to `True`.</span></span>  
  
6.  <span data-ttu-id="6712e-110">Введите имя файла контрольных точек в поле свойства CheckpointFileName.</span><span class="sxs-lookup"><span data-stu-id="6712e-110">Type the name of the checkpoint file in the CheckpointFileName property.</span></span>  
  
7.  <span data-ttu-id="6712e-111">Установите значение свойства CheckpointUsage в одно из двух значений:</span><span class="sxs-lookup"><span data-stu-id="6712e-111">Set the CheckpointUsage property to one of two values:</span></span>  
  
    -   <span data-ttu-id="6712e-112">Установите `Always`, чтобы всегда перезапускать пакет с контрольной точки.</span><span class="sxs-lookup"><span data-stu-id="6712e-112">Select `Always` to always restart the package from the checkpoint.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6712e-113">Если файл контрольных точек недоступен, то возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="6712e-113">An error occurs if the checkpoint file is not available.</span></span>  
  
    -   <span data-ttu-id="6712e-114">Выберете свойство `IfExists`, чтобы перезапускать пакет, только если доступен файл контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="6712e-114">Select `IfExists` to restart the package only if the checkpoint file is available.</span></span>  
  
8.  <span data-ttu-id="6712e-115">Настройте задачи и контейнеры, из которых пакет может быть перезапущен.</span><span class="sxs-lookup"><span data-stu-id="6712e-115">Configure the tasks and containers from which the package can restart.</span></span>  
  
    -   <span data-ttu-id="6712e-116">Правой кнопкой мыши щелкните задание или контейнер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6712e-116">Right-click a task or container and click **Properties**.</span></span>  
  
    -   <span data-ttu-id="6712e-117">Задайте для свойства FailPackageOnFailure значение `True` для каждой выбранной задачи и контейнера.</span><span class="sxs-lookup"><span data-stu-id="6712e-117">Set the FailPackageOnFailure property to `True` for each selected task and container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6712e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="6712e-118">See Also</span></span>  
 [<span data-ttu-id="6712e-119">Перезапуск пакетов с помощью контрольных точек</span><span class="sxs-lookup"><span data-stu-id="6712e-119">Restart Packages by Using Checkpoints</span></span>](packages/restart-packages-by-using-checkpoints.md)  
  
  
