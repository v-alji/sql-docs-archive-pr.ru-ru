---
title: MSSQLSERVER_50000 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 50000 [SQL Server Native Client setup error]
ms.assetid: 5426d87a-d5d9-4984-b211-b07d69e834a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cc805042bff7259a311ca3f2acf4c26db59381b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732685"
---
# <a name="mssqlserver_50000"></a><span data-ttu-id="f8abf-102">MSSQLSERVER_50000</span><span class="sxs-lookup"><span data-stu-id="f8abf-102">MSSQLSERVER_50000</span></span>
    
## <a name="details"></a><span data-ttu-id="f8abf-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f8abf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8abf-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f8abf-104">Product Name</span></span>|<span data-ttu-id="f8abf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8abf-105">SQL Server</span></span>|  
|<span data-ttu-id="f8abf-106">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="f8abf-106">Product Version</span></span>|<span data-ttu-id="f8abf-107">11.0</span><span class="sxs-lookup"><span data-stu-id="f8abf-107">11.0</span></span>|  
|<span data-ttu-id="f8abf-108">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f8abf-108">Event ID</span></span>|<span data-ttu-id="f8abf-109">50 000</span><span class="sxs-lookup"><span data-stu-id="f8abf-109">50000</span></span>|  
|<span data-ttu-id="f8abf-110">Источник события</span><span class="sxs-lookup"><span data-stu-id="f8abf-110">Event Source</span></span>|<span data-ttu-id="f8abf-111">SETUP</span><span class="sxs-lookup"><span data-stu-id="f8abf-111">SETUP</span></span>|  
|<span data-ttu-id="f8abf-112">Компонент</span><span class="sxs-lookup"><span data-stu-id="f8abf-112">Component</span></span>|<span data-ttu-id="f8abf-113">Собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8abf-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>|  
|<span data-ttu-id="f8abf-114">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f8abf-114">Symbolic Name</span></span>||  
|<span data-ttu-id="f8abf-115">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f8abf-115">Message Text</span></span>|<span data-ttu-id="f8abf-116">Произошла сетевая ошибка при попытке чтения из файла «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="f8abf-116">A network error occurred while attempting to read from the file '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f8abf-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f8abf-117">Explanation</span></span>  
 <span data-ttu-id="f8abf-118">Была сделана попытка установить (или обновить) собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на компьютер, где собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] уже установлен и где существующая установка производилась из MSI-файла, который был переименован из sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="f8abf-118">An attempt was made to install (or update) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client on a computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is already installed, and where the existing installation was from an MSI file that was renamed from sqlncli.msi.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f8abf-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f8abf-119">User Action</span></span>  
 <span data-ttu-id="f8abf-120">Для разрешения этой ошибки удалите существующую версию собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8abf-120">To resolve this error, uninstall the existing version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="f8abf-121">Чтобы предотвратить эту ошибку, не устанавливайте собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из MSI-файла, который не называется sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="f8abf-121">To prevent this error, do not install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client from an MSI file that is not named sqlncli.msi.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="f8abf-122">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="f8abf-122">Internal-Only</span></span>  
  
