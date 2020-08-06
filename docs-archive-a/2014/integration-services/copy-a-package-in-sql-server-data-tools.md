---
title: Копирование пакета с помощью SQL Server Data Tools | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], copying
- copying packages
- regenerating package GUID
- updating package properties
ms.assetid: 03edc659-e76d-48c0-a749-5f1899b6b507
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bd6ed4dd66ee4755181f5df6f3c1b5466b3f26b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665056"
---
# <a name="copy-a-package-in-sql-server-data-tools"></a><span data-ttu-id="8ce0e-102">Копирование пакета с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="8ce0e-102">Copy a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="8ce0e-103">В этом разделе описывается, как создать новый пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] копированием существующего пакета и как обновить свойства `Name` и `GUID` нового пакета.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-103">This topic describes how to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package by copying an existing package, and how to update the `Name` and `GUID` properties of the new package.</span></span>  
  
### <a name="to-copy-a-package"></a><span data-ttu-id="8ce0e-104">Копирование пакета</span><span class="sxs-lookup"><span data-stu-id="8ce0e-104">To copy a package</span></span>  
  
1.  <span data-ttu-id="8ce0e-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет, который нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to copy.</span></span>  
  
2.  <span data-ttu-id="8ce0e-106">Дважды щелкните пакет в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-106">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="8ce0e-107">Убедитесь, что копируемый пакет выбран в обозревателе решений либо в конструкторе служб SSIS выбрана вкладка, содержащая пакет</span><span class="sxs-lookup"><span data-stu-id="8ce0e-107">Verify either the package to copy is selected in Solution Explorer or the tab in SSIS Designer that contains the package is the active tab</span></span>  
  
4.  <span data-ttu-id="8ce0e-108">В меню **Файл** выберите команду **Сохранить \<package name> как**.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-108">On the **File** menu, click **Save \<package name> As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ce0e-109">Чтобы команда **Сохранить как** появилась в меню **Файл** , пакет нужно открыть в конструкторе служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-109">The package must be opened in SSIS Designer before the **Save As** option appears on the **File** menu.</span></span>  
  
5.  <span data-ttu-id="8ce0e-110">При необходимости перейдите в другую папку.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-110">Optionally, browse to a different folder.</span></span>  
  
6.  <span data-ttu-id="8ce0e-111">Обновите имя файла пакета.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-111">Update the name of the package file.</span></span> <span data-ttu-id="8ce0e-112">Убедитесь, что файл сохраняется с расширением DTSX.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-112">Make sure that you retain the .dtsx file extension.</span></span>  
  
7.  <span data-ttu-id="8ce0e-113">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-113">Click **Save**.</span></span>  
  
8.  <span data-ttu-id="8ce0e-114">Выберите, обновлять ли имя объекта пакета, чтобы оно соответствовало имени файла.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-114">At the prompt, choose whether to update the name of the package object to match the file name.</span></span> <span data-ttu-id="8ce0e-115">Если нажать кнопку **Да**, `Name` свойство пакета будет обновлено.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-115">If you click **Yes**, the `Name` property of the package is updated.</span></span> <span data-ttu-id="8ce0e-116">Новый пакет будет добавлен к проекту служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и открыт в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ce0e-116">The new package is added to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
9. <span data-ttu-id="8ce0e-117">При необходимости перейдите на вкладку **Поток управления** и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-117">Optionally, click in the background of the **Control Flow** tab, and the click **Properties**.</span></span>  
  
10. <span data-ttu-id="8ce0e-118">В окне "Свойства" щелкните значение свойства идентификатора (ID), а затем выберите в раскрывающемся списке **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="8ce0e-118">In the Properties window, click the value of the ID property, and then in the drop-down list click **\<Generate New ID>**.</span></span>  
  
11. <span data-ttu-id="8ce0e-119">В меню **Файл** выберите команду **Сохранить выбранные элементы** , чтобы сохранить новый пакет.</span><span class="sxs-lookup"><span data-stu-id="8ce0e-119">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce0e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ce0e-120">See Also</span></span>  
 <span data-ttu-id="8ce0e-121">[Сохранение одной копии пакета](../../2014/integration-services/save-a-copy-of-a-package.md) </span><span class="sxs-lookup"><span data-stu-id="8ce0e-121">[Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md) </span></span>  
 <span data-ttu-id="8ce0e-122">[Создание пакетов в SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8ce0e-122">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="8ce0e-123">Пакеты служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="8ce0e-123">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
