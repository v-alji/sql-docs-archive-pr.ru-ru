---
title: Восстановление главного ключа базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 614ba8bdc494ae7e7e5b3ed7b62390721ef642a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752063"
---
# <a name="restore-a-database-master-key"></a><span data-ttu-id="c0f58-102">Восстановление главного ключа базы данных</span><span class="sxs-lookup"><span data-stu-id="c0f58-102">Restore a Database Master Key</span></span>
  <span data-ttu-id="c0f58-103">В этом разделе описывается, как восстановить главный ключ базы данных в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при помощи [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0f58-103">This topic describes how to restore the database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c0f58-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c0f58-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c0f58-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c0f58-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c0f58-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c0f58-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c0f58-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c0f58-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="c0f58-108">Восстановление главного ключа базы данных с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0f58-108">To restore the database master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0f58-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c0f58-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c0f58-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c0f58-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c0f58-111">Когда главный ключ восстановлен, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] дешифрует все ключи, зашифрованные текущим активным главным ключом, и затем шифрует эти ключи с помощью восстановленного главного ключа.</span><span class="sxs-lookup"><span data-stu-id="c0f58-111">When the master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys that are encrypted with the currently active master key, and then encrypts these keys with the restored master key.</span></span> <span data-ttu-id="c0f58-112">Данную ресурсоемкую операцию следует планировать на то время, когда количество обращений к серверу минимальное.</span><span class="sxs-lookup"><span data-stu-id="c0f58-112">This resource-intensive operation should be scheduled during a period of low demand.</span></span> <span data-ttu-id="c0f58-113">Если текущий главный ключ базы данных не открыт или не может быть открыт, или если какой-либо зашифрованный им ключ не может быть дешифрован, операция восстановления заканчивается неудачно.</span><span class="sxs-lookup"><span data-stu-id="c0f58-113">If the current database master key is not open or cannot be opened, or if any of the keys that are encrypted by it cannot be decrypted, the restore operation fails.</span></span>  
  
-   <span data-ttu-id="c0f58-114">Если во время расшифровки любого объекта произойдет ошибка, восстановление будет прервано.</span><span class="sxs-lookup"><span data-stu-id="c0f58-114">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="c0f58-115">Чтобы пропускать ошибки, можно использовать параметр FORCE, но это приведет к потере всех данных, которые не удается расшифровать.</span><span class="sxs-lookup"><span data-stu-id="c0f58-115">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="c0f58-116">Если главный ключ был зашифрован главным сервисным ключом, восстановленный главный ключ также будет зашифрован главным сервисным ключом.</span><span class="sxs-lookup"><span data-stu-id="c0f58-116">If the master key was encrypted by the service master key, the restored master key will also be encrypted by the service master key.</span></span>  
  
-   <span data-ttu-id="c0f58-117">Если в текущей базе данных нет главного ключа, RESTORE MASTER KEY создает главный ключ.</span><span class="sxs-lookup"><span data-stu-id="c0f58-117">If there is no master key in the current database, RESTORE MASTER KEY creates a master key.</span></span> <span data-ttu-id="c0f58-118">Новый главный ключ не будет автоматически шифроваться главным сервисным ключом.</span><span class="sxs-lookup"><span data-stu-id="c0f58-118">The new master key will not be automatically encrypted with the service master key.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0f58-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="c0f58-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c0f58-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="c0f58-120">Permissions</span></span>  
 <span data-ttu-id="c0f58-121">Требует разрешения CONTROL для базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0f58-121">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="SSMSProcedure"></a><span data-ttu-id="c0f58-122">Использование SQL Server Management Studio с Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0f58-122">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-restore-the-database-master-key"></a><span data-ttu-id="c0f58-123">Восстановление главного ключа базы данных</span><span class="sxs-lookup"><span data-stu-id="c0f58-123">To restore the database master key</span></span>  
  
1.  <span data-ttu-id="c0f58-124">Сохраните резервную копию главного ключа базы данных с физического носителя данных резервных копий или из папки локальной файловой системы.</span><span class="sxs-lookup"><span data-stu-id="c0f58-124">Retrieve a copy of the backed-up database master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="c0f58-125">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0f58-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="c0f58-126">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c0f58-126">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="c0f58-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c0f58-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0f58-128">Путь к файлу ключа и пароль ключа (если он существует) будет отличаться от вышеуказанного.</span><span class="sxs-lookup"><span data-stu-id="c0f58-128">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="c0f58-129">Убедитесь, что оба этих параметра соответствуют настройке конкретного сервера и ключа.</span><span class="sxs-lookup"><span data-stu-id="c0f58-129">Please make sure that both are specific to your server and key set-up.</span></span>  
  
 <span data-ttu-id="c0f58-130">Дополнительные сведения см. в разделе [RESTORE MASTER KEY (Transact-SQL)](/sql/t-sql/statements/restore-master-key-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="c0f58-130">For more information, see [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span></span>  
  
  
