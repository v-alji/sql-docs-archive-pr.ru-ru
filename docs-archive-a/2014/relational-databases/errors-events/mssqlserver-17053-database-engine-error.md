---
title: MSSQLSERVER_17053 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17053 (Database Engine error)
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11137ba334b66f20c7d9a6caaaf7d1ef42c15dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654317"
---
# <a name="mssqlserver_17053"></a><span data-ttu-id="b55e0-102">MSSQLSERVER_17053</span><span class="sxs-lookup"><span data-stu-id="b55e0-102">MSSQLSERVER_17053</span></span>
    
## <a name="details"></a><span data-ttu-id="b55e0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b55e0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b55e0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b55e0-104">Product Name</span></span>|<span data-ttu-id="b55e0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b55e0-105">SQL Server</span></span>|  
|<span data-ttu-id="b55e0-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b55e0-106">Event ID</span></span>|<span data-ttu-id="b55e0-107">17053</span><span class="sxs-lookup"><span data-stu-id="b55e0-107">17053</span></span>|  
|<span data-ttu-id="b55e0-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b55e0-108">Event Source</span></span>|<span data-ttu-id="b55e0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b55e0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b55e0-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b55e0-110">Component</span></span>|<span data-ttu-id="b55e0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b55e0-111">SQLEngine</span></span>|  
|<span data-ttu-id="b55e0-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b55e0-112">Symbolic Name</span></span>|<span data-ttu-id="b55e0-113">OS_ERROR</span><span class="sxs-lookup"><span data-stu-id="b55e0-113">OS_ERROR</span></span>|  
|<span data-ttu-id="b55e0-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b55e0-114">Message Text</span></span>|<span data-ttu-id="b55e0-115">%ls: Ошибка операционной системы %ls.</span><span class="sxs-lookup"><span data-stu-id="b55e0-115">%ls: Operating system error %ls encountered.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b55e0-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b55e0-116">Explanation</span></span>  
 <span data-ttu-id="b55e0-117">Произошла общая системная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b55e0-117">Generic operating system error occurred.</span></span>  <span data-ttu-id="b55e0-118">Результирующее состояние системы неизвестно.</span><span class="sxs-lookup"><span data-stu-id="b55e0-118">Not clear what the resulting state is.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b55e0-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b55e0-119">User Action</span></span>  
 <span data-ttu-id="b55e0-120">Обычно это сообщение выдается совместно с сообщением о другой ошибке и призвано помочь диагностировать проблему.</span><span class="sxs-lookup"><span data-stu-id="b55e0-120">Usually this is in conjunction with some other error and should be used to help diagnose that failure.</span></span> <span data-ttu-id="b55e0-121">Например, это может быть неудачная попытка чтения или записи файлов данных или журнала, операции чтения или записи в системный реестр или другие непредвиденные сбои функций Win32API.</span><span class="sxs-lookup"><span data-stu-id="b55e0-121">Examples would include reads or writes to data or log files that fail, registry read/write operations, or other unexpected Win32API failures.</span></span>  
  
  
