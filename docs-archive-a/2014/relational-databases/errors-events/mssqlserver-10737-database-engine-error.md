---
title: MSSQLSERVER_10737 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666660"
---
# <a name="mssqlserver_10737"></a><span data-ttu-id="a3c14-102">MSSQLSERVER_10737</span><span class="sxs-lookup"><span data-stu-id="a3c14-102">MSSQLSERVER_10737</span></span>
    
## <a name="details"></a><span data-ttu-id="a3c14-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a3c14-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3c14-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a3c14-104">Product Name</span></span>|<span data-ttu-id="a3c14-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3c14-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3c14-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a3c14-106">Event ID</span></span>|<span data-ttu-id="a3c14-107">10737</span><span class="sxs-lookup"><span data-stu-id="a3c14-107">10737</span></span>|  
|<span data-ttu-id="a3c14-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a3c14-108">Event Source</span></span>|<span data-ttu-id="a3c14-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3c14-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3c14-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a3c14-110">Component</span></span>|<span data-ttu-id="a3c14-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3c14-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3c14-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a3c14-112">Symbolic Name</span></span>|<span data-ttu-id="a3c14-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span><span class="sxs-lookup"><span data-stu-id="a3c14-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span></span>|  
|<span data-ttu-id="a3c14-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a3c14-114">Message Text</span></span>|<span data-ttu-id="a3c14-115">Если в предложении DATA_COMPRESSION инструкции ALTER TABLE REBUILD или ALTER INDEX REBUILD указана секция, то должно быть задано предложение PARTITION=ALL.</span><span class="sxs-lookup"><span data-stu-id="a3c14-115">In an ALTER TABLE REBUILD or ALTER INDEX REBUILD statement, when a partition is specified in a DATA_COMPRESSION clause, PARTITION=ALL must be specified.</span></span> <span data-ttu-id="a3c14-116">Предложение PARTITION=ALL используется для подтверждения того, что должны быть перестроены все секции таблицы или индекса, даже если в предложении DATA_COMPRESSION указано только подмножество.</span><span class="sxs-lookup"><span data-stu-id="a3c14-116">The PARTITION=ALL clause is used to reinforce that all partitions of the table or index will be rebuilt, even if only a subset is specified in the DATA_COMPRESSION clause.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="a3c14-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a3c14-117">User Action</span></span>  
 <span data-ttu-id="a3c14-118">Добавьте предложение PARTITION=ALL к инструкции ALTER INDEX или ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="a3c14-118">Add the PARTITION=ALL clause to the ALTER TABLE or ALTER INDEX statement.</span></span> <span data-ttu-id="a3c14-119">Также вы можете перестроить конкретную секцию, используя команду REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span><span class="sxs-lookup"><span data-stu-id="a3c14-119">Or, to rebuild a specific partition, use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span></span>  
  
  
