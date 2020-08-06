---
title: Создание определяемой пользователем роли | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0ee905c2636e20315c2180a6be8f8e40f76d5f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658326"
---
# <a name="create-a-user-defined-role"></a><span data-ttu-id="da998-102">Создание пользовательской роли</span><span class="sxs-lookup"><span data-stu-id="da998-102">Create a User-Defined Role</span></span>
    
### <a name="to-create-a-user-defined-role"></a><span data-ttu-id="da998-103">Создание пользовательской роли</span><span class="sxs-lookup"><span data-stu-id="da998-103">To create a user-defined role</span></span>  
  
1.  <span data-ttu-id="da998-104">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da998-104">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="da998-105">Щелкните **обозреватель объектов** в меню **Вид** .</span><span class="sxs-lookup"><span data-stu-id="da998-105">Click **Object Explorer** on the **View** menu.</span></span>  
  
3.  <span data-ttu-id="da998-106">На панели инструментов обозревателя объектов нажмите кнопку **Соединить**и выберите **Компонент Database Engine**.</span><span class="sxs-lookup"><span data-stu-id="da998-106">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
4.  <span data-ttu-id="da998-107">В диалоговом окне **Соединение с сервером** введите имя сервера и выберите режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="da998-107">In the **Connect to Server** dialog box, provide a server name and select an authentication mode.</span></span> <span data-ttu-id="da998-108">Для указания локального сервера можно использовать точку (.), (local) или `localhost`.</span><span class="sxs-lookup"><span data-stu-id="da998-108">You can use a period (.), (local), or `localhost` to indicate the local server.</span></span>  
  
5.  <span data-ttu-id="da998-109">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="da998-109">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="da998-110">Последовательно разверните узлы «Базы данных», «Системные базы данных», «msdb», «Безопасность» и «Роли».</span><span class="sxs-lookup"><span data-stu-id="da998-110">Expand Databases, System Databases, msdb, Security, and Roles.</span></span>  
  
7.  <span data-ttu-id="da998-111">В узле "Роли" щелкните правой кнопкой мыши элемент "Роли базы данных" и выберите **Создать роль базы данных**.</span><span class="sxs-lookup"><span data-stu-id="da998-111">In the Roles node, right-click Database Roles, and click **New Database Role**.</span></span>  
  
8.  <span data-ttu-id="da998-112">На странице «Общие» введите имя и при необходимости укажите владельца, схемы владельца и членов роли.</span><span class="sxs-lookup"><span data-stu-id="da998-112">On the General page, provide a name and optionally, specify an owner and owned schemas and add role members.</span></span>  
  
9. <span data-ttu-id="da998-113">При необходимости нажмите кнопку **Разрешения** и настройте разрешения объекта.</span><span class="sxs-lookup"><span data-stu-id="da998-113">Optionally, click **Permissions** and configure object permissions.</span></span>  
  
10. <span data-ttu-id="da998-114">При необходимости нажмите кнопку **Расширенные свойства** и настройте расширенные свойства.</span><span class="sxs-lookup"><span data-stu-id="da998-114">Optionally, click **Extended Properties** and configure any extended properties.</span></span>  
  
11. <span data-ttu-id="da998-115">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="da998-115">Click **OK**.</span></span>  
  
  
