---
title: Импорт проекта Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3301c328-b0f5-4517-915c-93713413e453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a98219f3a04d11e086957d64a62e7c64cd51418
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655845"
---
# <a name="import-an-integration-services-project"></a><span data-ttu-id="5b864-102">Импорт проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="5b864-102">Import an Integration Services Project</span></span>
  <span data-ttu-id="5b864-103">Для создания проекта из существующего файла развертывания (ISPAC) или из проекта, развернутого в каталоге служб Integration Services, используется **Мастер импорта проекта** служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b864-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]**Import Project Wizard** to create a project from an existing deployment file (.ispac) or from a project deployed to Integration services catalog.</span></span> <span data-ttu-id="5b864-104">Эта функция особенно полезна в случаях, когда отсутствует исходная копия проекта, но необходимо создать ее из файла с расширением ISPAC или каталога SSISDB.</span><span class="sxs-lookup"><span data-stu-id="5b864-104">This feature is especially useful when you do not have the original copy of the project but you want to create one from an .ispac file or SSISDB catalog.</span></span>  
  
### <a name="to-import-a-project"></a><span data-ttu-id="5b864-105">Импорт проекта</span><span class="sxs-lookup"><span data-stu-id="5b864-105">To Import a Project</span></span>  
  
1.  <span data-ttu-id="5b864-106">В выберите [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] пункт **создать**  >  **проект** в меню **файл** .</span><span class="sxs-lookup"><span data-stu-id="5b864-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New** > **Project** on the **File** menu.</span></span>  
  
2.  <span data-ttu-id="5b864-107">В области **Установленные шаблоны** в окне **Создание проекта** разверните пункт **Бизнес-аналитика**и выберите **Службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="5b864-107">In the **Installed Templates** area of the **New Project** window, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="5b864-108">Из списка типов проекта выберите **Мастер импорта проекта служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="5b864-108">Select **Integration Services Import Project Wizard** from the project types list.</span></span>  
  
4.  <span data-ttu-id="5b864-109">В текстовом поле **Имя** введите имя создаваемого проекта.</span><span class="sxs-lookup"><span data-stu-id="5b864-109">Type a name for the new project to be created in the **Name** text box.</span></span>  
  
5.  <span data-ttu-id="5b864-110">В текстовое поле **Расположение** введите путь или расположение проекта или нажмите кнопку **Обзор** , чтобы найти нужную папку.</span><span class="sxs-lookup"><span data-stu-id="5b864-110">Type the path or location for the project in the **Location** text box, or click **Browse** to select one.</span></span>  
  
6.  <span data-ttu-id="5b864-111">В текстовом поле **Имя решения** введите имя решения.</span><span class="sxs-lookup"><span data-stu-id="5b864-111">Type a name for the solution in the **Solution name** text box.</span></span>  
  
7.  <span data-ttu-id="5b864-112">Нажмите кнопку **OK** , чтобы открыть диалоговое окно **Мастер импорта проекта служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="5b864-112">Click **OK** to launch the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
8.  <span data-ttu-id="5b864-113">Нажмите кнопку **Далее** , чтобы перейти на страницу **Выбор источника данных** .</span><span class="sxs-lookup"><span data-stu-id="5b864-113">Click **Next** to switch to the **Select Source** page.</span></span>  
  
9. <span data-ttu-id="5b864-114">При импортировании из файла с расширением **ISPAC** введите путь в текстовое поле **Путь** , включая имя файла.</span><span class="sxs-lookup"><span data-stu-id="5b864-114">If you are importing from an **.ispac** file, type the path including file name in the **Path** text box.</span></span> <span data-ttu-id="5b864-115">Нажмите кнопку **Обзор** , чтобы перейти к папке, где необходимо сохранить решение, введите имя файла в текстовое поле **Имя файла** и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="5b864-115">Click **Browse** to navigate to the folder where you want the solution to be stored and type file name in the **File name** text box, and click **Open**.</span></span>  
  
     <span data-ttu-id="5b864-116">При импортировании из **Каталога служб Integration Services**введите имя экземпляра базы данных в текстовое поле **Имя сервера** или нажмите кнопку **Обзор** и выберите экземпляр базы данных, в котором содержится каталог.</span><span class="sxs-lookup"><span data-stu-id="5b864-116">If you are importing from an **Integration Services Catalog**, type the database instance name in the **Server name** text box or click **Browse** and select the database instance that contains the catalog.</span></span>  
  
     <span data-ttu-id="5b864-117">Нажмите кнопку **Обзор** , которая находится рядом с текстовым полем **Путь** , раскройте папку в каталоге, выберите проект, который необходимо импортировать и нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b864-117">Click **Browse** next to **Path** text box, expand folder in the catalog, select the project you want to import, and click **OK**.</span></span>  
  
     <span data-ttu-id="5b864-118">Чтобы перейти к странице **Просмотр** , нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="5b864-118">Click **Next** to switch to the **Review** page.</span></span>  
  
10. <span data-ttu-id="5b864-119">Изучите имеющиеся сведения и нажмите кнопку **Импорт** для создания проекта на основе существующего выбранного проекта.</span><span class="sxs-lookup"><span data-stu-id="5b864-119">Review the information and click **Import** to create a project based on the existing project you selected.</span></span>  
  
11. <span data-ttu-id="5b864-120">Необязательно. Нажмите кнопку **Сохранить отчет** , чтобы сохранить результаты в файл.</span><span class="sxs-lookup"><span data-stu-id="5b864-120">Optional: click **Save Report** to save the results to a file</span></span>  
  
12. <span data-ttu-id="5b864-121">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Мастер импорта проекта служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="5b864-121">Click **Close** to close the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
  
