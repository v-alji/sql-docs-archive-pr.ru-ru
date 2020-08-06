---
title: Диалоговое окно "Задание значения параметра" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ce9c2201-4e9a-4495-948f-b68deeaa7955
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 637267603c66921a566ca0d2a3f49f6142cfd203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736668"
---
# <a name="set-parameter-value-dialog-box"></a><span data-ttu-id="6e8d0-102">Диалоговое окно «Задание значения параметра»</span><span class="sxs-lookup"><span data-stu-id="6e8d0-102">Set Parameter Value Dialog Box</span></span>
  <span data-ttu-id="6e8d0-103">Диалоговое окно **Задание значения параметра** используется для настройки параметров и свойств диспетчеров соединений для пакетов и проектов.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-103">Use the **Set Parameter Value** dialog box to set values for parameters and connection manager properties, for projects and packages.</span></span>  
  
 <span data-ttu-id="6e8d0-104">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="6e8d0-105">Открыть диалоговое окно «Задание значения параметра»</span><span class="sxs-lookup"><span data-stu-id="6e8d0-105">Open the Set Parameter Value dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="6e8d0-106">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="6e8d0-106">Configure the options</span></span>](#option)  
  
##  <a name="open-the-set-parameter-value-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="6e8d0-107">Открыть диалоговое окно «Задание значения параметра»</span><span class="sxs-lookup"><span data-stu-id="6e8d0-107">Open the Set Parameter Value dialog box</span></span>  
  
1.  <span data-ttu-id="6e8d0-108">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e8d0-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="6e8d0-109">Устанавливается соединение с экземпляром [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], в котором размещена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="6e8d0-110">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="6e8d0-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="6e8d0-111">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="6e8d0-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="6e8d0-112">Щелкните правой кнопкой мыши пакет, выберите **Настроить**, а затем нажмите кнопку с многоточием на вкладке **Параметры** или **Диспетчеры соединений** .</span><span class="sxs-lookup"><span data-stu-id="6e8d0-112">Right-click a package or project, click **Configure**, and then click the ellipsis button in the **Parameters** tab or in the **Connection Managers** tab.</span></span>  
  
##  <a name="configure-the-options"></a><a name="option"></a> <span data-ttu-id="6e8d0-113">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="6e8d0-113">Configure the options</span></span>  
 <span data-ttu-id="6e8d0-114">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-114">**Parameter**</span></span>  
 <span data-ttu-id="6e8d0-115">Выводит список имен параметра.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-115">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="6e8d0-116">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-116">**Type**</span></span>  
 <span data-ttu-id="6e8d0-117">Перечисляет тип данных значения параметра.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-117">Lists the data type of the parameter value.</span></span>  
  
 <span data-ttu-id="6e8d0-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-118">**Description**</span></span>  
 <span data-ttu-id="6e8d0-119">Показывает дополнительное описание параметра.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-119">Shows an optional description for the parameter.</span></span>  
  
 <span data-ttu-id="6e8d0-120">**Изменить значение**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-120">**Edit value**</span></span>  
 <span data-ttu-id="6e8d0-121">Выберите этот параметр, чтобы изменить значение параметра.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-121">Select this option to edit the parameter value.</span></span>  
  
 <span data-ttu-id="6e8d0-122">**Использовать значение по умолчанию из пакета**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-122">**Use default value from package**</span></span>  
 <span data-ttu-id="6e8d0-123">Выберите этот параметр, чтобы использовать значение параметра по умолчанию, сохраненное в пакете.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-123">Select this option to use the default parameter value stored in the package.</span></span>  
  
 <span data-ttu-id="6e8d0-124">**Использовать переменную среды**</span><span class="sxs-lookup"><span data-stu-id="6e8d0-124">**Use environment variable**</span></span>  
 <span data-ttu-id="6e8d0-125">Выберите этот параметр для использования значения переменной, сохраненного в среде, на которую ссылается проект или пакет.</span><span class="sxs-lookup"><span data-stu-id="6e8d0-125">Select this option to use a variable value stored in the environment, which is referenced by the project or package.</span></span> <span data-ttu-id="6e8d0-126">Чтобы добавить ссылку среды к проекту или пакету, используйте диалоговое окно **Настройка** .</span><span class="sxs-lookup"><span data-stu-id="6e8d0-126">To add an environment reference to a project or package, use the **Configure** dialog box.</span></span> <span data-ttu-id="6e8d0-127">Дополнительные сведения см. в статье [Configure Dialog Box](configure-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="6e8d0-127">For more information, see [Configure Dialog Box](configure-dialog-box.md).</span></span>  
  
  
