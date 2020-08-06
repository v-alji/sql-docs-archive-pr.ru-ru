---
title: Скрытие системных объектов в обозревателе объектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- hiding system objects
- system objects [SQL Server]
- objects [SQL Server], hiding
- Object Explorer, hiding objects
ms.assetid: c01d8804-838c-4f75-b78c-80e41e4fffdc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e039446191154144dd6660fa6e8d3b4b65d1013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654023"
---
# <a name="hide-system-objects-in-object-explorer"></a><span data-ttu-id="98a07-102">Скрыть системные объекты в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="98a07-102">Hide System Objects in Object Explorer</span></span>
  <span data-ttu-id="98a07-103">В этом разделе описывается, как скрыть системные объекты в обозревателе объектов [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98a07-103">This topic describes how to hide system objects in Object Explorer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="98a07-104">Узел **Базы данных** в обозревателе объектов содержит системные объекты, такие как системные базы данных.</span><span class="sxs-lookup"><span data-stu-id="98a07-104">The **Databases** node of Object Explorer contains system objects such as the system databases.</span></span> <span data-ttu-id="98a07-105">На страницах **Сервис**/**Параметры** можно скрыть системные объекты.</span><span class="sxs-lookup"><span data-stu-id="98a07-105">Use the **Tools**/**Options** pages to hide the system objects.</span></span> <span data-ttu-id="98a07-106">На некоторые системные объекты, например системные функции и типы данных, эта настройка не влияет.</span><span class="sxs-lookup"><span data-stu-id="98a07-106">Some system objects, such as system functions and system data types, are not affected by this setting.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98a07-107">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98a07-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-hide-system-objects-in-object-explorer"></a><span data-ttu-id="98a07-108">Скрытие системных объектов в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="98a07-108">To hide system objects in Object Explorer</span></span>  
  
1.  <span data-ttu-id="98a07-109">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="98a07-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="98a07-110">На странице **Среда/загрузка** установите флажок **Скрыть системные объекты в обозревателе объектов**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="98a07-110">On the **Environment/Startup** page, select **Hide system objects in Object Explorer**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="98a07-111">В диалоговом окне **SQL Server Management Studio** нажмите кнопку **ОК** , чтобы подтвердить, что среда SQL Server Management Studio должна быть перезапущена для вступления в силу изменений.</span><span class="sxs-lookup"><span data-stu-id="98a07-111">In the **SQL Server Management Studio** dialog box, click **OK** to acknowledge that SQL Server Management Studio must be restarted for this change to take effect.</span></span>  
  
4.  <span data-ttu-id="98a07-112">Закройте и снова откройте среду SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="98a07-112">Close and reopen SQL Server Management Studio.</span></span>  
  
  
