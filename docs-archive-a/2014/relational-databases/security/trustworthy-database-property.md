---
title: Свойство базы данных TRUSTWORTHY | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database property
ms.assetid: 64b2a53d-4416-4a19-acc0-664a61b45348
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23391fe48037d4cd7f69aef7df6649949301a0f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730297"
---
# <a name="trustworthy-database-property"></a><span data-ttu-id="0bc06-102">Свойство базы данных TRUSTWORTHY</span><span class="sxs-lookup"><span data-stu-id="0bc06-102">TRUSTWORTHY Database Property</span></span>
  <span data-ttu-id="0bc06-103">Свойство TRUSTWORTHY используется для указания того, доверяет ли экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базе данных и ее содержимому.</span><span class="sxs-lookup"><span data-stu-id="0bc06-103">The TRUSTWORTHY database property is used to indicate whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trusts the database and the contents within it.</span></span> <span data-ttu-id="0bc06-104">По умолчанию это свойство имеет значение OFF, но его можно установить в ON при помощи инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="0bc06-104">By default, this setting is OFF, but can be set to ON by using the ALTER DATABASE statement.</span></span> <span data-ttu-id="0bc06-105">Например, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span><span class="sxs-lookup"><span data-stu-id="0bc06-105">For example, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0bc06-106">Изменять это свойство могут только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0bc06-106">To set this option, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="0bc06-107">Это свойство позволяет уменьшить уязвимость системы перед рядом угроз, связанных с присоединением базы данных, содержащей один из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="0bc06-107">This property can be used to reduce certain threats that can exist as a result of attaching a database that contains one of the following objects:</span></span>  
  
-   <span data-ttu-id="0bc06-108">вредоносные сборки с параметром разрешения EXTERNAL_ACCESS или UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="0bc06-108">Malicious assemblies with an EXTERNAL_ACCESS or UNSAFE permission setting.</span></span> <span data-ttu-id="0bc06-109">Дополнительные сведения см. в статье [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="0bc06-109">For more information, see [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span></span>  
  
-   <span data-ttu-id="0bc06-110">вредоносные модули, выполняемые в контексте привилегированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0bc06-110">Malicious modules that are defined to execute as high privileged users.</span></span> <span data-ttu-id="0bc06-111">Дополнительные сведения см. в разделе [Предложение EXECUTE AS (Transact-SQL)](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0bc06-111">For more information, see [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="0bc06-112">В обеих ситуациях объектам нужны конкретные права доступа, что повышает уязвимость системы. Для защиты от атак при использовании таких объектов в контексте базы данных, уже присоединенной к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], применяют соответствующие механизмы.</span><span class="sxs-lookup"><span data-stu-id="0bc06-112">Both of these situations require a specific degree of privileges and are protected against by appropriate mechanisms when they are used in the context of a database that is already attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0bc06-113">Однако, если база данных переведена в режим работы «вне сети», пользователь, имеющий доступ к файлу базы данных, теоретически может присоединить ее к любому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и добавить в нее вредоносное содержимое.</span><span class="sxs-lookup"><span data-stu-id="0bc06-113">However, if the database is taken offline, a user that has access to the database file can potentially attach it to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of his or her choice and add malicious content to the database.</span></span> <span data-ttu-id="0bc06-114">Когда в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]отсоединяются и присоединяются базы данных, для файлов данных и журналов задаются определенные разрешения, ограничивающие доступ к файлам базы данных.</span><span class="sxs-lookup"><span data-stu-id="0bc06-114">When databases are detached and attached in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], certain permissions are set on the data and log files that restrict access to the database files.</span></span>  
  
 <span data-ttu-id="0bc06-115">Так как база данных, присоединенная к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , не может сразу стать доверенной, то ей не разрешается доступ к ресурсам вне ее области до тех пор, пока не будет явно отмечена как доверенная.</span><span class="sxs-lookup"><span data-stu-id="0bc06-115">Because a database that is attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be immediately trusted, the database is not allowed to access resources beyond the scope of the database until the database is explicitly marked trustworthy.</span></span> <span data-ttu-id="0bc06-116">Для успешного выполнения модулей, которые обращаются к ресурсам, внешним по отношению к базе данных, и сборок с параметром разрешения EXTERNAL_ACCESS или UNSAFE нужно, чтобы были удовлетворены кое-какие дополнительные требования.</span><span class="sxs-lookup"><span data-stu-id="0bc06-116">Also, modules that are designed to access resources outside the database, and assemblies with either the EXTERNAL_ACCESS and UNSAFE permission setting, have additional requirements in order to run successfully.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="0bc06-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0bc06-117">Related Content</span></span>  
 [<span data-ttu-id="0bc06-118">Центр безопасности для ядра СУБД SQL Server и Базы данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="0bc06-118">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="0bc06-119">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0bc06-119">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
