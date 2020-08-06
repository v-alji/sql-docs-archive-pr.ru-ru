---
title: Учебник. Начало работы с ядром СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorials [connecting]
- tutorials [Database Engine]
- unable to connect [SQL Server]
- failure to connect [SQL Server]
- connecting tutorial [SQL Server]
ms.assetid: 655e709b-346b-469c-bddc-a5a0238d07e0
author: rothja
ms.author: jroth
ms.openlocfilehash: aaa1fb21c026d064c2b14db73aadc2b82e9c15d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668129"
---
# <a name="tutorial-getting-started-with-the-database-engine"></a><span data-ttu-id="6c37a-102">Учебник. Приступая к работе с компонентом Database Engine</span><span class="sxs-lookup"><span data-stu-id="6c37a-102">Tutorial: Getting Started with the Database Engine</span></span>
  <span data-ttu-id="6c37a-103">Добро пожаловать в учебник «Приступая к работе с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="6c37a-103">Welcome to the Getting Started with the [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorial.</span></span> <span data-ttu-id="6c37a-104">Этот учебник предназначен для пользователей, незнакомых с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , установивших выпуск [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c37a-104">This tutorial is intended for users who are new to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and who have installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="6c37a-105">Этот краткий курс поможет приступить к работе с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c37a-105">This brief tutorial helps you get started using the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="6c37a-106">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="6c37a-106">What You Will Learn</span></span>  
 <span data-ttu-id="6c37a-107">В этом учебнике рассказано, как подключиться к компоненту [!INCLUDE[ssDE](../includes/ssde-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] как на локальном компьютере, так и на удаленном.</span><span class="sxs-lookup"><span data-stu-id="6c37a-107">This tutorial shows you how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on both the local computer and from another computer.</span></span>  
  
 <span data-ttu-id="6c37a-108">Учебник разделен на два занятия.</span><span class="sxs-lookup"><span data-stu-id="6c37a-108">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="6c37a-109">Занятие 1. Подключение к ядру СУБД</span><span class="sxs-lookup"><span data-stu-id="6c37a-109">Lesson 1: Connecting to the Database Engine</span></span>](lesson-1-connecting-to-the-database-engine.md)  
 <span data-ttu-id="6c37a-110">Это занятие учит соединяться с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)] и позволять соединяться другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6c37a-110">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] and enable additional people to connect.</span></span>  
  
 [<span data-ttu-id="6c37a-111">Занятие 2. Соединение с другого компьютера</span><span class="sxs-lookup"><span data-stu-id="6c37a-111">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
 <span data-ttu-id="6c37a-112">Это занятие учит соединяться с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)] с другого компьютера, включая активацию протоколов, настройку портов и настроек брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="6c37a-112">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from a second computer, including enabling protocols, configuring ports, and configuring firewall settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c37a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6c37a-113">Requirements</span></span>  
 <span data-ttu-id="6c37a-114">Для изучения этого учебника предварительный набор знаний не нужен.</span><span class="sxs-lookup"><span data-stu-id="6c37a-114">This tutorial has no knowledge prerequisites.</span></span>  
  
 <span data-ttu-id="6c37a-115">Для работы с этим учебником в системе должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="6c37a-115">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="6c37a-116">.</span><span class="sxs-lookup"><span data-stu-id="6c37a-116">.</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] <span data-ttu-id="6c37a-117">можно установить, запустив программу установки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] либо выполнив загрузку и установку из [Центра загрузки Майкрософт](https://go.microsoft.com/fwlink/?LinkId=144346).</span><span class="sxs-lookup"><span data-stu-id="6c37a-117">can be installed by running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup or by downloading and installing from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c37a-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c37a-118">See Also</span></span>  
 [<span data-ttu-id="6c37a-119">Руководство: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6c37a-119">Tutorial: SQL Server Management Studio</span></span>](../ssms/tutorials/tutorial-sql-server-management-studio.md)  
  
  
