---
title: Подготовка SQL Server для скрипта представления CDC-View Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d0c8f942-4c96-456f-ad10-577577c0f74e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bdc0e93b901a6a4b00c908ec3f898b3ceea32ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655298"
---
# <a name="prepare-sql-server-for-oracle-cdc-view-script"></a><span data-ttu-id="77352-102">Подготовка SQL Server для скрипта представления CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="77352-102">Prepare SQL Server for Oracle CDC-View Script</span></span>
  <span data-ttu-id="77352-103">Это диалоговое окно показывает скрипт подготовки SQL, с помощью которого создается база данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="77352-103">This dialog box shows the Prepare SQL script that creates the MSXDBCDC database.</span></span> <span data-ttu-id="77352-104">Эта база данных должна быть на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы имелась возможность использовать ее вместе со службой Oracle CDC для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="77352-104">This database is must be on a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for it to be used with Oracle CDC for SQL Server.</span></span>  
  
 <span data-ttu-id="77352-105">В диалоговом окне «Подготовка скрипта SQL Server» выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="77352-105">Do the following in the Prepare SQL Server Script dialog box.</span></span>  
  
 <span data-ttu-id="77352-106">**Сохранить как**</span><span class="sxs-lookup"><span data-stu-id="77352-106">**Save As**</span></span>  
 <span data-ttu-id="77352-107">Сохранение скрипта в текстовый файл, который можно разместить в любом каталоге.</span><span class="sxs-lookup"><span data-stu-id="77352-107">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="77352-108">Эти скрипты можно будет запустить позднее путем их вставки в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77352-108">You can then run the scripts at a later time by pasting the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="77352-109">**Copy**.</span><span class="sxs-lookup"><span data-stu-id="77352-109">**Copy**</span></span>  
 <span data-ttu-id="77352-110">Копирует скрипт в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="77352-110">Copies the script to the clipboard.</span></span> <span data-ttu-id="77352-111">Затем можно скопировать скрипт в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для его выполнения и создания базы данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="77352-111">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to run them and create the MSXDBCDC database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77352-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="77352-112">See Also</span></span>  
 [<span data-ttu-id="77352-113">Подготовка SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="77352-113">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
