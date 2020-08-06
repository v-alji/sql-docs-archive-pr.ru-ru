---
title: Служба агент SQL Server не может использовать проверку подлинности SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- authentication [SQL Server Agent]
- SQL Server Authentication [SQL Server Agent]
ms.assetid: c39f3ec3-fc2c-4c12-940f-60d8d3d17660
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 32188b1c47168aefbca914fa15f71850df716153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665773"
---
# <a name="sql-server-agent-service-cannot-use-sql-server-authentication"></a><span data-ttu-id="73f89-102">Служба агента SQL Server не может использовать проверку подлинности SQL Server</span><span class="sxs-lookup"><span data-stu-id="73f89-102">SQL Server Agent Service cannot use SQL Server Authentication</span></span>
  <span data-ttu-id="73f89-103">Агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает только проверку подлинности Windows, когда служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] подключается к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73f89-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent only supports Windows Authentication when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="73f89-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="73f89-104">Component</span></span>  
 <span data-ttu-id="73f89-105">Агент[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f89-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="73f89-106">Описание</span><span class="sxs-lookup"><span data-stu-id="73f89-106">Description</span></span>  
 <span data-ttu-id="73f89-107">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может осуществлять вход в базу данных только с проверкой подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="73f89-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can only log on to the database using Windows Authentication.</span></span> <span data-ttu-id="73f89-108">Это означает, что учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна представлять пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73f89-108">This means that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account must be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="73f89-109">Дополнительные сведения см. в разделах «Безопасность автоматического администрирования» и «Обеспечение безопасности агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]» в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73f89-109">For more information, see the topics "Security for Automatic Administration" and "Implementing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Security" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f89-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="73f89-110">See Also</span></span>  
 [<span data-ttu-id="73f89-111">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="73f89-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
