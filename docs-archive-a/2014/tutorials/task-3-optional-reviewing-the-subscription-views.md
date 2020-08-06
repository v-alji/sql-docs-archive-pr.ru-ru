---
title: 'Задача 3 (необязательно): Просмотр представлений подписки | Документация Майкрософт'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3f1d3eb7-2baa-4215-b040-0b41e3d10740
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35cf0c246ab778b46a2ceaa2b6ff6fad02d0b670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656103"
---
# <a name="task-3-optional-reviewing-the-subscription-views"></a><span data-ttu-id="8eeed-102">Задача 3 (необязательно). Проверка представлений подписки</span><span class="sxs-lookup"><span data-stu-id="8eeed-102">Task 3 (Optional): Reviewing the Subscription Views</span></span>
  <span data-ttu-id="8eeed-103">В этой задаче вы ознакомитесь с созданием представлений SQL с помощью среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8eeed-103">In this task, you confirm that the SQL views are created by using SQL Server Management Studio.</span></span>

1.  <span data-ttu-id="8eeed-104">Запустите **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="8eeed-104">Launch **SQL Server Management Studio**.</span></span> <span data-ttu-id="8eeed-105">Нажмите кнопку **Пуск** , выберите пункт **все программы**, щелкните **Microsoft SQL Server 2012**, а затем — **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="8eeed-105">Click the **Start** button, click **All Programs**, click **Microsoft SQL Server 2012**, and then click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="8eeed-106">В окне **Подключение к серверу** задайте для параметра **тип сервера** значение **ядро СУБД**, введите **имя сервера** (или выберите **(local)**, выберите соответствующую **проверку подлинности**и нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="8eeed-106">In the **Connect to Server** window, set **Server Type** to **Database Engine**, type the **server name** (or select **(local)**, and select appropriate **authentication**, and click **Connect**.</span></span>

3.  <span data-ttu-id="8eeed-107">В области **Обозреватель объектов** разверните узел **базы данных**, разверните узел **MDS**, а затем разверните узел **представления**.</span><span class="sxs-lookup"><span data-stu-id="8eeed-107">In the **Object Explorer** pane, expand **Databases**, expand **MDS**, and then expand **Views**.</span></span>

4.  <span data-ttu-id="8eeed-108">Убедитесь, что вы видите \*\*MDM. \*\*Список «поставщики» в списке.</span><span class="sxs-lookup"><span data-stu-id="8eeed-108">Confirm that you see the **mdm.Suppliers** view in the list.</span></span>

     <span data-ttu-id="8eeed-109">![SQL Server Management Studio — представление mdm.Suppliers](../../2014/tutorials/media/et-reviewingthesubscriptionviews.jpg "SQL Server Management Studio — представление mdm.Suppliers")</span><span class="sxs-lookup"><span data-stu-id="8eeed-109">![SQL Server Management Studio - mdm.Suppliers View](../../2014/tutorials/media/et-reviewingthesubscriptionviews.jpg "SQL Server Management Studio - mdm.Suppliers View")</span></span>

## <a name="next-step"></a><span data-ttu-id="8eeed-110">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8eeed-110">Next Step</span></span>
 [<span data-ttu-id="8eeed-111">Задача 4. Создание проекта SSIS с помощью SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="8eeed-111">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>](../../2014/tutorials/task-4-creating-an-ssis-project-using-sql-server-data-tools.md)