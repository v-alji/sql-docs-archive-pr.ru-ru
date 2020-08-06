---
title: MSSQLSERVER_15661 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15661 (Database Engine error)
ms.assetid: 88b01bfb-74ce-4aa0-aec0-7885261c7ef3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 966e23e8d970c36eba81253228cc18ed4af3ff77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654318"
---
# <a name="mssqlserver_15661"></a><span data-ttu-id="b4534-102">MSSQLSERVER_15661</span><span class="sxs-lookup"><span data-stu-id="b4534-102">MSSQLSERVER_15661</span></span>
    
## <a name="details"></a><span data-ttu-id="b4534-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b4534-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4534-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b4534-104">Product Name</span></span>|<span data-ttu-id="b4534-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4534-105">SQL Server</span></span>|  
|<span data-ttu-id="b4534-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b4534-106">Event ID</span></span>|<span data-ttu-id="b4534-107">15661</span><span class="sxs-lookup"><span data-stu-id="b4534-107">15661</span></span>|  
|<span data-ttu-id="b4534-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b4534-108">Event Source</span></span>|<span data-ttu-id="b4534-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b4534-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b4534-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b4534-110">Component</span></span>|<span data-ttu-id="b4534-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b4534-111">SQLEngine</span></span>|  
|<span data-ttu-id="b4534-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b4534-112">Symbolic Name</span></span>|<span data-ttu-id="b4534-113">SQLErrorNum15661</span><span class="sxs-lookup"><span data-stu-id="b4534-113">SQLErrorNum15661</span></span>|  
|<span data-ttu-id="b4534-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b4534-114">Message Text</span></span>|<span data-ttu-id="b4534-115">Хранимая процедура sp_estimate_data_compression_savings не может применяться для временных таблиц.</span><span class="sxs-lookup"><span data-stu-id="b4534-115">The sp_estimate_data_compression_savings stored procedure cannot be used for temporary tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b4534-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b4534-116">Explanation</span></span>  
 <span data-ttu-id="b4534-117">В качестве аргумента для хранимой процедуры sp_estimate_data_compression_savings указана временная таблица.</span><span class="sxs-lookup"><span data-stu-id="b4534-117">A temporary table was used as an argument for the sp_estimate_data_compression_savings stored procedure.</span></span> <span data-ttu-id="b4534-118">Хотя сжатие временных таблиц поддерживается, пользоваться хранимой процедурой sp_estimate_data_compression_savings для оценки сжатия нельзя.</span><span class="sxs-lookup"><span data-stu-id="b4534-118">Although the compression of temporary tables is supported, you cannot use sp_estimate_data_compression_savings to estimate the compression savings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4534-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b4534-119">User Action</span></span>  
 <span data-ttu-id="b4534-120">Исключите временную таблицу из числа аргументов хранимой процедуры sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="b4534-120">Remove the temporary table as an argument for sp_estimate_data_compression_savings.</span></span>  
  
  
