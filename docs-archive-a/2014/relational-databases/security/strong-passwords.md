---
title: Надежные пароли | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730305"
---
# <a name="strong-passwords"></a><span data-ttu-id="51ee5-102">Надежные пароли</span><span class="sxs-lookup"><span data-stu-id="51ee5-102">Strong Passwords</span></span>
  <span data-ttu-id="51ee5-103">Пароли могут быть самым слабым звеном в развертывании системы безопасности сервера.</span><span class="sxs-lookup"><span data-stu-id="51ee5-103">Passwords can be the weakest link in a server security deployment.</span></span> <span data-ttu-id="51ee5-104">При выборе пароля всегда следует проявлять особую внимательность.</span><span class="sxs-lookup"><span data-stu-id="51ee5-104">You should always take great care when you select a password.</span></span> <span data-ttu-id="51ee5-105">Надежный пароль имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="51ee5-105">A strong password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="51ee5-106">содержит как минимум 8 символов;</span><span class="sxs-lookup"><span data-stu-id="51ee5-106">Is at least 8 characters long.</span></span>  
  
-   <span data-ttu-id="51ee5-107">сочетает в себе буквы, числа и специальные символы;</span><span class="sxs-lookup"><span data-stu-id="51ee5-107">Combines letters, numbers, and symbol characters within the password.</span></span>  
  
-   <span data-ttu-id="51ee5-108">не содержится в словарях;</span><span class="sxs-lookup"><span data-stu-id="51ee5-108">Is not found in a dictionary.</span></span>  
  
-   <span data-ttu-id="51ee5-109">не является именем команды;</span><span class="sxs-lookup"><span data-stu-id="51ee5-109">Is not the name of a command.</span></span>  
  
-   <span data-ttu-id="51ee5-110">не является именем человека;</span><span class="sxs-lookup"><span data-stu-id="51ee5-110">Is not the name of a person.</span></span>  
  
-   <span data-ttu-id="51ee5-111">не является именем пользователя;</span><span class="sxs-lookup"><span data-stu-id="51ee5-111">Is not the name of a user.</span></span>  
  
-   <span data-ttu-id="51ee5-112">не является именем компьютера;</span><span class="sxs-lookup"><span data-stu-id="51ee5-112">Is not the name of a computer.</span></span>  
  
-   <span data-ttu-id="51ee5-113">регулярно меняется;</span><span class="sxs-lookup"><span data-stu-id="51ee5-113">Is changed regularly.</span></span>  
  
-   <span data-ttu-id="51ee5-114">в значительной степени отличается от предыдущих паролей.</span><span class="sxs-lookup"><span data-stu-id="51ee5-114">Is significantly different from previous passwords.</span></span>  
  
 <span data-ttu-id="51ee5-115">Пароли [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут содержать до 128 символов, включая буквы, знаки и цифры.</span><span class="sxs-lookup"><span data-stu-id="51ee5-115">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain up to 128 characters, including letters, symbols, and digits.</span></span> <span data-ttu-id="51ee5-116">Поскольку имена входа, имена пользователей, роли и пароли часто используются в инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] , определенные символы должны заключаться в двойные кавычки (") или квадратные скобки ([ ]).</span><span class="sxs-lookup"><span data-stu-id="51ee5-116">Because logins, user names, roles, and passwords are frequently used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, certain symbols must be enclosed by double quotation marks (") or square brackets ([ ]).</span></span> <span data-ttu-id="51ee5-117">Используйте разделители в инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)] , если имя входа, пользователь, роль или пароль [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеют следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="51ee5-117">Use these delimiters in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, user, role, or password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="51ee5-118">содержат пробел или начинаются с пробела;</span><span class="sxs-lookup"><span data-stu-id="51ee5-118">Contains or starts with a space character.</span></span>  
  
-   <span data-ttu-id="51ee5-119">начинаются с символа $ или \@.</span><span class="sxs-lookup"><span data-stu-id="51ee5-119">Starts with the $ or \@ character.</span></span>  
  
 <span data-ttu-id="51ee5-120">При использовании в строке подключения OLE DB или ODBC имя входа или пароль не должны содержать следующие символы: [] {} () , ; ?</span><span class="sxs-lookup"><span data-stu-id="51ee5-120">If used in an OLE DB or ODBC connection string, a login or password must not contain the following characters: [] {}() , ; ?</span></span> <span data-ttu-id="51ee5-121">\* !</span><span class="sxs-lookup"><span data-stu-id="51ee5-121">\* !</span></span> <span data-ttu-id="51ee5-122">\@.</span><span class="sxs-lookup"><span data-stu-id="51ee5-122">\@.</span></span> <span data-ttu-id="51ee5-123">Эти символы используются для инициализации соединения или для указания его отдельных значений.</span><span class="sxs-lookup"><span data-stu-id="51ee5-123">These characters are used to either initialize a connection or separate connection values.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="51ee5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="51ee5-124">Related Content</span></span>  
 [<span data-ttu-id="51ee5-125">Политика паролей</span><span class="sxs-lookup"><span data-stu-id="51ee5-125">Password Policy</span></span>](password-policy.md)  
  
  
