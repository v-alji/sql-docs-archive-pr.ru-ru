---
title: Задача 1. Создание модели поставщиков с помощью диспетчер основных данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6bbbcbff-1ecd-456c-947f-c445c8da673c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f6823c96acb7db77a3daafa895f3353b70af44dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731230"
---
# <a name="task-1-creating-suppliers-model-using-master-data-manager"></a><span data-ttu-id="76891-102">Задача 1. Создание модели поставщиков с помощью диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="76891-102">Task 1: Creating Suppliers Model using Master Data Manager</span></span>
  <span data-ttu-id="76891-103">В этой задаче вы создадите модель с именем " **поставщики** " в MDS с помощью **Диспетчер основных данных**.</span><span class="sxs-lookup"><span data-stu-id="76891-103">In this task, you create a model named **Suppliers** in MDS using **Master Data Manager**.</span></span>  
  
1.  <span data-ttu-id="76891-104">Перейдите к `http://localhost/MDS` , чтобы запустить **Диспетчер основных данных**.</span><span class="sxs-lookup"><span data-stu-id="76891-104">Navigate to `http://localhost/MDS` to launch **Master Data Manager**.</span></span> <span data-ttu-id="76891-105">Замените URL-адрес, если при настройке веб-приложения было указано другое имя или другой веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="76891-105">Replace the URL if you have configured Web Application with a different name or on a different a web site.</span></span>  
  
     <span data-ttu-id="76891-106">![Диспетчер основных данных — системное администрирование](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-01.jpg "Диспетчер основных данных — системное администрирование")</span><span class="sxs-lookup"><span data-stu-id="76891-106">![Master Data Manager - System Administation](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-01.jpg "Master Data Manager - System Administation")</span></span>  
  
2.  <span data-ttu-id="76891-107">В разделе **задачи администрирования** щелкните **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="76891-107">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="76891-108">Если страница **Добавление модели** не отображается, наведите указатель мыши на пункт **Управление** в строке меню, выберите **модели**, а затем нажмите кнопку **Добавить модель (+)** на панели инструментов, чтобы создать модель.</span><span class="sxs-lookup"><span data-stu-id="76891-108">If you do not see the **Add Model** page, hover mouse over **Manage** on the menu bar, click **Models**, and then click **Add Model (+)** toolbar button to create a model.</span></span>  
  
     <span data-ttu-id="76891-109">![Управление — меню моделей](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-02.jpg "Управление — меню моделей")</span><span class="sxs-lookup"><span data-stu-id="76891-109">![Manage - Models Menu](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-02.jpg "Manage - Models Menu")</span></span>  
  
     <span data-ttu-id="76891-110">![Кнопка панели инструментов «Добавить модель»](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-03.jpg "Кнопка панели инструментов «Добавить модель»")</span><span class="sxs-lookup"><span data-stu-id="76891-110">![Add Model Toolbat Button](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-03.jpg "Add Model Toolbat Button")</span></span>  
  
4.  <span data-ttu-id="76891-111">Введите **поставщики** для **имени модели**.</span><span class="sxs-lookup"><span data-stu-id="76891-111">Enter **Suppliers** for **Model name**.</span></span>  
  
5.  <span data-ttu-id="76891-112">Снимите флажок **создать сущность с тем же именем, что и параметр модели** .</span><span class="sxs-lookup"><span data-stu-id="76891-112">Clear **Create entity with same name as model** option.</span></span> <span data-ttu-id="76891-113">Сущность будет создана позже с помощью **надстройка MDS для Excel**.</span><span class="sxs-lookup"><span data-stu-id="76891-113">You will create an entity later using the **MDS Add-in for Excel**.</span></span>  
  
     <span data-ttu-id="76891-114">![Страница «Добавление модели»](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-04.jpg "Страница «Добавление модели»")</span><span class="sxs-lookup"><span data-stu-id="76891-114">![Add Model Page](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-04.jpg "Add Model Page")</span></span>  
  
6.  <span data-ttu-id="76891-115">Нажмите кнопку **сохранить модель** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="76891-115">Click **Save Model** button on the toolbar.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="76891-116">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="76891-116">Next Step</span></span>  
 [<span data-ttu-id="76891-117">Задача 2. Отправка данных поставщика в MDS с помощью надстройки MDS для Excel</span><span class="sxs-lookup"><span data-stu-id="76891-117">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>](../../2014/tutorials/task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel.md)  
  
  
