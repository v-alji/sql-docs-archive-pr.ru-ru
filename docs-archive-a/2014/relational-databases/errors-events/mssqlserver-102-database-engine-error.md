---
title: MSSQLSERVER_102 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655257"
---
# <a name="mssqlserver_102"></a><span data-ttu-id="efbce-102">MSSQLSERVER_102</span><span class="sxs-lookup"><span data-stu-id="efbce-102">MSSQLSERVER_102</span></span>
    
## <a name="details"></a><span data-ttu-id="efbce-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="efbce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efbce-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="efbce-104">Product Name</span></span>|<span data-ttu-id="efbce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="efbce-105">SQL Server</span></span>|  
|<span data-ttu-id="efbce-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="efbce-106">Event ID</span></span>|<span data-ttu-id="efbce-107">102</span><span class="sxs-lookup"><span data-stu-id="efbce-107">102</span></span>|  
|<span data-ttu-id="efbce-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="efbce-108">Event Source</span></span>|<span data-ttu-id="efbce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="efbce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="efbce-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="efbce-110">Component</span></span>|<span data-ttu-id="efbce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="efbce-111">SQLEngine</span></span>|  
|<span data-ttu-id="efbce-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="efbce-112">Symbolic Name</span></span>|<span data-ttu-id="efbce-113">P_SYNTAXERR2</span><span class="sxs-lookup"><span data-stu-id="efbce-113">P_SYNTAXERR2</span></span>|  
|<span data-ttu-id="efbce-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="efbce-114">Message Text</span></span>|<span data-ttu-id="efbce-115">Неправильный синтаксис около "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="efbce-115">Incorrect syntax near '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efbce-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="efbce-116">Explanation</span></span>  
 <span data-ttu-id="efbce-117">Указывает на синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="efbce-117">Indicates a syntax error.</span></span> <span data-ttu-id="efbce-118">Дополнительная информация недоступна из-за того, что ошибка мешает компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] обработать инструкцию.</span><span class="sxs-lookup"><span data-stu-id="efbce-118">Additional information is not available because the error prevents the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from processing the statement.</span></span>  
  
 <span data-ttu-id="efbce-119">Может быть вызвана попыткой создать симметричный ключ с помощью устаревшего шифрования RC4 или RC4_128 при нахождении не в режимах совместимости 90 или 100.</span><span class="sxs-lookup"><span data-stu-id="efbce-119">Can be caused by attempting to create a symmetric key using the deprecated RC4 or RC4_128 encryption, when not in 90 or 100 compatibility mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efbce-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="efbce-120">User Action</span></span>  
 <span data-ttu-id="efbce-121">Проверьте инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] на наличие синтаксических ошибок.</span><span class="sxs-lookup"><span data-stu-id="efbce-121">Search the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement for syntax errors.</span></span>  
  
 <span data-ttu-id="efbce-122">При создании симметричного ключа с помощью RC4 или RC4_128 выберите более новое шифрование, например один из алгоритмов AES.</span><span class="sxs-lookup"><span data-stu-id="efbce-122">If creating a symmetric key using the RC4 or RC4_128, select a newer encryption such as one of the AES algorithms.</span></span> <span data-ttu-id="efbce-123">(Рекомендуется.) Если необходимо использовать RC4, используйте ALTER DATABASE SET COMPATIBILITY_LEVEL, чтобы установить базу данных на уровень совместимости 90 или 100.</span><span class="sxs-lookup"><span data-stu-id="efbce-123">(Recommended.) If you must use RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL to set the database to compatibility level 90 or 100.</span></span> <span data-ttu-id="efbce-124">(Не рекомендуется.)</span><span class="sxs-lookup"><span data-stu-id="efbce-124">(Not recommended.)</span></span>  
  
  
