---
title: Задача 4. Создание проекта служб SSIS с помощью SQL Server Data Tools | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733342"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a><span data-ttu-id="df0a8-102">Задача 4. Создание проекта SSIS с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="df0a8-102">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>
  <span data-ttu-id="df0a8-103">В этой задаче вы создадите проект служб SSIS с помощью **SQL Server Data Tools** для автоматизации очистки и сопоставления данных поставщика.</span><span class="sxs-lookup"><span data-stu-id="df0a8-103">In this task, you create an SSIS project by using **SQL Server Data Tools** to automate cleansing and matching supplier data.</span></span>

1.  <span data-ttu-id="df0a8-104">Запустите **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-104">Launch **SQL Server Data Tools**.</span></span> <span data-ttu-id="df0a8-105">Нажмите кнопку Пуск, укажите **все программы**, разверните **Microsoft SQL Server 2012**и щелкните **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-105">Click Start, point to **All Programs**, expand **Microsoft SQL Server 2012**, and click **SQL Server Data Tools**.</span></span>

2.  <span data-ttu-id="df0a8-106">В меню **Файл** укажите пункт **Создать**, затем выберите пункт **Проект**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-106">On the **File** menu, point to **New**, and click **Project**.</span></span>

3.  <span data-ttu-id="df0a8-107">Разверните узел **Бизнес-аналитика** в области **Установленные шаблоны** и выберите **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-107">Expand **Business Intelligence** in the **Installed Templates** pane, and select **Integration Services**.</span></span>

     <span data-ttu-id="df0a8-108">![Visual Studio — диалоговое окно «Создание проекта»](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio — диалоговое окно «Создание проекта»")</span><span class="sxs-lookup"><span data-stu-id="df0a8-108">![Visual Studio - New Project Dialog Box](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - New Project Dialog Box")</span></span>

4.  <span data-ttu-id="df0a8-109">Выберите **Integration Services проект** в **списке типов проектов**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-109">Select **Integration Services Project** in the **list of project types**.</span></span>

5.  <span data-ttu-id="df0a8-110">Введите **CleanseAndCurateSuppliers** в качестве **имени** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-110">Type **CleanseAndCurateSuppliers** for **Name** and click **OK**.</span></span>

6.  <span data-ttu-id="df0a8-111">В **Обозреватель решений** окне щелкните правой кнопкой мыши **Package. dtsx** и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-111">In **Solution Explorer** window, right-click **Package.dtsx** and select **Rename**.</span></span> <span data-ttu-id="df0a8-112">Если окно **Обозреватель решений** не отображается, нажмите кнопку **Просмотр** в строке меню и выберите пункт **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-112">If you don't see **Solution Explorer** window, click **View** on the menu bar and click **Solution Explorer**.</span></span>

     <span data-ttu-id="df0a8-113">![Package.dtsx — меню переименования](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx — меню переименования")</span><span class="sxs-lookup"><span data-stu-id="df0a8-113">![Package.dtsx - Rename Menu](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Rename Menu")</span></span>

7.  <span data-ttu-id="df0a8-114">Введите **CleanseAndCurate. dtsx** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-114">Type **CleanseAndCurate.dtsx** and press **ENTER**.</span></span> <span data-ttu-id="df0a8-115">Убедитесь, что **расширение** остается в виде **dtsx**.</span><span class="sxs-lookup"><span data-stu-id="df0a8-115">Make sure that the **extension** remains **.dtsx**.</span></span>

## <a name="next-step"></a><span data-ttu-id="df0a8-116">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="df0a8-116">Next Step</span></span>
 [<span data-ttu-id="df0a8-117">Задача 5. Добавление задачи потока данных</span><span class="sxs-lookup"><span data-stu-id="df0a8-117">Task 5: Adding Data Flow Task</span></span>](task-5-adding-data-flow-task.md)


