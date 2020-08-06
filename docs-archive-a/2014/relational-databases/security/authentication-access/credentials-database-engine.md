---
title: Учетные данные (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: faa2b5be7cf6918b5d5232763a96ed4dbbc89e51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666996"
---
# <a name="credentials-database-engine"></a><span data-ttu-id="8d987-102">Учетные данные (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="8d987-102">Credentials (Database Engine)</span></span>
  <span data-ttu-id="8d987-103">Учетные данные представляют собой запись, которая содержит сведения для проверки подлинности (учетные данные), которые необходимы для подключения к ресурсу вне [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d987-103">A credential is a record that contains the authentication information (credentials) required to connect to a resource outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8d987-104">Эти сведения используются [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d987-104">This information is used internally by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8d987-105">Большинство учетных данных содержат имя пользователя Windows и пароль.</span><span class="sxs-lookup"><span data-stu-id="8d987-105">Most credentials contain a Windows user name and password.</span></span>  
  
 <span data-ttu-id="8d987-106">Хранимые в учетных данных сведения позволяют пользователю, подключившемуся к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с применением проверки подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , обращаться к ресурсам, размещенным вне данного экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="8d987-106">The information stored in a credential enables a user who has connected to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by way of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to access resources outside the server instance.</span></span> <span data-ttu-id="8d987-107">Когда внешним ресурсом является ОС Windows, проверяется соответствие данных пользователя сведениям, указанным в учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="8d987-107">When the external resource is Windows, the user is authenticated as the Windows user specified in the credential.</span></span> <span data-ttu-id="8d987-108">Одни учетные данные могут соответствовать нескольким зарегистрированным именам входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d987-108">A single credential can be mapped to multiple [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="8d987-109">Но имя входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] может соответствовать только одним учетным данным.</span><span class="sxs-lookup"><span data-stu-id="8d987-109">However, a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can be mapped to only one credential.</span></span>  
  
 <span data-ttu-id="8d987-110">Системные учетные данные создаются автоматически и связываются с определенными конечными точками.</span><span class="sxs-lookup"><span data-stu-id="8d987-110">System credentials are created automatically and are associated with specific endpoints.</span></span> <span data-ttu-id="8d987-111">Имена для системных учетных данных начинаются с двух символов решетки (##).</span><span class="sxs-lookup"><span data-stu-id="8d987-111">Names for system credentials start with two hash signs (##).</span></span>  
  
 <span data-ttu-id="8d987-112">Дополнительные сведения об учетных данных см. в представлении каталога [sys. Credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8d987-112">For more information about credentials, see the [sys.credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) catalog view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="8d987-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8d987-113">Related Content</span></span>  
 <span data-ttu-id="8d987-114">[Создание учетных данных](../authentication-access/create-a-credential.md) [Создание учетных данных &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="8d987-114">[Create a Credential](../authentication-access/create-a-credential.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span></span>  
  
 [<span data-ttu-id="8d987-115">Обеспечение безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d987-115">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  
